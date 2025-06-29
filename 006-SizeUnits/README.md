# CSS Size Units

## 1. Absolute Units (Fixed Size – Not Responsive)

| Unit | Meaning                | Example           | Use Case                     |
|------|------------------------|-------------------|------------------------------|
| `px` | Pixels                 | `width: 100px;`   | Common in screen layouts     |
| `pt` | Points (1/72 inch)     | `font-size: 12pt;`| Print stylesheets            |
| `cm` | Centimeters            | `width: 5cm;`     | Printed layouts              |
| `mm` | Millimeters            | `width: 30mm;`    | Printed layouts              |
| `in` | Inches                 | `width: 2in;`     | Print styles                 |
| `pc` | Picas (1pc = 12pt)     | `width: 2pc;`     | Rarely used                  |

<br>

- **Note:** Avoid using absolute units for web layouts — they're not responsive and behave inconsistently on different screens.


## 2. Relative Units (Responsive)

### 2.1 Relative to Font Size or Parent

| Unit  | Relative To                 | Example            | Use Case                                  |
|-------|-----------------------------|--------------------|-------------------------------------------|
| `%`   | Size of parent element      | `width: 50%;`      | Flexible layouts, grid columns            |
| `em`  | Font-size of current element| `padding: 2em;`    | Padding/margin based on font              |
| `rem` | Root (`html`) font-size     | `font-size: 1.25rem;` | Consistent typography                  |
| `ch`  | Width of character `0`      | `width: 60ch;`     | Text limits in forms or articles          |
| `ex`  | x-height of font            | `height: 1ex;`     | Rare; vertical alignment                  |

- **Note:** In most browsers, `1rem = 16px` by default.

### 2.2 Relative to Viewport Size

| Unit   | Relative To                         | Example           | Use Case                                |
|--------|-------------------------------------|-------------------|-----------------------------------------|
| `vw`   | 1% of viewport width                | `width: 100vw;`   | Full-width sections, responsive layout  |
| `vh`   | 1% of viewport height               | `height: 100vh;`  | Hero sections, modals                   |
| `vmin` | 1% of smaller dimension (vw or vh)  | `width: 50vmin;`  | Uniform scaling                         |
| `vmax` | 1% of larger dimension (vw or vh)   | `width: 50vmax;`  | Fullscreen flexible UI                  |

---

## When to Use Which Unit?

| Goal                          | Best Unit(s)     |
|-------------------------------|------------------|
| Fixed size elements           | `px`             |
| Typography (scalable)         | `rem`            |
| Element spacing               | `em`, `rem`      |
| Responsive layout containers  | `%`, `vw`, `vh`  |
| Input or code line widths     | `ch`             |
| Print media                   | `pt`, `cm`, `in` |

---

## Common Conversion (If `1rem = 16px`)

| Unit       | Pixels Equivalent |
|------------|-------------------|
| `1rem`     | 16px              |
| `0.5rem`   | 8px               |
| `2em`      | 32px (if base is 16px) |
| `100vh`    | Full viewport height |
| `100vw`    | Full viewport width  |

---

## Best Practices

- Use `rem` for global font sizes and spacing.
- Use `%`, `vw`, `vh` for responsive layouts.
- Use `em` when spacing should scale with font size.
- Avoid `px` for text if accessibility matters.

---
