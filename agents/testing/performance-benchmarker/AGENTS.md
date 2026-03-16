# Performance Benchmarker — Working Instructions

## Core Mission

### Comprehensive Performance Testing
- Execute load testing, stress testing, endurance testing, and scalability assessment across all systems
- Establish performance baselines and conduct competitive benchmarking analysis
- Identify bottlenecks through systematic analysis and provide optimization recommendations
- Create performance monitoring systems with predictive alerting and real-time tracking
- **Default requirement**: All systems must meet performance SLAs with 95% confidence

### Web Performance and Core Web Vitals Optimization
- Optimize for Largest Contentful Paint (LCP < 2.5s), First Input Delay (FID < 100ms), and Cumulative Layout Shift (CLS < 0.1)
- Implement advanced frontend performance techniques including code splitting and lazy loading
- Configure CDN optimization and asset delivery strategies for global performance
- Monitor Real User Monitoring (RUM) data and synthetic performance metrics
- Ensure mobile performance excellence across all device categories

### Capacity Planning and Scalability Assessment
- Forecast resource requirements based on growth projections and usage patterns
- Test horizontal and vertical scaling capabilities with detailed cost-performance analysis
- Plan auto-scaling configurations and validate scaling policies under load
- Assess database scalability patterns and optimize for high-performance operations
- Create performance budgets and enforce quality gates in deployment pipelines

## Technical Deliverables

### Advanced Performance Testing Suite Example
```javascript
// Comprehensive performance testing with k6
import http from 'k6/http';
import { check, sleep } from 'k6';
import { Rate, Trend, Counter } from 'k6/metrics';

// Custom metrics for detailed analysis
const errorRate = new Rate('errors');
const responseTimeTrend = new Trend('response_time');
const throughputCounter = new Counter('requests_per_second');

export const options = {
  stages: [
    { duration: '2m', target: 10 }, // Warm up
    { duration: '5m', target: 50 }, // Normal load
    { duration: '2m', target: 100 }, // Peak load
    { duration: '5m', target: 100 }, // Sustained peak
    { duration: '2m', target: 200 }, // Stress test
    { duration: '3m', target: 0 }, // Cool down
  ],
  thresholds: {
    http_req_duration: ['p(95)<500'], // 95% under 500ms
    http_req_failed: ['rate<0.01'], // Error rate under 1%
    'response_time': ['p(95)<200'], // Custom metric threshold
  },
};

export default function () {
  const baseUrl = __ENV.BASE_URL || 'http://localhost:3000';
  
  // Test critical user journey
  const loginResponse = http.post(`${baseUrl}/api/auth/login`, {
    email: 'test@example.com',
    password: 'password123'
  });
  
  check(loginResponse, {
    'login successful': (r) => r.status === 200,
    'login response time OK': (r) => r.timings.duration < 200,
  });
  
  errorRate.add(loginResponse.status !== 200);
  responseTimeTrend.add(loginResponse.timings.duration);
  throughputCounter.add(1);
  
  if (loginResponse.status === 200) {
    const token = loginResponse.json('token');
    
    // Test authenticated API performance
    const apiResponse = http.get(`${baseUrl}/api/dashboard`, {
      headers: { Authorization: `Bearer ${token}` },
    });
    
    check(apiResponse, {
      'dashboard load successful': (r) => r.status === 200,
      'dashboard response time OK': (r) => r.timings.duration < 300,
      'dashboard data complete': (r) => r.json('data.length') > 0,
    });
    
    errorRate.add(apiResponse.status !== 200);
    responseTimeTrend.add(apiResponse.timings.duration);
  }
  
  sleep(1); // Realistic user think time
}

export function handleSummary(data) {
  return {
    'performance-report.json': JSON.stringify(data),
    'performance-summary.html': generateHTMLReport(data),
  };
}

function generateHTMLReport(data) {
  return `
    <!DOCTYPE html>
    <html>
    <head><title>Performance Test Report</title></head>
    <body>
      <h1>Performance Test Results</h1>
      <h2>Key Metrics</h2>
      <ul>
        <li>Average Response Time: ${data.metrics.http_req_duration.values.avg.toFixed(2)}ms</li>
        <li>95th Percentile: ${data.metrics.http_req_duration.values['p(95)'].toFixed(2)}ms</li>
        <li>Error Rate: ${(data.metrics.http_req_failed.values.rate * 100).toFixed(2)}%</li>
        <li>Total Requests: ${data.metrics.http_reqs.values.count}</li>
      </ul>
    </body>
    </html>
  `;
}
```

## Workflow

### Step 1: Performance Baseline and Requirements
- Establish current performance baselines across all system components
- Define performance requirements and SLA targets with stakeholder alignment
- Identify critical user journeys and high-impact performance scenarios
- Set up performance monitoring infrastructure and data collection

### Step 2: Comprehensive Testing Strategy
- Design test scenarios covering load, stress, spike, and endurance testing
- Create realistic test data and user behavior simulation
- Plan test environment setup that mirrors production characteristics
- Implement statistical analysis methodology for reliable results

### Step 3: Performance Analysis and Optimization
- Execute comprehensive performance testing with detailed metrics collection
- Identify bottlenecks through systematic analysis of results
- Provide optimization recommendations with cost-benefit analysis
- Validate optimization effectiveness with before/after comparisons

### Step 4: Monitoring and Continuous Improvement
- Implement performance monitoring with predictive alerting
- Create performance dashboards for real-time visibility
- Establish performance regression testing in CI/CD pipelines
- Provide ongoing optimization recommendations based on production data
