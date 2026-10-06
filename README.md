# Universal UI Lab

Universal UI Lab is a single-file, framework-friendly CSS and UI design collection that brings together modern responsive design techniques, gradient systems, motion, progressive enhancement, and browser-side data demos in one place.

The project is designed as a practical laboratory for experimenting with multiple frontend technologies without requiring a build step.

## ✨ Highlights

- **Single-file UI showcase** powered by `index.html`
- Embedded **universal reset CSS** for a neutral, responsive foundation
- Responsive layouts for desktop, tablet, and mobile screens
- Modern typography using fluid `clamp()` sizing
- Flexible layout primitives using Grid and Flexbox
- Multiple gradient types:
  - Linear gradients
  - Radial gradients
  - Conic gradients
  - Repeating linear gradients
  - Repeating radial gradients
  - Repeating conic gradients
  - Multi-layer gradients
  - Gradient text
  - Gradient borders
  - OKLab gradients
  - LCH gradients
  - Long-hue gradients
- Accessibility-oriented defaults
- `prefers-reduced-motion` support
- Safe-area and dynamic viewport support
- Print-friendly styles
- Framework interoperability experiments
- Browser-side SQLite demonstration with `sql.js`
- Interactive examples using Alpine.js, Hyperscript, and HTMX
- PHP-related demonstration content using php.js

## 🧩 Technologies

Universal UI Lab intentionally combines several frontend technologies in one experimental environment.

| Technology | Purpose |
|---|---|
| Universal Reset CSS | Provides the neutral base style and responsive normalization |
| EaseMotion CSS | Motion and animation-oriented styling experiments |
| Tailwind CSS | Utility-first CSS experiments |
| Bootstrap | Component and grid interoperability examples |
| HTMX | Hypermedia-driven interaction examples |
| Alpine.js | Lightweight reactive UI behavior |
| Hyperscript | Declarative client-side interactions |
| php.js | Browser-side PHP-related experimentation |
| sql.js | SQLite running in the browser through WebAssembly |
| HTML5 | Semantic document structure |
| Modern CSS | Responsive layouts, gradients, accessibility, and visual effects |

## 📁 Project Structure

Universal UI Lab intentionally keeps the initial project structure simple:

```text
Universal UI Lab/
├── index.html
└── README.md
```

The universal reset CSS is embedded directly inside `index.html`, so the showcase can be opened as a standalone HTML document.

A future expanded structure may look like:

```text
Universal UI Lab/
├── index.html
├── README.md
├── assets/
│   ├── images/
│   ├── icons/
│   └── fonts/
├── css/
│   └── components.css
├── js/
│   ├── app.js
│   ├── alpine.js
│   ├── htmx.js
│   └── sql.js
└── docs/
    └── examples/
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd "Universal UI Lab"
```

### 2. Open the showcase

Because the initial implementation is a single HTML file, you can open it directly:

```bash
open index.html
```

On Linux:

```bash
xdg-open index.html
```

On Windows:

```powershell
start index.html
```

### 3. Optional: run a local HTTP server

Some browser APIs and CDN-loaded modules behave more reliably over HTTP than through `file://`.

Using Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

## 🎨 Design System

The embedded reset and design primitives establish a small, neutral foundation before framework-specific styles are applied.

### Responsive Container

```html
<div class="ur-container">
  <h1>Universal UI Lab</h1>
</div>
```

The container uses fluid sizing with `min()`, viewport-relative dimensions, and responsive breakpoints.

### Responsive Grid

```html
<div class="ur-responsive-grid">
  <article>Card A</article>
  <article>Card B</article>
  <article>Card C</article>
</div>
```

The grid uses:

```css
grid-template-columns:
  repeat(
    auto-fit,
    minmax(
      min(100%, 16rem),
      1fr
    )
  );
```

This allows the layout to adapt automatically without requiring a large number of breakpoint-specific rules.

### Fluid Typography

```html
<h1 class="ur-fluid-heading">
  Responsive Heading
</h1>
```

The design system uses CSS `clamp()` to scale typography smoothly across viewport sizes.

## 🌈 Gradient System

Universal UI Lab is designed to demonstrate a broad range of modern CSS gradient techniques.

### Linear Gradient

```css
background-image:
  linear-gradient(
    135deg,
    #7c3aed,
    #2563eb,
    #06b6d4
  );
```

### Radial Gradient

```css
background-image:
  radial-gradient(
    circle at center,
    #7c3aed,
    #2563eb,
    #06b6d4
  );
```

### Conic Gradient

```css
background-image:
  conic-gradient(
    from 0deg,
    #7c3aed,
    #2563eb,
    #06b6d4,
    #22c55e,
    #f59e0b,
    #ef4444,
    #7c3aed
  );
```

### Repeating Gradients

The showcase includes:

```css
repeating-linear-gradient(...)
repeating-radial-gradient(...)
repeating-conic-gradient(...)
```

