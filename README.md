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
