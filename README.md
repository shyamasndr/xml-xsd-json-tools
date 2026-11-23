# XSD Visualizer

XSD Visualizer is a browser-based, read-only tool for exploring XML Schema (XSD) files. It turns declarations and their relationships into navigable views, while keeping the files on your device. It is an early explorer, not a schema editor or validator.

## Get started

1. Open `XSDVisualizer.html` in a modern browser.
2. Choose **Open XSD files** to select one or more `.xsd` files, or **Open folder** to load a schema project while preserving its folder structure.
3. Browse the schema from the **Explorer**, or select a global declaration in **Overview**.
4. Select a component to inspect its properties, documentation, relationships, and source location in **Details**.

No server, installation, or build step is required.

## Features

- **Schema overview:** See counts for loaded files, components, global declarations, namespaces, and diagnostics. Browse global declarations grouped by component kind.
- **Explorer, search, and filters:** Browse declarations by file and kind. Search component names, kinds, namespaces, file paths, documentation, type names, and references; filter by component kind and global/local scope.
- **Expandable content models:** Explore elements, attributes, compositors (`sequence`, `choice`, and `all`), type references, and other recognized schema constructs. Occurrence ranges and selected declaration properties are shown in the diagram. Expand branches as needed and collapse them again.
- **Relationship graph:** Inspect incoming and outgoing component relationships, switch between the selected component and the whole project, filter by relationship kind, and find a path between two selected components. Unresolved references and built-in XSD types are identified.
- **Dependency graph:** View selected schema files and their resolved or unresolved `include` and `import` dependencies.
- **Namespace graph:** Explore namespaces and the cross-namespace references and imports connecting them; select a namespace to browse its global declarations.
- **Analytics:** Review declaration counts, dependency and reference counts, diagnostics, and component documentation coverage.
- **Source viewer:** Read syntax-highlighted XSD with line numbers. Selecting a declaration in the source opens its content model; selecting a component also reveals its source location.
- **Diagnostics:** Review parsing, dependency-resolution, duplicate-declaration, and reference warnings, with links to the relevant source where available.
- **Navigation and display controls:** Use back/forward component history, zoom, fit, center, graph layouts, a graph minimap, and a names-only content-model display.
- **SVG export:** Export the current relationship/dependency/namespace graph or selected content model as SVG.

## XSD coverage and limitations

The visualizer recognizes common declarations and constructs, including elements, attributes, simple and complex types, groups, attribute groups, compositors, derivation, facets, list and union types, wildcards, and identity-constraint declarations. It resolves selected-file references and local schema dependencies where possible.

This is not a full XSD implementation. In particular:

- It does not validate schemas or evaluate facets.
- Advanced XSD 1.1 constructs, `redefine`/`override`, chameleon includes, and identity-constraint semantics are not interpreted.
- Inherited content is not fully expanded, and some XSD semantics may not be represented. Check **Diagnostics** for warnings.
- External or absolute schema locations are not fetched. Select the required files (or their containing folder) to resolve local dependencies.
- Analytics are partial. Large relationship graphs are initially limited; use **Show more graph nodes and edges** to reveal more.
- Parsing is performed on the main thread; virtualization and cancellation are not available yet.

The loader accepts up to 250 selected files, with a 10 MB per-file limit and a 50 MB total project limit. Visualization is capped at 30,000 components. These limits help prevent excessive resource use in the browser.

## Read-only and local processing

The tool does not edit or save schema files, and it has no upload or network-fetch feature for schema dependencies. Selected XSD files are read in the browser. DTD and entity declarations are rejected; external schema locations are not loaded.

## Project files

- `XSDVisualizer.html` — the standalone application.
- `xsd_visualizer_visualization_requirements.md` — broader visualization requirements and product scope; some items in that document are planned rather than implemented.