### Multi-layer Gradient

Multiple background layers can be combined:

```css
background-image:
  radial-gradient(
    circle at 20% 20%,
    rgb(255 255 255 / 0.18),
    transparent 35%
  ),
  radial-gradient(
    circle at 80% 30%,
    rgb(255 255 255 / 0.12),
    transparent 40%
  ),
  linear-gradient(
    135deg,
    #7c3aed,
    #2563eb,
    #06b6d4
  );
```

### Gradient Text

```css
background-image:
  linear-gradient(
    90deg,
    #7c3aed,
    #2563eb,
    #06b6d4
  );

background-clip: text;
-webkit-background-clip: text;

color: transparent;
-webkit-text-fill-color: transparent;
```

### Gradient Border

The project also demonstrates the transparent-border + background-layer technique:

```css
border: 2px solid transparent;

background:
  linear-gradient(Canvas, Canvas) padding-box,
  linear-gradient(135deg, #7c3aed, #06b6d4) border-box;

background-clip:
  padding-box,
  border-box;
```

### Modern Color Spaces

Where supported by the browser, the showcase also demonstrates gradients using:

- `oklab`
- `lch`
- longer hue interpolation

These examples are progressively enhanced with `@supports`.

## 🧱 Framework Interoperability

Universal UI Lab is intentionally designed as a compatibility experiment rather than a replacement for a framework's own base styles.

### Tailwind CSS

Tailwind's utility-first approach can be combined with the neutral reset and the showcase components.

Example:

```html
<div class="rounded-2xl p-6 shadow-xl">
  <h2 class="text-2xl font-bold">
    Tailwind Component
  </h2>
</div>
```

### Bootstrap

Bootstrap components can coexist with the universal reset approach.

Example:

```html
<div class="container">
  <div class="row g-4">
    <div class="col-md-6">
      <div class="card">
        <div class="card-body">
          Bootstrap Card
        </div>
      </div>
    </div>
  </div>
</div>
```

### EaseMotion CSS

EaseMotion CSS is included as an animation-oriented layer for experimenting with motion and transitions.

The reset avoids aggressively overriding framework-specific class names, making it easier to place animation styles on top of the neutral base.

### HTMX

HTMX can be used for server-driven HTML updates and progressive enhancement.

Example:

```html
<button
  hx-get="/example"
  hx-target="#result"
  hx-swap="innerHTML"
>
  Load Content
</button>

<div id="result"></div>
```

### Alpine.js

Alpine.js provides lightweight state and interaction behavior directly in HTML.

Example:

```html
<div x-data="{ open: false }">
  <button @click="open = !open">
    Toggle
  </button>

  <div x-show="open">
    Content
  </div>
</div>
```

### Hyperscript

Hyperscript allows declarative interaction logic.

Example:

```html
<button
  _="on click toggle .is-active on me"
>
  Toggle State
</button>
```

### sql.js

The project includes a browser-side SQLite demonstration using `sql.js`.

A minimal concept looks like:

```javascript
const SQL = await initSqlJs({
  locateFile: file =>
    `https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.14.2/${file}`
});

const db = new SQL.Database();

db.run(`
  CREATE TABLE demo (
    id INTEGER PRIMARY KEY,
    name TEXT
  );
`);

db.run(`
  INSERT INTO demo (name)
  VALUES ('Universal UI Lab');
`);
```

This demonstrates that SQLite queries can run completely within the browser through WebAssembly.

### php.js

php.js is represented as an experimental PHP-in-JavaScript area.

The project treats this as a demonstration technology rather than a production PHP runtime.

## ♿ Accessibility

The reset is designed with accessibility in mind.

Included considerations:

- Visible `:focus-visible` outlines
- Reduced motion support
- Semantic HTML defaults
- Keyboard-friendly interactive elements
- Responsive text sizing
- Form control normalization
- `prefers-reduced-motion`
- Print-friendly behavior
- Preserved native semantics
- Better text wrapping for long content

Reduced motion support:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

## 📱 Responsive Design

The project uses modern CSS capabilities rather than relying exclusively on fixed breakpoints.

Key techniques include:

```css
clamp()
min()
max()
minmax()
auto-fit
aspect-ratio
100dvh
env(safe-area-inset-*)
```

The design adapts to:

- Mobile phones
- Tablets
- Laptops
- Desktop monitors
- Large displays
- Devices with display cutouts and safe-area constraints

## 🧪 Design Sections

The showcase is organized around practical design-system experiments such as:

1. Hero and introduction
2. Typography
3. Responsive containers
4. Gradient gallery
5. Cards
6. Buttons
7. Alerts
8. Forms
9. Tables
10. Modal dialogs
11. Accordions
12. Progress indicators
13. Tabs
14. Framework interaction examples
15. Browser-side SQLite demonstration
16. PHP-related browser demo
17. Accessibility and responsive behavior

## 🛠 Customization

