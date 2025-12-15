# Design Guidelines: AI-Driven Mine Management System

## Design Approach
**Design System Foundation**: Carbon Design System with influences from modern operational dashboards (Grafana, Datadog, Linear)
**Rationale**: Enterprise data-heavy application requiring clarity, scalability, and information density for mission-critical mining operations

## Core Design Principles
1. **Information Hierarchy**: Critical alerts and high-risk indicators must dominate visual attention
2. **Operational Clarity**: Every element serves a functional purpose - no decorative elements
3. **Scannable Density**: Dense information presented in organized, digestible chunks
4. **Status-Driven Design**: Visual system built around operational states (normal, warning, critical)

## Typography System

**Font Families**:
- Primary: Inter (via Google Fonts) - headings, UI labels, data tables
- Monospace: JetBrains Mono - numerical data, timestamps, asset IDs

**Hierarchy**:
- Page Titles: text-2xl font-semibold (24px)
- Section Headers: text-lg font-semibold (18px)
- Card Titles: text-base font-medium (16px)
- Body/Data: text-sm (14px)
- Captions/Metadata: text-xs (12px)
- Critical Alerts: text-lg font-bold

## Layout System

**Spacing Primitives**: Tailwind units of 2, 4, 6, 8 for consistency
- Component padding: p-4 or p-6
- Section gaps: gap-6 or gap-8
- Card spacing: space-y-4
- Table cell padding: px-4 py-3

**Grid Structure**:
- Dashboard cards: 12-column grid with responsive breakpoints
- Safety view: 2-column split (66% table/charts, 33% status cards)
- PdM view: Full-width table with expandable details
- Digital Twin: 75% map canvas, 25% detail panel (slide-in)

**Container Strategy**:
- Max-width: Full viewport with internal padding (px-6 lg:px-8)
- No centered containers - maximize screen real estate
- Fixed header: h-16 with shadow for depth separation

## Component Library

**Navigation**:
- Fixed top header with dark theme treatment
- Left sidebar (240px) with collapsible state for focused views
- Tab navigation within views using underline indicator style
- Breadcrumbs for deep navigation contexts

**Data Tables**:
- Zebra striping for row differentiation
- Sortable columns with arrow indicators
- Row hover state with subtle highlight
- Inline status badges (compact, pill-shaped)
- Sticky headers on scroll
- Action buttons on row hover (right-aligned)

**Cards & Panels**:
- Sharp corners (rounded-sm) for professional aesthetic
- Border-based separation, minimal shadows
- Card header with title and action area (filters, refresh icon)
- Compact card padding (p-4)
- Consistent card heights in grid layouts

**Status Indicators**:
- Color-coded risk levels:
  - Critical: Bold red treatment (text, borders, backgrounds)
  - Warning: Amber/orange for moderate risk
  - Normal: Green for safe operations
  - Info: Blue for neutral data
- Badge components: Small (px-2 py-0.5), uppercase text (text-xs), semibold
- Icon + text pattern for quick scanning

**Charts & Visualizations**:
- Use Chart.js or Recharts libraries
- Consistent axis styling and grid lines
- Legend placement: top-right or bottom
- Tooltip on hover with detailed metrics
- Time-series: Line charts with area fills for trends
- Distribution: Horizontal bar charts for equipment health scores

**Interactive Map/Schematic**:
- Grid-based or SVG overlay approach
- Zone boundaries with hover highlights
- Color-coded zones matching risk system
- Pin markers for equipment locations
- Click interaction opens detail panel (slide from right)

**Alert System**:
- Persistent notification bell (top-right header)
- Badge counter for unread alerts
- Dropdown panel: max-h-96 with scroll
- Alert cards: Severity icon, timestamp, description, action buttons
- Grouped by severity with visual separators

**Forms & Filters**:
- Compact form controls (h-9 inputs)
- Inline filter chips with remove X
- Dropdown selects with search capability
- Date range picker for time-based filtering
- Clear all filters button

**Buttons**:
- Primary: Solid fill for main actions
- Secondary: Outlined for secondary actions
- Ghost: Text-only for tertiary actions
- Icon buttons: Square (h-9 w-9) for toolbar actions
- Sizes: sm (h-8), md (h-9), lg (h-10)

## Responsive Strategy

**Breakpoints**:
- Desktop: 1280px+ (primary target)
- Tablet: 768px-1279px (functional, simplified grids)
- Mobile: Not prioritized per requirements

**Tablet Adaptations**:
- Stack 2-column layouts to single column
- Collapse sidebar to icons-only
- Tables: Horizontal scroll or card view toggle
- Reduce chart heights for fit

## Animations

**Minimal Motion Approach**:
- Data loading: Simple spinner (no skeleton screens)
- Panel transitions: 200ms ease slide-in/out
- Table sorting: Instant (no animation)
- Alerts: Subtle fade-in for new items (300ms)
- No decorative animations

## Images

**No Hero Images**: This is an operational dashboard - lead with data immediately

**Icon Strategy**:
- Use Heroicons (outline style) via CDN for UI icons
- Custom mine equipment icons: Use placeholder comments for specialized assets
- Status icons: Embedded in badge components (warning triangle, check circle, info circle)

## Accessibility Notes
- High contrast text for readability in control room environments
- Focus states on all interactive elements
- ARIA labels for icon-only buttons
- Keyboard navigation support for tables and filters
- Screen reader announcements for critical alerts

---

**Design Philosophy**: This system prioritizes **operational efficiency over aesthetics**. Every pixel serves the mine operators who rely on this data for safety-critical decisions. The design is intentionally utilitarian, dense, and focused on rapid information processing.