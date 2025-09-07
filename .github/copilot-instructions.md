# KP Wealth & Family Office Website

**ALWAYS follow these instructions first and fallback to search or additional context gathering only when the information here is incomplete or found to be in error.**

The KP Wealth & Family Office website is a static HTML site deployed via GitHub Pages to the kpwafo.com domain. This is a simple, elegant website with no build process, no dependencies, and no test suite - it consists of pure HTML and CSS files.

## Repository Structure

This repository contains:
- `README.md` - Basic repository description
- `CNAME` - GitHub Pages domain configuration (kpwafo.com)
- `index (2).html` - Main HTML file (PROBLEMATIC: space in filename)
- `assets_styles.css` - CSS stylesheet

## Critical Issues to Fix

**ALWAYS address these structural issues when working on the site:**

1. **Broken CSS Link**: The HTML file references `assets/styles.css` but the actual file is `assets_styles.css`
2. **Problematic Filename**: `index (2).html` has a space which causes URL encoding issues
3. **Missing Directory Structure**: CSS should be in `assets/` directory for proper organization

## Local Development Workflow

### Start Local Development Server
```bash
cd /home/runner/work/kpwafo-site/kpwafo-site
python3 -m http.server 8080 --bind 127.0.0.1 &
```
- **Timing**: Server starts instantly (< 1 second)
- **NEVER CANCEL**: Let server run in background during development

### Test Website Functionality
```bash
# Test HTML loading (note URL encoding for space in filename)
curl -s 'http://127.0.0.1:8080/index%20(2).html' | head -5

# Test broken CSS link (will return 404)
curl -s -w "\nResponse: %{http_code}\n" 'http://127.0.0.1:8080/assets/styles.css'

# Test actual CSS file (will return 200)
curl -s -w "\nResponse: %{http_code}\n" 'http://127.0.0.1:8080/assets_styles.css'
```
- **Timing**: Each curl test completes in < 1 second
- **Expected Results**: HTML loads, CSS link returns 404, actual CSS file returns 200

### Visual Validation (Critical)
**ALWAYS perform visual validation after making changes:**

