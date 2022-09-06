# Named Cascading Style Sheets
Recreated docs of Named Cascading Style Sheets. Originally made by RedaxMedia.

## Introduction
Named Cascading Style Sheets is a naming convention and guideline for semantic CSS.

### Why

Massive CSS used to be a nightmare while working on projects with different kinds of developers. The lack of conventions and guidelines are going to lead to a unmaintainable ball of mud.

### Goal

A predictable grammar for CSS that provides semantic information about the HTML template.

- What tags, components and sections are affected
- What is the relation of one class to another

## Class Basics

Named Cascading Style Sheets are divided into:

- Namespaces
- Structural Classes
- Component Classes
- Type Classes
- Modifier Classes
- Functional Classes
- Exceptions

### Namespaces
Pick a namespace once you provide your library to a third party or need to prevent naming conflicts inside your project.

#### Syntax

```
.{namespace}-{context}

.{namespace}-{type}
```

#### Overview
| Prefix       | Tag | Example   |
|--------------|-----|-----------|
| {namespace}- | *   | .foo-main |

### Structural Classes
Structural classes provide a semantic context for the underlying elements and are preferably utilized to define a layout.

#### Syntax
```
.{context}

.{context}-{name}
```

#### Overview
| Tag     | Example     |
|---------|-------------|
| article | .content    |
| body    | .body       |
| footer  | .footer     |
| header  | .header     |
| main    | .main       |
| nav     | .navigation |
| section | .section    |
| aside   | .sidebar    |

### Component Classes
Component classes provide a group context for the underlying elements and are preferably utilized to define a working unit.

#### Syntax
```
.component

.component-{name}

.component-{context}
```

#### Overview
| Prefix       | Tag | Example   |
|--------------|-----|-----------|
| component- | *   | .component-accordion |

### Type Classes
Type classes are the foundation for **reusable**, **modular** and **semantic** CSS to provide the reader what elements, tags and sections are affected.

#### Syntax
```
.{type}

.{type}-{name}

.{type}-{context}
```

#### Overview
| Prefix  | Tag                               | Example          |
|---------|-----------------------------------|------------------|
| address- | address                          | .address-content |
| audio-   | audio, object                    | .audio-content   |
| box-     | div                              | .box-content     |
| break-   | hr                               | .break-content   |
| button-  | a, button                        | .button-content  |
| caption- | caption                          | .capiton-content |
| code-    | code, pre                        | .code-content    |
| col-     | td, th                           | .col-content     |
| data-   | datalist                          | .data-content    |
| field-  | input, select, textarea           | .field-content   |
| form-   | form                              | .form-content    |
| frame-  | iframe                            | .frame-content   |
| image-  | canvas, img, object, picture, svg | .image-content   |
| item-   | dd, dt, li                        | .item-content    |
| label-  | label                             | .label-content   |
| link-     | a                               | .link-content     |
| list-     | dt, ol, ul                      | .list-content     |
| modal-    | div                             | .modal-content    |
| overlay-  | div                             | .overlay-content  |
| progress- | progress                        | .progress-content |
| quote-    | blockquote, citie               | .quote-content    |
| set-      | fieldset                        | .set-content      |
| shape-    | circle, path, rect, symbol, use | .shape-content    |
| legend- | legend                            | .legend-content  |
| table- | table                      | .table-content    |
| row-   | tr                         | .row-content      |
| text-  | em, small, span, strong, p | .text-content     |
| title- | h1, h2, h3, h4, h5, h6     | .title-content    |
| video- | object, video              | .progress-content |


### Modifier Classes
There is no limitation to extend your type classes with individual state, size and position modifier. Proper handling of context and type should prevent the need of adjoining classes.

#### Syntax
State related syntax:
```
.{type}-{state}

.{type}-{context}-{state}
```
Size related syntax:
```
.{type}-{size}

.{type}-{context}-{size}
```
Position related syntax:
```
.{type}-{position}

.{type}-{context}-{position}
```

#### Overview
| Suffix  | Tag | Example      |
|---------|-----|--------------|
| -active | *   | .item-active |
| -idle   | *   | .item-idle   |
| -hover  | *   | .item-hover  |
| -touch  | *   | .item-touch  |
| -small  | *   | .item-small  |
| -medium | *   | .item-medium |
| -large  | *   | .item-large  |
| -first  | *   | .item-first  |
| -second | *   | .item-second |
| -third  | *   | .item-third  |
| -last   | *   | .item-last   |
| -odd    | *   | .item-odd    |
| -even   | *   | .item-even   |

### Functional Classes
Functional classes using pure CSS are marked with the is, no, has and fn prefix. JavaScript enhanced and therefore reusable classes on the other hand can be identified by the js prefix. Each of them should never have styles for painting.

#### Syntax
Pure CSS related syntax:
```
.is-{state}

.has-{context}

.no-{feature}

.fn-{action}
```
JavaScript related syntax:
```
.js-{action}

.js-{context}
```

#### Overview
| Prefix | Tag | Example      |
|--------|-----|--------------|
| is-    | *   | .is-active   |
| has-   | *   | .has-tooltip |
| no-    | *   | .no-webgl    |
| fn-    | *   | .fn-clearfix |
| js-    | *   | .js-click    |

### Exceptions
There are exceptions that are not following the specifications.

#### Syntax
```
.wrapper

.wrapper-{name}

.wrapper-{context}

.wrapper-{component}

.wrapper-{type}
```

#### Overview
| Prefix | Tag | Example      |
|--------|-----|--------------|
| wrapper-| * | .wrapper-body

## Variables - Basics
A variables guideline based on the latest CSS4 specification and parts of the PostCSS ecosystem.

### Variable Colors

#### Colors
The color palette is a set of fixed hex values:
```css
:root {
	--color-primary: #ff3300;
	--color-secondary: #6600ff;
	--color-tertiary: #cc0033;
}
```
#### Abstracts

Abstract color variables contain a light or dark suffix extension:
```css
:root {
	--color-primary-light: color(var(--color-primary) l(70%));
	--color-primary-dark: color(var(--color-primary) l(30%));
}
```
### Variable Fonts
#### Fonts
```css
:root {
	--font-primary: arial, sans-serif;
	--font-code: monospace, arial, sans-serif;
	--font-icon: icon;
}
```
### Variable Queries
#### Queries

```css
@custom-media --media-small-max (max-width: 29.999em);
@custom-media --media-small-min (min-width: 30em);
@custom-media --media-medium-max (max-width: 49.999em);
@custom-media --media-medium-min (min-width: 50em);
@custom-media --media-large-max (max-width: 79.999em);
@custom-media --media-large-min (min-width: 80em);
@custom-media --media-retina (min-resolution: 192dpi);
```
