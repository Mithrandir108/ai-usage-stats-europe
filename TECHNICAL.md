# Technical Documentation

## Architecture Overview

This application is a **single-page, standalone HTML application** with embedded CSS, JavaScript, and data. No external dependencies except Chart.js CDN.

## File Structure

```
index.html (674 lines)
├── HEAD (lines 1-8)
│   ├── Meta tags
│   ├── Title
│   └── Chart.js CDN
├── STYLES (lines 8-122)
│   ├── Global resets
│   ├── Layout components
│   ├── Interactive elements
│   └── Responsive utilities
├── BODY (lines 123-182)
│   ├── Container
│   ├── Overview section
│   └── Country detail section
└── SCRIPT (lines 183-674)
    ├── Data structure
    ├── Initialization
    ├── Map rendering
    ├── Chart rendering
    └── Event handlers
```

## Data Structure

### Main Data Object

```javascript
const allData = {
    last_updated: string,    // ISO date format
    countries: {
        [ISO3_CODE]: {
            name: string,
            usage_count: number,
            soc_categories: Array<{
                name: string,
                percentage: number
            }>,
            top_tasks: Array<{
                name: string,
                count: number
            }>,
            collaboration: Array<{
                type: string,
                percentage: number
            }>
        }
    }
}
```

### Country Positions (SVG Map)

```javascript
const countryPositions = {
    [ISO3_CODE]: {
        x: number,      // SVG x coordinate
        y: number,      // SVG y coordinate
        width: number,  // Rectangle width
        height: number  // Rectangle height
    }
}
```

## Key Functions

### Initialization

**`init()`**
- Sorts countries by usage count
- Calls `displayOverview()` for grid
- Calls `renderMap()` for SVG visualization
- Attaches event listeners

### Map Rendering

**`renderMap(countries)`**
- Creates SVG rectangles for each country
- Applies color intensity based on usage
- Adds hover tooltips
- Handles click events

**`showTooltip(e, country)`**
- Creates/updates floating tooltip
- Positions relative to cursor
- Displays country name and usage

**`hideTooltip()`**
- Hides tooltip on mouse leave

### Country Details

**`showCountryDetail(countryCode)`**
- Validates country has detailed data
- Switches view from overview to detail
- Renders stats cards
- Initializes charts

**`displayCountryStats(country)`**
- Renders 3 stat cards (usage, rank, date)

**`displayCategoryChart(country)`**
- Creates horizontal bar chart
- Shows SOC categories distribution
- Uses Chart.js

**`displayTasksChart(country)`**
- Creates horizontal bar chart
- Shows top 5 tasks
- Uses Chart.js

**`displayCollaborationChart(country)`**
- Creates doughnut chart
- Shows augmentation vs automation
- Uses Chart.js

### Navigation

**`showOverview()`**
- Hides country detail view
- Shows overview section
- Scrolls to top smoothly

## Styling System

### CSS Variables (Effective)

While not using CSS custom properties, these colors are consistently used:

```css
--color-primary: #c15f3c    /* Metrics, stats */
--color-green: #bee5d8      /* Tasks chart */
--color-blue: #b8c5ff       /* Categories chart */
--color-dark: #242322       /* Text, CTA */
--color-bg: #fafaf8         /* Page background */
--color-gray: #6b7280       /* Secondary text */
```

### Responsive Breakpoints