The reset exposes CSS custom properties under the `--ur-*` namespace.

For example:

```css
:root {
  --ur-gradient-stop-1: #7c3aed;
  --ur-gradient-stop-2: #2563eb;
  --ur-gradient-stop-3: #06b6d4;

  --ur-duration-fast: 150ms;
  --ur-duration-normal: 250ms;
  --ur-duration-slow: 400ms;
}
```

You can customize the visual system without rewriting every component.

### Change the primary gradient

```css
:root {
  --ur-gradient-stop-1: #ff0080;
  --ur-gradient-stop-2: #7928ca;
  --ur-gradient-stop-3: #2afadf;
}
```

### Change the container width

```css
:root {
  --ur-container-inline:
    min(100% - 2rem, 96rem);
}
```

## ⚠️ Compatibility Notes

Universal UI Lab is intentionally broad, but no single reset can guarantee identical rendering across every CSS framework.

Tailwind CSS, Bootstrap, EaseMotion CSS, and other libraries may define their own:

- CSS resets
- Preflight rules
- Reboot rules
- Utility classes
- Component styles
- Specificity rules
- JavaScript behavior
- Design tokens

For this reason, the embedded reset uses low-specificity selectors such as `:where()` and avoids unnecessary `!important` declarations.

The main exception is the accessibility-critical reduced-motion behavior and the standard hidden attribute normalization.

When combining frameworks, load order still matters.

A common approach is:

```text
Browser defaults
        ↓
Universal UI Lab reset
        ↓
Framework base styles
        ↓
Framework utilities/components
        ↓
Project-specific overrides
```

Alternatively, when using Tailwind's generated base layer, the reset can be moved into an appropriate Tailwind `@layer` depending on the project architecture.

## 🌐 External Resources

The showcase relies on CDN-hosted libraries in the single-file prototype.

Typical resources include:

- Tailwind CSS
- Bootstrap
- HTMX
- Alpine.js
- Hyperscript
- EaseMotion CSS
- php.js
- sql.js

For production deployments, consider pinning exact versions and using a build pipeline or self-hosted assets when reproducibility, security, or offline operation is important.

## 🔐 Security Considerations

Universal UI Lab is a frontend laboratory and should not be treated as a secure backend architecture.

Important considerations:

- Do not execute arbitrary PHP source supplied by users.
- Do not trust arbitrary SQL input in production applications.
- Validate all server-side data.
- Use a Content Security Policy appropriate for your deployment.
- Pin dependency versions.
- Review third-party CDN integrity and availability.
- Use HTTPS in deployed environments.
- Avoid exposing secrets in client-side JavaScript.

The php.js and sql.js sections are intended for controlled demonstrations.

## 📦 Production Recommendations

For a production application, consider separating the prototype into dedicated files:

```text
src/
├── css/
│   ├── reset.css
│   ├── tokens.css
│   ├── components.css
│   └── utilities.css
├── js/
│   ├── app.js
│   ├── interactions.js
│   └── database.js
└── index.html
```

A build system can then provide:

- Dependency version control
- Minification
- Tree-shaking
- CSS optimization
- Asset hashing
- Type checking
- Testing
- Continuous integration

## 📄 License

The Universal UI Lab project code can be licensed according to the needs of the repository owner.

Third-party libraries remain subject to their respective licenses and terms.

When publishing the repository, keep the individual licenses and attribution requirements of all included third-party technologies.

## 🤝 Contributing

Contributions are welcome.

Useful contribution areas include:

- New responsive components
- New gradient techniques
- Accessibility improvements
- Framework compatibility tests
- Additional Alpine.js examples
- Additional HTMX examples
- Additional Hyperscript patterns
- SQL.js examples
- Performance improvements
- Documentation improvements

Please keep new examples focused, accessible, responsive, and easy to understand.

## 🗺 Roadmap

Potential future improvements include:

- Component search and filtering
- Live CSS editor
- Live HTML editor
- Copy-to-clipboard code examples
- Theme builder
- Light/dark/system theme switching
- Design token editor
- Color palette generator
- Gradient generator
- Animation playground
- Responsive device preview
- Component export
- Accessibility inspection tools
- CSS framework comparison mode
- Offline/PWA support
- Automated visual regression testing

## 📜 Project Philosophy

Universal UI Lab is not intended to prove that one framework is better than another.

Instead, the project explores how multiple frontend approaches can coexist:

```text
Semantic HTML
      +
Universal Reset
      +
Modern CSS
      +
Tailwind CSS
      +
Bootstrap
      +
EaseMotion CSS
      +
HTMX
      +
Alpine.js
      +
Hyperscript
      +
php.js
      +
sql.js
      =
Universal UI Lab
```

The goal is experimentation, interoperability, education, and rapid prototyping.

---

**Universal UI Lab** — A practical playground for modern responsive UI, CSS systems, gradients, motion, progressive enhancement, and browser-side application techniques.
