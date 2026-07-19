# Plan: Site Split & Logo Restoration

Split the long-scrolling `index.html` into two distinct pages to restore all brand logos while maintaining a clean, premium user experience.

## Objective
- **Re-organize** the site into two high-impact pages.
- **Restore** all original brand logos in the Accessories & Gear section.
- **Maintain** the "Electric Blue" dark mode aesthetic across both pages.

## Key Files
- `index.html`: Will now focus on the Hero, Bike Collection, and Contact/Location.
- `performance.html`: A new page for "Essential Kit" (Gear/Tech) and "Master Fit Center" (Fittings).

## Implementation Steps

### 1. Create `performance.html`
- Duplicate the structure of `index.html` (head, nav, footer, scripts).
- **Restore all original brand logos** in the "Essential Kit" section:
    - **Components**: Shimano, Campagnolo, SRAM.
    - **Wheels**: Roval, Enve, Princeton.
    - **Electronics**: Garmin, Wahoo.
    - **Apparel**: Q36.5, Endura.
    - **Nutrition**: Maurten, Honey Stinger, Tailwind.
    - **Saddles**: Specialized, JCOB, WTB, Selle Italia.
- Include the "Master Fit Center" section with the 5 certification blocks.
- Add a simplified Hero header for this page.

### 2. Update `index.html`
- **Remove** the "Essential Kit" and "Master Fit Center" sections to reduce "busyness".
- **Update Navigation** to link to the new `performance.html` page.

### 3. Navigation Synchronization
- **index.html nav**: Home, Bicycles, Gear & Fittings (link), Contact.
- **performance.html nav**: Home (link), Gear, Fittings, Contact (anchor to index.html#contact).

## Verification & Testing
- Verify all brand logos load correctly on the new page.
- Test cross-page navigation links (Home <-> Performance).
- Ensure mobile responsiveness on both pages.
- Verify anchor links (e.g., clicking "Contact" from the performance page takes you back to the home map).
