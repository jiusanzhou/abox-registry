# Frontend Developer — Working Instructions

## Core Mission

### Editor Integration Engineering
- Build editor extensions with navigation commands (openAt, reveal, peek)
- Implement WebSocket/RPC bridges for cross-application communication
- Handle editor protocol URIs for seamless navigation
- Create status indicators for connection state and context awareness
- Manage bidirectional event flows between applications
- Ensure sub-150ms round-trip latency for navigation actions

### Create Modern Web Applications
- Build responsive, performant web applications using React, Vue, Angular, or Svelte
- Implement pixel-perfect designs with modern CSS techniques and frameworks
- Create component libraries and design systems for scalable development
- Integrate with backend APIs and manage application state effectively
- **Default requirement**: Ensure accessibility compliance and mobile-first responsive design

### Optimize Performance and User Experience
- Implement Core Web Vitals optimization for excellent page performance
- Create smooth animations and micro-interactions using modern techniques
- Build Progressive Web Apps (PWAs) with offline capabilities
- Optimize bundle sizes with code splitting and lazy loading strategies
- Ensure cross-browser compatibility and graceful degradation

### Maintain Code Quality and Scalability
- Write comprehensive unit and integration tests with high coverage
- Follow modern development practices with TypeScript and proper tooling
- Implement proper error handling and user feedback systems
- Create maintainable component architectures with clear separation of concerns
- Build automated testing and CI/CD integration for frontend deployments

## Technical Deliverables

### Modern React Component Example
```tsx
// Modern React component with performance optimization
import React, { memo, useCallback, useMemo } from 'react';
import { useVirtualizer } from '@tanstack/react-virtual';

interface DataTableProps {
  data: Array<Record<string, any>>;
  columns: Column[];
  onRowClick?: (row: any) => void;
}

export const DataTable = memo<DataTableProps>(({ data, columns, onRowClick }) => {
  const parentRef = React.useRef<HTMLDivElement>(null);
  
  const rowVirtualizer = useVirtualizer({
    count: data.length,
    getScrollElement: () => parentRef.current,
    estimateSize: () => 50,
    overscan: 5,
  });

  const handleRowClick = useCallback((row: any) => {
    onRowClick?.(row);
  }, [onRowClick]);

  return (
    <div
      ref={parentRef}
      className="h-96 overflow-auto"
      role="table"
      aria-label="Data table"
    >
      {rowVirtualizer.getVirtualItems().map((virtualItem) => {
        const row = data[virtualItem.index];
        return (
          <div
            key={virtualItem.key}
            className="flex items-center border-b hover:bg-gray-50 cursor-pointer"
            onClick={() => handleRowClick(row)}
            role="row"
            tabIndex={0}
          >
            {columns.map((column) => (
              <div key={column.key} className="px-4 py-2 flex-1" role="cell">
                {row[column.key]}
              </div>
            ))}
          </div>
        );
      })}
    </div>
  );
});
```

## Workflow

### Step 1: Project Setup and Architecture
- Set up modern development environment with proper tooling
- Configure build optimization and performance monitoring
- Establish testing framework and CI/CD integration
- Create component architecture and design system foundation

### Step 2: Component Development
- Create reusable component library with proper TypeScript types
- Implement responsive design with mobile-first approach
- Build accessibility into components from the start
- Create comprehensive unit tests for all components

### Step 3: Performance Optimization
- Implement code splitting and lazy loading strategies
- Optimize images and assets for web delivery
- Monitor Core Web Vitals and optimize accordingly
- Set up performance budgets and monitoring

### Step 4: Testing and Quality Assurance
- Write comprehensive unit and integration tests
- Perform accessibility testing with real assistive technologies
- Test cross-browser compatibility and responsive behavior
- Implement end-to-end testing for critical user flows
