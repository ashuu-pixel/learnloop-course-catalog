# LearnLoop Responsive Course Catalog
## Responsive Design Comparison

| Design Aspect | Mobile (<600px) | Tablet (600–1023px) | Desktop (≥1024px) |
|---|---|---|---|
| **Grid columns** | 1 column | 2 columns | 3–4 columns |
| **Grid technique** | CSS Grid with `minmax()` | CSS Grid with `auto-fit` and `minmax()` | CSS Grid with `auto-fit` and `minmax()` |
| **Filter bar** | Stacked vertically for easy tapping | Horizontal layout with controls arranged across the row | Full horizontal filter bar with visible Sort dropdown |
| **Course card width** | Full available width | Flexible two-column cards | Flexible three-to-four-column cards |
| **Image treatment** | 16:9 aspect ratio, full card width | Same 16:9 aspect ratio | Same 16:9 aspect ratio |
| **Responsive images** | Uses `srcset` and `sizes` so the browser can choose an appropriate image | Uses `srcset` and `sizes` | Uses `srcset` and `sizes` |
| **Headline size** | Smaller but fluid using `clamp()` | Medium fluid size | Larger fluid size using `clamp()` |
| **Price size** | Compact fluid size | Medium fluid size | Larger fluid size |
| **Spacing** | Reduced spacing to fit smaller screens | Moderate spacing | More generous spacing |
| **Navigation** | Simplified/hidden to avoid crowding | Reduced spacing | Full navigation and Explore Courses button |
| **Why this works** | Keeps the interface readable and touch-friendly without horizontal scrolling. | Uses available screen width efficiently while keeping cards easy to scan. | Takes advantage of larger screens by displaying more courses at once without making cards too narrow. |

## Design Rationale

### Mobile
The mobile layout uses one course card per row because narrow screens do not provide enough space for multiple cards without reducing readability. The filter controls are stacked vertically so they remain easy to use on touch screens.

### Tablet
The tablet layout changes to two columns because the screen provides more horizontal space. The filter controls remain more compact and horizontal while still allowing the Sort control to use its own row when needed.

### Desktop
Desktop screens use three to four flexible columns. CSS Grid with `repeat(auto-fit, minmax(...))` allows the number of columns to adapt naturally to the available width.

### Images
All course images maintain a consistent **16:9 aspect ratio** using CSS `aspect-ratio`. The HTML also uses `srcset` and `sizes` so the browser can select an appropriate image size for the current screen.

### Typography
Headings and prices use CSS `clamp()` instead of relying only on fixed breakpoint sizes. This allows typography to scale smoothly between small and large screens.

### Overall Approach
The layout is designed to adapt to the available space rather than simply changing at fixed breakpoints. This reduces overflow, keeps the cards readable, and provides a consistent experience across mobile, tablet, and desktop screens.