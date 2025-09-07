# GitHub Copilot Instructions for KP Wealth & Family Office Website

## Project Overview

This repository hosts the digital governance and legacy platform for KP Wealth & Family Office. It is a sophisticated, private family office website focused on:

- **Privacy & Confidentiality**: All content should maintain the highest standards of discretion
- **Legacy Preservation**: Supporting generational wealth management and heritage
- **Elegant Design**: Sophisticated, timeless aesthetic befitting a family office
- **Security**: Private family archival use with restricted access

## Technical Stack

- **Static Website**: Pure HTML, CSS, and minimal JavaScript
- **Hosting**: GitHub Pages with custom domain
- **Styling**: Custom CSS with sophisticated color palette and typography
- **Structure**: Single-page application with planned multi-section architecture

## Design System & Branding

### Color Palette
```css
--navy: #1a2235     /* Primary dark color */
--charcoal: #282828 /* Text color */
--ivory: #f6f3ee    /* Background */
--gold: #b8a165     /* Accent color */
```

### Typography
- **Serif**: 'Merriweather', 'Georgia', serif (for headings and formal content)
- **Sans-serif**: 'Montserrat', 'Helvetica Neue', Arial, sans-serif (for body text)

### Design Principles
1. **Elegance over flashiness**: Clean, refined, understated luxury
2. **Readability**: Clear hierarchy and generous whitespace
3. **Timelessness**: Avoid trendy elements that may date quickly
4. **Professional confidence**: Convey trust, stability, and expertise

## Current File Structure

```
/
├── index (2).html          # Main landing page (needs rename to index.html)
├── assets_styles.css       # Main stylesheet (needs move to assets/styles.css)
├── CNAME                   # GitHub Pages custom domain
├── README.md               # Project documentation
└── .github/
    └── copilot-instructions.md  # This file
```

## Planned File Structure

```
/
├── index.html              # Main landing page (corrected name)
├── sections/               # Individual content sections
│   ├── charter.html       # Family Office Charter
│   ├── trusts.html        # Trust Architecture
│   ├── governance.html    # Wealth Governance
│   ├── legacy.html        # Legacy & Heritage
│   └── vault.html         # Vault Access
├── assets/                # Static assets directory
│   ├── styles.css         # Main stylesheet (corrected path)
│   ├── crest.png          # Family crest image
│   └── images/            # Additional images
├── CNAME                   # GitHub Pages custom domain
├── README.md              # Project documentation
└── .github/
    └── copilot-instructions.md  # Copilot guidance
```

## File Naming Issues to Address

1. **`index (2).html`** → Should be renamed to `index.html`
2. **`assets_styles.css`** → Should be moved to `assets/styles.css`
3. **Missing `assets/` directory** → Should be created for better organization
4. **CSS path in HTML** → Currently references `assets/styles.css` but file is `assets_styles.css`

## Coding Standards

### HTML
- Use semantic HTML5 elements
- Maintain clean, indented structure
- Include appropriate meta tags for SEO and security
- Ensure accessibility with proper ARIA labels where needed
- Use descriptive alt text for images, especially the family crest

### CSS
- Use CSS custom properties (variables) defined in `:root`
- Follow BEM methodology for class naming when applicable
- Maintain consistent spacing and typography scales
- Ensure responsive design for mobile/tablet viewing
- Use elegant transitions and subtle animations

### JavaScript (when needed)
- Keep to minimum - prefer CSS solutions
- Use modern ES6+ syntax
- Focus on progressive enhancement
- Ensure graceful degradation for older browsers

## Content Guidelines

### Tone & Voice
- **Formal but approachable**: Professional without being cold
- **Confident**: Convey expertise and reliability
- **Discreet**: Maintain confidentiality and privacy
- **Legacy-focused**: Emphasize generational thinking

### Content Types
1. **Family Office Charter**: Governance principles and values
2. **Trust Architecture**: Wealth structuring information
3. **Wealth Governance**: Management and oversight processes
4. **Legacy & Heritage**: Historical and cultural preservation
5. **Vault Access**: Secure document and asset management

## Security & Privacy Considerations

- **No personal information**: Avoid specific names, amounts, or sensitive details
- **Private repository**: Ensure all development happens in private repos
- **Access controls**: Implement appropriate authentication for sensitive sections
- **HTTPS only**: All connections must be secure
- **Minimal tracking**: Avoid unnecessary analytics or third-party scripts

## Development Workflow

1. **Test locally**: Always test changes in a local environment first
2. **Incremental updates**: Make small, focused changes
3. **Backup considerations**: Ensure important content is backed up
4. **Review process**: Consider implementing code review for significant changes

## Accessibility Requirements

- WCAG 2.1 AA compliance minimum
- Proper heading hierarchy (h1 → h2 → h3)
- Sufficient color contrast ratios
- Keyboard navigation support
- Screen reader compatibility

## Performance Guidelines

- Optimize images for web (consider WebP format)
- Minimize CSS and JavaScript
- Use efficient fonts (consider font-display: swap)
- Keep page load times under 3 seconds
- Implement proper caching headers

## Future Enhancements

When suggesting improvements, consider:
- **Document management system**: Secure file sharing capabilities
- **Member portal**: Authentication and personalized content
- **Mobile app**: Companion iOS/Android application
- **Integration capabilities**: Connection with wealth management platforms
- **Advanced security**: Two-factor authentication, encryption

## Common Tasks

When working on this project, you might be asked to:
- Create new section pages following the established design system
- Implement responsive layouts for various devices
- Add subtle animations or transitions
- Optimize performance and loading times
- Enhance accessibility features
- Implement basic form functionality (contact, secure messaging)

## Immediate Improvements Needed

1. **File Organization**:
   - Rename `index (2).html` to `index.html`
   - Create `assets/` directory
   - Move `assets_styles.css` to `assets/styles.css`
   - Update HTML file references accordingly

2. **Missing Assets**:
   - Add family crest image (`assets/crest.png`)
   - Create placeholder images for future sections

3. **Responsive Design**:
   - Add viewport meta tag (already present)
   - Implement mobile-responsive navigation
   - Test on various device sizes

4. **Content Development**:
   - Create individual section pages referenced in navigation
   - Develop content following privacy guidelines
   - Implement proper internal linking

## Notes for AI Assistance

- Always maintain the sophisticated, professional tone
- Respect the privacy-focused nature of the content
- Suggest improvements that align with family office standards
- Consider long-term maintainability and scalability
- Focus on user experience that conveys trust and competence
- When making changes, follow the planned file structure
- Prioritize the immediate improvements listed above when relevant