1. Navigate to `http://127.0.0.1:8080/index%20(2).html` in browser
2. Check if CSS is loading (styled vs unstyled appearance)
3. Verify navigation links are present (will return 404 as sections don't exist)
4. Confirm family crest image placeholder appears
5. Validate responsive layout on different screen sizes

**Expected Visual Results:**
- **Without CSS**: Plain HTML with blue underlined links, default fonts
- **With CSS**: Dark blue header with gold navigation, elegant typography, styled layout

### Stop Development Server
```bash
pkill -f "python3 -m http.server"
```

## Common Fix Workflows

### Fix CSS Link Issue
```bash
# Create properly named index file
cp 'index (2).html' index.html

# Fix CSS reference in the file
sed -i 's|assets/styles\.css|assets_styles.css|g' index.html

# Test the fix
python3 -m http.server 8080 &
curl -s 'http://127.0.0.1:8080/index.html' | grep "assets_styles.css"
```

### Proper Directory Structure Fix
```bash
# Create assets directory
mkdir -p assets

# Move CSS file to proper location
mv assets_styles.css assets/styles.css

# Update HTML reference
sed -i 's|assets_styles\.css|assets/styles.css|g' index.html
```

## Git Operations

### Check Repository Status
```bash
git --no-pager status
git --no-pager diff
```
- **Timing**: < 1 second each
- **NEVER CANCEL**: Git operations are instant for this small repository

### View File Changes
```bash
git --no-pager show HEAD -- "index (2).html"
git --no-pager log --oneline -5
```

## GitHub Pages Deployment

### Deployment Process
- **Automatic**: Changes pushed to main branch auto-deploy via GitHub Pages
- **Domain**: Site deploys to kpwafo.com (configured via CNAME file)
- **Timing**: Deployment typically completes within 1-2 minutes after push
- **Workflow**: Uses GitHub's automatic `pages-build-deployment` workflow

### Validate Deployment
```bash
# Check if CNAME file exists and contains correct domain
cat CNAME  # Should output: kpwafo.com

# Monitor deployment status via GitHub Actions (manual check in web interface)
```

## Validation Scenarios

**ALWAYS run these validation scenarios after making changes:**

### Scenario 1: CSS Styling Validation
1. Start local server: `python3 -m http.server 8080`
2. Navigate to the site in browser
3. **EXPECTED**: Dark blue header, gold navigation, elegant typography
4. **IF UNSTYLED**: CSS link is broken - check file paths and references

### Scenario 2: File Structure Validation
1. List all files: `find . -name "*.html" -o -name "*.css"`
2. **EXPECTED**: Find both HTML and CSS files
3. Check file references in HTML match actual file locations

### Scenario 3: Link Validation
1. Test all navigation links (they will return 404 as sections don't exist yet)
2. Verify image references (crest image is missing but placeholder should display)
3. **EXPECTED**: Navigation is functional even if destinations don't exist

### Scenario 4: Domain Configuration
1. Verify CNAME file: `cat CNAME`
2. **EXPECTED**: Contains exactly "kpwafo.com"
3. No trailing spaces or extra characters

## Common Commands Reference

### Repository Exploration
```bash
# Repository structure (instant)
ls -la

# Find all web files (< 1 second)
find . -name "*.html" -o -name "*.css" -o -name "*.js" -o -name "*.png"

# Check file sizes
du -h *.html *.css
```

### File Content Inspection
```bash
# View HTML structure
head -20 'index (2).html'

# Check CSS variables and styling
head -20 assets_styles.css

# Verify CNAME configuration
cat CNAME
```

### Development Server Management
```bash
# Start server (runs indefinitely until killed)
python3 -m http.server 8080 --bind 127.0.0.1 &

# Check if server is running
curl -s http://127.0.0.1:8080 | head -5

# Stop server when done
pkill -f "python3 -m http.server"
```

## Key Repository Information

### Current File Structure
```
.
├── .git/
├── .github/
│   └── copilot-instructions.md
├── CNAME
├── README.md
├── assets_styles.css
└── index (2).html
```

### File Details
- **Main HTML**: 1,424 bytes, contains complete site structure
- **CSS File**: 1,803 bytes, contains comprehensive styling with custom color scheme
- **CNAME**: 10 bytes, contains domain "kpwafo.com"
- **README**: 293 bytes, basic description

### GitHub Pages Configuration
- **Domain**: kpwafo.com
- **Source**: Deploy from root of main branch
- **Workflow**: Automatic deployment on push to main
- **SSL**: Enabled via GitHub Pages

## Troubleshooting

### CSS Not Loading
**Problem**: Website appears unstyled
**Diagnosis**: Check CSS file path in HTML
**Solution**: Ensure HTML references correct CSS filename and location

### File Not Found Errors
**Problem**: 404 errors when accessing files
**Diagnosis**: Check for spaces in filenames or incorrect paths
**Solution**: Use URL encoding for spaces or rename files properly

### Images Not Displaying
**Problem**: Family crest image shows placeholder
**Diagnosis**: Image file is missing from repository
**Solution**: Add `assets/crest.png` or update HTML to use available image

### Local Server Issues
**Problem**: Cannot access website locally
**Diagnosis**: Check if Python HTTP server is running
**Solution**: Start server with `python3 -m http.server 8080`

## Important Notes

- **NO BUILD PROCESS**: This is a static site - no compilation, bundling, or preprocessing
- **NO DEPENDENCIES**: No package.json, no npm install, no node_modules
- **NO TESTS**: Manual validation through visual inspection is the primary testing method
- **DEPLOYMENT**: Automatic via GitHub Pages on push to main branch
- **TIMING**: All operations are near-instant due to small repository size
- **MANUAL VALIDATION**: Always test visual appearance after changes

Always validate your changes by serving the site locally and checking both the unstyled (broken CSS) and styled (working CSS) versions to ensure proper functionality.