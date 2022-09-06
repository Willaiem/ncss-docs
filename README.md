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

## Units
### Unit Basics

A units guideline based on working in 0.125 steps, a magic number like π in the world of CSS.
### Why

Nested HTML elements with relative units are going to lead to odd PX values.
### Goal

A simplified management for spaces and dimensions of HTML elements.

### Unit Steps
#### Overview
| Factor | Value |
|--------|-------|
| 1      | 0.125 |
| 2      | 0.25  |
| 3      | 0.375 |
| 4      | 0.5   |
| 5      | 0.625 |
| 6      | 0.75  |
| 7      | 0.875 |
| 8      | 1     |

## Examples
### Example Basics
Different examples based on the NCSS convention.

### Example Layout
#### HTML
```html
<!-- header -->

<header id="header" class="foo-header"> 
	<h1 class="foo-title-header">Website</h1>
</header>

<!-- main -->

<main class="foo-main foo-wrapper">

	<!-- content -->

	<article id="content" class="foo-content">
		<h2 class="foo-title-content">Headline</h2>
		<div class="foo-box-content">Box</div>
	</article>

	<!-- sidebar -->

	<aside id="sidebar" class="foo-sidebar">
		<h3 class="foo-title-sidebar">Headline</h3>
		<p class="foo-text-sidebar">Text</p>
	</aside>

</main>

<!-- footer -->

<footer id="footer" class="foo-footer">
	<div class="foo-box-footer">Powered by NCSS</div>
</footer>
```
#### CSS
```css
/**
 * @tableofcontents
 *
 * 1. layout
 */

/** @section 1. layout */

.foo-main {
}

.foo-content {
}

.foo-sidebar {
}
```
### Example Menu
#### HTML
```html
<!-- status -->

<input id="status-menu" class="foo-fn-status-menu" type="checkbox">

<div class="foo-has-menu">

	<!-- logic -->

	<label class="foo-fn-toggle-menu foo-label-toggle-menu" for="status-menu"></label>
	<label class="foo-fn-close-menu foo-label-close-menu" for="status-menu"></label>

	<!-- list -->

	<ul class="foo-fn-menu foo-list-menu">
		<li>Item</li>
	</ul>

</div>
```
#### CSS
```css
/**
 * @tableofcontents
 *
 * 1. logic
 * 2. list
 */

/** @section 1. logic */

.foo-fn-status-menu,
.foo-fn-status-menu:not(:checked) + .foo-has-menu .foo-fn-menu,
.foo-fn-status-menu:not(:checked) + .foo-has-menu .foo-fn-close-menu {
	display: none;
}

/** @section 2. list */

.foo-list-menu {
}
```
### Example Form
#### HTML
```html
<form class="foo-form-default foo-form-login">

	<!-- legend -->

	<legend class="foo-legend-default"></legend>

	<!-- list -->

	<ul>
		<li>
			<label class="foo-label-default" for="user">User</label>
			<input id="user" class="foo-field-default foo-field-text" name="user" />
		</li>
		<li>
			<label class="foo-label-default" for="password">Password</label>
			<input id="password" class="foo-field-default foo-field-password" type="password" name="password" />
		</li>
	</ul>

	<!-- button -->

	<button class="foo-button-default foo-button-submit" type="submit" name="submit">Submit</button>
	<button class="foo-button-default foo-button-reset" type="reset" name="reset">Reset</button>
</form>
```
#### CSS
```css
/**
 * @tableofcontents
 *
 * 1. form
 */

/** @section 1. form */

.foo-form-default {
}

.foo-field-default {
}

.foo-button-default {
}
```
