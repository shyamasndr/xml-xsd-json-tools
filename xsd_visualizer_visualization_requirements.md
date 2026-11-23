# XSD Visualizer — Visualization-Only Requirements

**Product type:** Read-only XSD visualization and exploration tool  
**Reference:** Altova XMLSpy schema visualization  
**Scope:** Visualize, navigate, inspect, and understand XML Schema (XSD). No schema editing.

---

## 1. Product Vision

Create a modern, interactive visualizer that helps developers understand XSD schemas—from individual elements and types to large, multi-file schema projects.

The application is strictly **read-only**. Users can explore schema structure, relationships, namespaces, types, documentation, and source locations, but cannot modify schemas.

### Goals

- Make complex XSD structures easy to understand visually.
- Navigate elements, types, attributes, references, and dependencies.
- Clearly visualize content models and cardinality.
- Support multi-file schemas and namespaces.
- Provide responsive diagrams for large schemas.
- Help users inspect and analyze schema structure.

---

## 2. Main Visualization Views

### 2.1 Schema Overview

A high-level view of the schema's global components.

- Display global elements, complex types, simple types, attributes, groups, and attribute groups.
- Organize components by namespace and/or category.
- Show relationships between global components.
- Allow selecting a component to open its detailed view.
- Provide overview and focused views.
- Show schema/file boundaries when a project contains multiple files.

### 2.2 Element / Content Model Diagram

Visualize the structure of a selected element or complex type.

- Display nested child elements.
- Display attributes.
- Show element type references.
- Show element references (`ref`).
- Visualize `sequence`, `choice`, and `all` compositors.
- Show occurrence constraints (`minOccurs`, `maxOccurs`).
- Clearly indicate required, optional, repeating, and nillable elements.
- Show default and fixed values where applicable.
- Expand/collapse nested content.
- Navigate to referenced types and elements.
- Indicate recursive structures without infinitely expanding them.

### 2.3 Type Visualization

- Visualize complex types and simple types.
- Show base types and derivation.
- Show extension and restriction relationships.
- Show inherited elements and attributes.
- Show simple type restrictions and facets.
- Visualize enumerations.
- Display list and union types.
- Navigate between base and derived types.
- Show built-in XSD types when relevant.

### 2.4 Relationship Graph

A graph view for exploring how schema components are connected.

Relationships to visualize:

- Element → Type
- Element → Referenced element
- Type → Base type
- Type → Derived type
- Element → Substitution group
- Component → Referenced by
- Group → Members
- Attribute group → Members
- Schema → Imported schema
- Schema → Included schema

Graph interactions:

- Highlight incoming and outgoing relationships.
- Filter relationship categories.
- Select a node to inspect it.
- Navigate to connected components.
- Focus/isolate a selected component and its connections.
- Show relationship paths.
- Indicate recursive/circular relationships.
- Control graph depth.

### 2.5 Namespace Visualization

- List namespaces used in the project.
- Show components grouped by namespace.
- Visualize relationships between namespaces.
- Display namespace prefixes and URIs.
- Navigate to components within a namespace.
- Show namespace usage/distribution.

### 2.6 Schema Dependency View

For multi-file XSD projects:

- Visualize schema files as nodes.
- Show `xs:include` relationships.
- Show `xs:import` relationships.
- Show dependency direction.
- Display namespace and schema-location information.
- Highlight unresolved dependencies.
- Navigate from dependency nodes to files/components.
- Show dependency chains.

---

## 3. Diagram Components and Visual Semantics

### Components to represent

- Global elements
- Local elements
- Complex types
- Simple types
- Attributes
- Attribute groups
- Model groups
- Enumerations
- Wildcards (`xs:any`, `xs:anyAttribute`)
- Built-in types (when useful)

### Visual indicators

- Component category icons or colors.
- Required vs optional.
- Repeating elements.
- Nillable elements.
- Abstract components.
- References vs declarations.
- Global vs local components.
- Compositor type: sequence, choice, all.
- Cardinality labels (`1`, `0..1`, `1..*`, `0..*`).
- Type derivation / inheritance.
- Documentation indicator.
- Source file indicator.

### Diagram readability

- Configurable detail density.
- Labels that remain legible at different zoom levels.
- Tooltips with component summaries.
- Distinct visual styles for nodes and relationship types.
- Avoid clutter in large diagrams.

---

## 4. Navigation and Exploration

### Schema explorer tree

