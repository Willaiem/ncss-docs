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

### Syntax
```
.component

.component-{name}

.component-{context}
```

### Overview
| Prefix       | Tag | Example   |
|--------------|-----|-----------|
| component- | *   | .component-accordion |