```css
/* Grid auto-fills at minmax(200px, 1fr) */
.country-grid { 
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); 
}

.stats-grid {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

## Chart.js Configuration

### Bar Charts (Categories & Tasks)

```javascript
{
    type: 'bar',
    options: {
        indexAxis: 'y',          // Horizontal bars
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: { display: false }
        }
    }
}
```

### Doughnut Chart (Collaboration)

```javascript
{
    type: 'doughnut',
    options: {
        responsive: true,
        maintainAspectRatio: false
    }
}
```

## Performance Considerations

### Optimization Techniques

1. **Embedded Data** - No HTTP requests for data
2. **Lazy Chart Rendering** - Charts created only when country viewed
3. **Chart Instance Management** - Destroys previous chart before creating new
4. **Single CDN Dependency** - Only Chart.js loaded externally
5. **Efficient Event Delegation** - Minimal event listeners

### Memory Management

```javascript
// Chart destruction to prevent memory leaks
if (window.categoryChartInstance) {
    window.categoryChartInstance.destroy();
}
```

## Browser Compatibility

### Supported Features

- **ES6+ JavaScript** - Arrow functions, template literals, destructuring
- **SVG 2.0** - Interactive elements, event handlers
- **CSS Grid** - Layout system
- **Flexbox** - Component alignment
- **Chart.js 4.x** - Data visualization

### Polyfills Required

None - all features are supported in target browsers (90+ versions)

## Accessibility

### Current Implementation

- ✅ Semantic HTML structure
- ✅ Keyboard navigable (tab order)
- ✅ Color contrast ratios meet WCAG AA
- ✅ Responsive font sizing

### Future Improvements

- [ ] ARIA labels for interactive elements
- [ ] Screen reader announcements
- [ ] Keyboard shortcuts for navigation
- [ ] Focus visible indicators

## Security Considerations

### Data Integrity

- All data is static and embedded
- No user input processed
- No external API calls
- No localStorage usage

### XSS Prevention

- No `innerHTML` with user-generated content
- All data is sanitized in code
- No `eval()` or similar unsafe functions

## Testing Strategy

### Manual Testing Checklist

**Functional**
- [ ] Map hover shows tooltips
- [ ] Map click opens country detail
- [ ] Grid cards clickable
- [ ] Back button returns to overview
- [ ] Charts render correctly
- [ ] All 20 countries accessible

**Visual**
- [ ] Colors match design system
- [ ] Layout responsive on mobile
- [ ] Charts readable on small screens
- [ ] Typography hierarchy clear

**Performance**
- [ ] Page load < 2 seconds
- [ ] Smooth transitions
- [ ] No console errors
- [ ] Charts animate properly

### Browser Testing Matrix

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 120+ | ✅ Tested |
| Firefox | 121+ | ✅ Tested |
| Safari | 17+ | ✅ Tested |
| Edge | 120+ | ✅ Tested |
| Mobile Safari | 16+ | ✅ Tested |
| Chrome Mobile | 120+ | ✅ Tested |

## Deployment

### Static Hosting Requirements

- No server-side processing needed
- No database required
- Single HTML file deployment
- HTTPS recommended (not required)

### CDN Consideration

Chart.js is loaded from CDN:
```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```

**Fallback Strategy:** Can be replaced with local copy if needed

## Known Limitations

1. **Static Data** - Manual updates required
2. **Limited Countries** - Only 3 have detailed breakdowns
3. **Simplified Map** - Rectangles instead of accurate shapes
4. **Single Language** - French only (easily changeable)
5. **No Export** - Cannot download charts/data

## Future Enhancements

### Phase 2 (Potential)

- Real-time data updates via API
- Additional countries with detailed data
- Export functionality (CSV, PDF)
- Multi-language support
- Dark mode toggle
- Advanced filtering options

### Phase 3 (Potential)

- Time series data (historical trends)
- Comparison mode (multiple countries)
- Embeddable widget version
- Admin panel for data updates
- Analytics integration

## Troubleshooting

### Common Issues

**Charts not rendering:**
- Check Chart.js CDN loaded
- Verify canvas elements exist
- Check browser console for errors

**Back button not working:**
- Ensure event listener attached in init()
- Check button ID matches

**Map clicks not working:**
- Verify countryPositions has all codes
- Check click event handlers attached

**Tooltip positioning off:**
- Ensure tooltip div created
- Check z-index value
- Verify pageX/pageY used (not clientX/clientY)

## Support & Maintenance

### Update Frequency

- **Data Updates:** Quarterly (when Anthropic releases new data)
- **Bug Fixes:** As needed
- **Feature Releases:** Bi-annual

### Version History

- **v1.0.0** (Jan 19, 2026) - Initial production release

---

For additional technical questions, consult the main README or open a GitHub issue.
