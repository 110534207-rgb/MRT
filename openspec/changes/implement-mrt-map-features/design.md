# Design: MRT Map Page Architecture

The implementation will adhere to the existing architecture of the project as described in `doc/SA.md`. No new technologies or frameworks will be introduced.

## Key Architectural Decisions

1.  **Self-Contained Static Pages**: Each MRT line will be a single, self-contained `.html` file. All necessary CSS and JavaScript will be embedded within the HTML file. This simplifies deployment, as no build process is required.

2.  **Embedded Data**: Station and attraction data will be stored directly within a JavaScript function (`getDefaultStations`) inside each HTML file. This avoids the need for external databases or API calls, keeping the application entirely client-side.

3.  **In-Memory State**: All user-initiated changes (like adding or deleting attractions in admin mode) will only affect the data in the browser's memory. The state is intentionally non-persistent and will reset upon page reload, as specified in the requirements. This is a core constraint of the current design.
