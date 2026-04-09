# Prospect Dashboard - GitHub Pages Deployment

A self-contained React dashboard for prospect intelligence and sales enablement, packaged as a single HTML file for GitHub Pages deployment.

## Files

- **index.html** (732 KB) - Complete self-contained application
  - Includes all React/ReactDOM/Babel from CDN
  - All 25 prospect accounts with complete data
  - All export functions (PDF, PowerPoint, Excel)
  - All UI components and sections
  - Responsive mobile-first design

- **manifest.json** - PWA manifest for app installation
  - Enables installation on mobile/desktop
  - Theme colors and app icons
  - Offline support configuration

- **sw.js** - Service Worker for offline functionality
  - Caches the app shell for offline access
  - Network-first strategy for assets
  - Automatic cache updates

## Deployment

### GitHub Pages

1. **Create repository** (or use existing):
   ```bash
   git init
   git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
   git branch -M main
   ```

2. **Add files**:
   ```bash
   git add index.html manifest.json sw.js
   git commit -m "Add Prospect Dashboard"
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to repository Settings > Pages
   - Source: Deploy from branch
   - Branch: main / root directory
   - Save

4. **Access app**:
   ```
   https://YOUR_USERNAME.github.io/REPO_NAME/
   ```

### Alternative: Deploy to any static host
- Netlify: Drag & drop the files
- Vercel: Connect GitHub repo
- AWS S3 + CloudFront
- Any web server with HTTPS

## Architecture

### React Setup
- **React 18** from CDN (production build)
- **Babel Standalone** for JSX compilation in browser
- **No build step required** - works directly in browser

### Mobile Responsive Design
- Full-screen mobile layout with hamburger menu
- 44px+ touch targets
- Notch-aware safe area padding
- Scrollable tab navigation
- Responsive grid layouts

### Export Capabilities
- **PDF**: Browser print dialog → Save as PDF
- **PowerPoint**: 7-slide deck via PptxGenJS
- **Excel**: 5-sheet workbook via SheetJS
- **HTML**: Formatted brief for printing

### Data Structure
All 25 accounts with complete fields:
- Executive Brief & Hypothesis
- Company Fundamentals & Business Model
- Strategic Priorities
- Workforce Intelligence
- Executive Mapping
- Business Challenges
- Outcome Framing
- Hyper-Cell Opportunity
- Geo-Political Context

## Features

### Prospect Management
- Account search and filtering
- Multi-section tabbed interface
- In-browser data editing
- Rich text content support

### Sections
1. Executive Brief - Snapshot and hypothesis
2. Fundamentals - Company core business
3. Revenue - Business model and segments
4. Strategy - CEO priorities and investments
5. Workforce - Team structure and hiring
6. Executives - Key stakeholder mapping
7. Problems - Pain identification
8. Use Cases - Workflow and opportunity
9. Challenges - Business challenges by severity
10. Outcomes - Impact framing and discovery
11. Hyper-Cell - Strategic opportunity
12. Geo-Politics - Regional context and signals

### Mobile Optimizations
- Collapsible sidebar drawer
- Top navigation bar with company name
- Horizontal scrollable tabs
- Touch-friendly button sizes
- Responsive card layouts

### PWA Features
- Install as app (mobile/desktop)
- Offline support via Service Worker
- App manifest with theme colors
- Custom app icons (SVG-based)

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+ (iOS 14+)
- All modern mobile browsers

## CDN Dependencies

All assets loaded from public CDNs (no build required):
- `react@18.2.0` - React library
- `react-dom@18.2.0` - React DOM rendering
- `babel-standalone@7.23.9` - JSX compilation
- `pptxgen@3.12.0` - PowerPoint export (loaded on demand)
- `xlsx@0.18.5` - Excel export (loaded on demand)

## File Size

- **index.html**: ~732 KB (minified, all data included)
- **manifest.json**: ~1.6 KB
- **sw.js**: ~1.9 KB

## Performance

- Single HTTP request for main app (index.html)
- Subsequent CDN loads cached by browser
- Service Worker caches entire app shell
- Lazy loads export libraries (PPTX/XLSX) on demand
- ~1s total load time on 3G connection

## Development

To modify the dashboard:

1. Update `index.html` directly (contains all JSX)
2. Modify account data in the `const pumaAccount = {...}` section
3. Modify component JSX within the `<script type="text/babel">` tag
4. No build step needed - just save and refresh

## License

Prospect Dashboard - Internal Use Only

## Support

For issues or questions, contact the sales enablement team.
