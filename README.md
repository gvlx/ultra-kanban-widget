# Ultra Kanban Widget

A configurable Kanban board widget for Grist, designed to turn a table into a drag-and-drop workflow board with support for custom lanes, WIP limits, sorting, card editing, and business rules.

This project is a single-file widget implementation built with HTML, CSS, and JavaScript, using Grist's plugin API and SortableJS for drag-and-drop interactions.

## Features

- Drag-and-drop cards between Kanban lanes
- Column/Lane mapping from a Grist table field
- Custom field visibility and ordering per lane
- WIP limits (visible and allowed counts) per lane
- Card sorting by multiple criteria
- Card and drawer editing support
- Support for reference and reference-list fields
- Multiple language bundles
- Visual customization for colors, backgrounds, shadows, and column sizing
- Rules engine for allowed movement, creation, and lane transfer actions
- Pagination within each lane

## Project structure

- `index.html` – widget layout, CSS, and UI shell
- `script.js` – Kanban logic, Grist integration, drag/drop, configuration handling, and rules engine
- `locales/` – translation files for different languages

## Requirements

- A Grist document and a table to use as the kanban source
- A field in that table representing the Kanban lane/status
- A web browser capable of loading custom Grist widgets

## How it works

The widget reads metadata from your Grist table, uses a selected field as the Kanban lane definition, and renders each distinct value as a column. Cards are displayed as rows from the table and can be moved between lanes using drag-and-drop.

Configuration is handled through the widget settings drawer, where you can:

- select the lane/status field
- set lane WIP limits
- choose which fields appear in cards and drawers
- define sort criteria
- set visual styles
- configure rules for lane constraints or automatic row creation

## Typical setup in Grist

1. Open a Grist document.
2. Add a custom widget (or load this widget in your Grist page).
3. Select the table containing the tasks/cards.
4. Configure the main Kanban field (for example, a `Status` choice column).
5. Customize lane display, card content, WIP rules, and styling in the widget settings.
6. Save configuration and start managing cards.

## Configuration notes

The widget stores configuration in Grist widget options and will reuse the selected settings across sessions.

Important settings include:

- `Kanban defining column`: the column used to generate lanes
- `Card sorting`: up to 3 sort criteria per lane
- `WIP limits`: max visible and max allowed counts
- `Restrictions`: adjacent-only movement if enabled
- `Visual`: background, widths, colors, card styles
- `Rules`: advanced lane behavior

## Localization

Translation bundles live under `locales/` as JSON files. The project includes multiple language packs and loads the active language at runtime.

## Development notes

This repo does not require a build step; it is a lightweight front-end widget intended to be embedded in Grist.

For local testing or debugging:

- open the widget within Grist,
- inspect the browser console,
- confirm the Grist plugin API is available,
- verify the lane field and table metadata are correctly mapped.

## License

This repository uses the AGPLv3 license. Read LICENSE for details.

## Contributing

If you want to improve the widget:

- keep behavior compatible with Grist's plugin API,
- maintain locale entries for any new UI strings,
- validate drag-and-drop flows and rule behavior after changes.

## Author

Roger Penna

## Repository

https://github.com/RogerPenna/ultra-kanban-widget