- Tree of schema files.
- Namespace grouping.
- Component grouping.
- Expand/collapse.
- Search/filter tree.
- Alphabetical or source-order display.
- Select tree item to focus diagram.
- Keep tree and diagram selection synchronized.

### Navigation features

- Breadcrumbs for current component path.
- Go to definition.
- Navigate to referenced type/element.
- Navigate to base type or derived type.
- Find references / usages.
- Back and forward navigation history.
- Jump between source and diagram.
- Center/focus selected component.
- Copy component name or qualified name (read-only utility).

---

## 5. Search and Filtering

- Search across all schema files.
- Search by component name.
- Search by element, type, attribute, group, or namespace.
- Search by documentation text.
- Search by datatype.
- Filter by component category.
- Filter by namespace.
- Filter by schema file.
- Filter global/local components.
- Filter by occurrence constraints.
- Filter by relationship type.
- Highlight search results in diagram.
- Navigate between results.
- Search result preview with component details.

Suggested shortcuts:

- `Ctrl+F` — Search current view/schema.
- `Ctrl+Shift+F` — Search all project files.
- `Ctrl+P` — Go to component.
- `F3` — Next result.

---

## 6. Component Details / Properties Panel

Selecting a component opens a read-only details panel.

### Element details

- Name
- Namespace
- Type
- Reference (`ref`)
- `minOccurs` / `maxOccurs`
- Nillable
- Abstract
- Default value
- Fixed value
- Form (`qualified` / `unqualified`)
- Substitution group
- Documentation
- Source file and line

### Attribute details

- Name
- Namespace
- Type
- Use (`optional`, `required`, `prohibited`)
- Default / fixed value
- Form
- Reference
- Documentation
- Source file and line

### Type details

- Name
- Namespace
- Base type
- Derivation method (`extension` / `restriction`)
- Child elements
- Attributes
- Facets and constraints
- Documentation
- Source file and line

### Group details

- Group name
- Group members
- Referencing components
- Source location
- Documentation

All properties are inspection-only.

---

## 7. Documentation and Annotations

- Display `xs:documentation`.
- Display `xs:annotation`.
- Documentation panel.
- Documentation on hover (short preview).
- Show component documentation alongside diagram.
- Markdown rendering if needed (sanitized).
- Navigate between documented components.
- Indicate components with/without documentation.

---

## 8. Read-Only XSD Source Viewer

- Syntax-highlighted XSD.
- Line numbers.
- XML formatting / pretty print (display-only; does not alter source file).
- Code folding.
- Tag matching.
- Find in source.
- Source location navigation.
- Click diagram component to highlight source declaration.
- Click source declaration to focus corresponding diagram component.
- Split view: diagram + source.
- Read-only mode only—no editing, saving, or source modification.

---

## 9. Schema Structure Analytics (Visualization Only)

Display informative counts and summaries.

### Metrics

- Total elements (global/local).
- Complex types.
- Simple types.
- Attributes.
- Groups and attribute groups.
- Namespace count.
- Schema file count.
- Import/include count.
- Maximum nesting depth.
- Recursive types.
- Component usage/reference counts.
- Documentation coverage.

### Visual summaries

- Component type distribution.
- Namespace distribution.
- Dependency graph.
- Most referenced components.
- Largest/most complex content models.
- Documentation coverage.
- Nesting depth visualization.
- Complexity hotspots.

Analytics are descriptive and read-only; do not offer editing, remediation, or schema transformation.

---

## 10. XSD Construct Coverage

The visualizer should accurately represent common XSD constructs and clearly indicate unsupported constructs.

### Core constructs

- `xs:element`
- `xs:attribute`
- `xs:complexType`
- `xs:simpleType`
- `xs:sequence`
- `xs:choice`
- `xs:all`
- `xs:group`
- `xs:attributeGroup`
- `xs:restriction`
- `xs:extension`
- `xs:list`
- `xs:union`
- `xs:enumeration`
- `xs:any`
- `xs:anyAttribute`
- Mixed content
- Simple content
- Complex content
- Substitution groups
- Abstract elements/types
- `block` and `final`
- Identity constraints: `xs:key`, `xs:keyref`, `xs:unique`
- Imports and includes
- Recursive structures

### Advanced constructs (progressive support)

- XSD 1.1 assertions
- Conditional type assignment
- XPath-based constraints
- `xs:redefine`
- Advanced wildcard namespace constraints

Unsupported features should be identified in the UI instead of being silently omitted or incorrectly drawn.

