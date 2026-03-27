CLAUDE.md — Frontend Website Rules
1. Always Do First
* Always invoke the frontend-design skill before writing any frontend code.
* This must be done every session, with no exceptions.

Reference Design Rules
If a Reference Image Is Provided
* Match the layout, spacing, typography, and colors exactly.
* Replace real content with placeholders:
    * Images: https://placehold.co/
    * Text: generic placeholder copy.
* Do not improve or modify the design.
Verification Process
1. Screenshot your implementation.
2. Compare against the reference image.
3. Fix mismatches.
4. Screenshot again.
5. Perform at least two comparison rounds.
Stop only when:
* No visible differences remain, or
* The user tells you to stop.

If No Reference Image Is Provided
Design from scratch with high craftsmanship, following the Anti-Generic Guardrails.

Local Development Server
Required Rules
* Always serve pages from localhost.
* Never screenshot from a file:/// URL.
Start the Dev Server
node serve.mjs
Server details:
* Serves project root
* URL: http://localhost:3000
Rules:
* serve.mjs is located in the project root
* Start the server before taking screenshots
* If the server is already running, do not start another instance

Screenshot Workflow
Environment
* Puppeteer location:
C:/Users/nateh/AppData/Local/Temp/puppeteer-test/
* Chrome cache:
C:/Users/nateh/.cache/puppeteer/

Take Screenshot
Always screenshot from localhost:
node screenshot.mjs http://localhost:3000
Screenshots are saved to:
./temporary_screenshots/screenshot-N.png
Rules:
* Files auto-increment
* Screenshots are never overwritten

Optional Label
node screenshot.mjs http://localhost:3000 label
Output example:
screenshot-N-label.png

Screenshot Analysis
After taking the screenshot:
1. Read the PNG fromtemporary_screenshots/
2. Analyze the image directly.
When comparing against reference, evaluate:
* Spacing and padding
* Font size
* Font weight
* Line height
* Exact hex colors
* Alignment
* Border radius
* Shadows
* Image sizing
* Layout spacing
Example feedback format:
* “Heading is 32px, but reference shows ~24px”
* “Card gap is 16px, but should be 24px”

Output Defaults
Unless the user specifies otherwise:
File Structure
* Output a single index.html file
* All styles inline
CSS Framework
Use Tailwind via CDN:
<script src="https://cdn.tailwindcss.com"></script>

Placeholder Images
https://placehold.co/WIDTHxHEIGHT
Example:
https://placehold.co/600x400

Responsive Design
* Always mobile-first

Brand Assets
Before designing:
1. Check the folder:
brand_assets/
Possible contents:
* Logos
* Color palettes
* Style guides
* Images
Rules
* If assets exist → use them
* Do not use placeholders if real assets exist
* If a logo exists → use it
* If colors are defined → use exact values
Never invent new brand colors when a palette exists.

Anti-Generic Design Guardrails
Colors
* Never use the default Tailwind palette:
    * indigo-500
    * blue-600
* Always define a custom brand color system.

Shadows
Do not use:
shadow-md
Instead:
* Use layered shadows
* Slight color tint
* Low opacity

Typography
Never use the same font for headings and body.
Recommended pairing:
* Display or Serif font → headings
* Clean Sans-Serif → body text
Typography rules:
* Large headings:tracking: -0.03em
* Body text:line-height: 1.7

Gradients
Use layered gradients:
* Multiple radial gradients
* Add grain texture using SVG noise filters

Animations
Only animate:
* transform
* opacity
Never use:
transition-all
Use spring-style easing.

Interactive States
Every clickable element must include:
* Hover state
* Focus-visible state
* Active state
No exceptions.

Images
Apply visual treatments:
* Gradient overlay:
bg-gradient-to-t from-black/60
* Color treatment layer:
mix-blend-multiply

Spacing
Use intentional spacing tokens.
Do not randomly use Tailwind spacing increments.
Spacing must feel systematic and consistent.

Depth System
All surfaces must follow a layered system:
Base → Elevated → Floating
Avoid designs where everything sits on the same visual layer.

Hard Rules
Never do the following:
* Add sections not present in the reference design
* Improve or reinterpret the reference design
* Stop after only one screenshot comparison
* Use transition-all
* Use default Tailwind blue or indigo as the primary color