---

## 11. Multi-File and Project Handling

- Open one XSD or a collection of related XSDs.
- Resolve `xs:include` and `xs:import`.
- Namespace-aware resolution.
- Relative schema-location resolution.
- Display file dependencies.
- Show unresolved imports/includes.
- Show duplicate declarations where detectable.
- Reload files when they change externally.
- Tabs for open files.
- Recently opened schemas.
- Project-level overview.
- Optional XML catalog support (advanced).

The application must not change the files being visualized.

---

## 12. Diagram Interaction and Layout

- Zoom in/out.
- Pan.
- Fit to viewport.
- Center selected node.
- Mini-map for large graphs.
- Automatic layout.
- Tree/hierarchical layout.
- Horizontal and vertical layout.
- Radial layout (optional).
- Expand/collapse nodes.
- Control relationship depth.
- Focus selected component.
- Isolate selected component.
- Highlight related nodes.
- Hide/show relationship categories.
- Preserve user diagram view state during navigation.
- Reset layout/view.

Manual rearrangement may be supported for the user's temporary viewing arrangement, but it must not modify the XSD.

---

## 14. Performance Requirements

- Lazy-load large component trees.
- Virtualize navigation tree and search results.
- Render diagram nodes progressively.
- Collapse large branches initially.
- Parse schemas in the background.
- Efficient graph layout.
- Cache parsed schema models.
- Avoid rendering all nodes when not visible/needed.
- Support large, multi-file schemas.
- Handle deep nesting and recursive types safely.
- Keep UI responsive during parsing and layout.
- Show progress for long-running tasks.
- Allow cancellation of expensive visualization operations.

---

## 15. Security and Reliability

- Secure XML parsing.
- Disable unsafe external entity resolution (XXE protection).
- Restrict external resource resolution.
- Avoid unrestricted network access.
- Resource, file-size, and recursion limits.
- Safe handling of imported schemas.
- Sanitize documentation/annotation content before rendering.
- Clear errors for invalid schemas or unresolved references.
- Unsupported XSD features must be reported clearly.
- Parsing/visualization errors must not crash the application.

---

## 16. UI Layout

### Recommended main window

**Top toolbar**
- Open schema/project
- Search
- View selector
- Layout selector
- Zoom controls
- Fit-to-view
- Export

**Left panel — Explorer**
- Files
- Namespaces
- Components
- Search results

**Center — Visualization canvas**
- Schema diagram
- Relationship graph (alternate view)
- Dependency graph (alternate view)
- Pan/zoom
- Mini-map

**Right panel — Details**
- Properties
- Documentation
- References
- Type information
- Source location

**Optional bottom panel**
- Schema overview/statistics
- Read-only source viewer
- Informational diagnostics (parsing/resolution warnings)

### UX

- Resizable panels.
- Multiple tabs.
- Dark and light themes.
- Keyboard shortcuts.
- Context menus for navigation.
- Tooltips.
- Breadcrumbs.
- Workspace/view-state persistence.
- Full-screen visualization mode.
- Accessible keyboard navigation.

---

## 18. Explicitly Out of Scope

This product is a visualization and exploration tool, not an editor or schema development suite.

Do **not** include:

- XSD editing.
- Creating schema components.
- Deleting or modifying schema components.
- Drag-and-drop editing of schema structure.
- Saving schema changes.
- Schema comparison or diff.
- Version comparison.
- Breaking-change detection between versions.
- Refactoring or rename operations.
- Code generation.
- XML instance generation.
- Schema transformation or flattening.
- JSON Schema conversion.
- Automated remediation or quick-fix changes.
- Collaborative schema editing.

---

## 19. Architectural Principles

- Parse XSD into a canonical internal schema model.
- Keep schema semantics independent of visualization nodes.
- Represent relationships explicitly.
- Track source locations for components.
- Resolve namespaces and references consistently.
- Separate parsing, resolution, graph construction, layout, rendering, and export.
- Diagram state must never alter schema semantics or source files.
- Read-only source access.
- Preserve accurate representation of schema constructs.
- Report unsupported features rather than silently misrepresenting them.

---

## Product Summary

The XSD Visualizer is a **read-only schema exploration application**. Its core value is accurate, clear, and fast graphical understanding of XSD structure, content models, type relationships, namespaces, dependencies, and component details.

Prioritize visualization quality, navigation, relationship exploration, readability, and performance. Editing, comparison, generation, and transformation capabilities are intentionally excluded.
