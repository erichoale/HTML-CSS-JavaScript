# HTML-CSS-JavaScript

Here’s a clear, high‑level breakdown of how building a web app from scratch (HTML/CSS/JavaScript) differs from building one with Esri’s Experience Builder. Since you already work with both worlds, I’ll frame this in a way that highlights the real differences in control, complexity, and responsibility.

How They Differ: Custom Code vs. Experience Builder
1. Level of Control
Custom HTML/CSS/JavaScript
You control everything: layout, styling, logic, data requests, UI behavior.

You decide how the map loads, how layers behave, how widgets interact.

You can build features that don’t exist in any Esri widget.

Experience Builder
You work within a structured framework.

Layout, widgets, and interactions are predefined.

You can configure deeply, but you don’t control the underlying code unless you build a Developer Edition custom widget.

Summary:  
Custom code = total freedom.
Experience Builder = structured, guided freedom.

2. Development Effort
Custom HTML/CSS/JavaScript
You must:

Write all UI components

Handle responsive design

Manage API calls to ArcGIS services

Build logic for pop-ups, filters, queries, etc.

Handle errors, performance, caching, accessibility

Experience Builder
You:

Drag and drop widgets

Configure data sources

Set interactions (triggers/actions)

Style with built‑in tools

Publish instantly

Summary:  
Custom code = high effort, high flexibility.
Experience Builder = low effort, fast deployment.

3. Required Skill Level
Custom Code
Strong JavaScript knowledge

Understanding of ArcGIS Maps SDK for JavaScript

HTML/CSS layout and responsive design

API authentication, hosting, and deployment

Experience Builder
GIS knowledge

Understanding of data relationships

Widget configuration

Basic logic (triggers, actions, views)

Summary:  
Custom code requires software engineering skills.
Experience Builder requires GIS + configuration skills.

4. Performance & Optimization
Custom Code
You optimize:

Layer loading

API calls

Rendering performance

Lazy loading

Caching strategies

Experience Builder
Esri handles most optimization.

You optimize mainly through:

scale dependencies

data structure

widget configuration

Summary:  
Custom code = you own performance.
Experience Builder = Esri handles the heavy lifting.

5. Hosting & Deployment
Custom Code
You must:

Host files on a server

Manage updates

Handle versioning

Ensure HTTPS, CORS, authentication

Experience Builder
Hosted automatically in ArcGIS Online or Enterprise

Publishing is one click

Versioning and hosting are handled for you

Summary:  
Custom code = you manage infrastructure.
Experience Builder = Esri manages it.

6. Customization Potential
Custom Code
Unlimited customization

Build any UI or workflow

Integrate non‑Esri libraries (React, Vue, D3, Leaflet, etc.)

Build custom tools not possible in Experience Builder

Experience Builder
Limited to available widgets unless using Developer Edition

Custom widgets require React + Esri’s framework

Great for standard GIS workflows, less ideal for unique apps

Summary:  
Custom code = infinite possibilities.
Experience Builder = powerful but bounded.

When Each Approach Makes Sense
Use Custom HTML/CSS/JavaScript when:
You need a unique workflow or UI

You want full control over performance

You’re integrating multiple APIs or libraries

You’re building a long‑term, scalable application

Use Experience Builder when:
You need something fast

You want a polished UI without coding

You’re building dashboards, viewers, or internal tools

You want easy maintenance and hosting

The Practical Difference (GIS Perspective)
Experience Builder is a GIS‑first app builder.  
Custom JavaScript is a software‑first approach that includes GIS.

Experience Builder gives you:

Speed

Consistency

Low maintenance

Easy sharing

Custom code gives you:

Power

Flexibility

Custom workflows

Deep integration

Great — let’s go deeper and compare Experience Builder to building with the ArcGIS Maps SDK for JavaScript (formerly the JS API). This is where the real architectural differences show up, especially for someone like you who already understands GIS workflows and public‑sector app needs.

Below is a structured breakdown that highlights how the two approaches differ under the hood and what that means for development, performance, and long‑term maintainability.

1. Architecture & Framework
ArcGIS Maps SDK for JavaScript (Custom Code)
You build the entire app structure yourself.

You choose the framework (or none):

Vanilla JS

React

Vue

Angular

Svelte

You import Esri modules directly (e.g., Map, MapView, FeatureLayer).

You control the lifecycle of the map, widgets, events, and DOM.

Think of it as:  
A blank canvas with a powerful paint set.

Experience Builder
Built on React + Esri’s internal framework.

You don’t manage the map lifecycle — Experience Builder does.

Widgets communicate through a message/action system.

Layout is controlled by a drag‑and‑drop UI, not code.

Think of it as:  
A structured studio where the tools are pre‑arranged for you.

2. Data Handling & Integration
Custom JavaScript
You manually:

Connect to feature services, map services, image services.

Handle authentication (OAuth, API keys).

Write queries, filtering, and event listeners.

Manage state (selected features, filters, UI state).

This gives you:

Full control over performance.

Ability to integrate non‑Esri data sources easily (REST APIs, CSVs, Firebase, etc.).

Experience Builder
Data sources are configured through the UI.

Widgets automatically share data through the framework.

Querying, filtering, and selection are handled by widgets or triggers.

This gives you:

Faster setup.

Less flexibility for custom data logic.

3. UI & Interaction Model
Custom JavaScript
You build:

Buttons

Panels

Modals

Custom widgets

Animations

Responsive layouts

You decide:

How the user interacts with the map

How selections propagate

How tools appear/disappear

Experience Builder
You use:

Prebuilt widgets (Map, Table, List, Filter, Query, Chart)

Prebuilt layouts (Row, Column, Grid)

Prebuilt interactions (Zoom to, Filter, Select, Show/Hide)

You configure:

Triggers (e.g., “When feature is selected…”)

Actions (e.g., “…filter this list”)

Experience Builder is opinionated — it guides you toward a certain style of GIS app.

4. Customization & Extensibility
Custom JavaScript
Unlimited customization.

You can build tools that don’t exist anywhere in Esri’s ecosystem.

You can integrate:

D3 visualizations

Chart.js

Custom geoprocessing workflows

External APIs (weather, traffic, elections, etc.)

Custom authentication flows

Experience Builder
Out‑of‑the‑box widgets are limited.

Developer Edition allows custom widgets, but:

Must be written in React

Must follow Esri’s widget lifecycle

Must integrate with the Experience Builder data model

Custom widgets in Experience Builder are powerful but require more overhead than writing a standalone JS app.

5. Performance & Optimization
Custom JavaScript
You control:

Layer loading strategy

Renderer complexity

Feature reduction

Lazy loading

Worker threads

Caching

You can squeeze out every bit of performance.

Experience Builder
Performance is good but less tunable.

You rely on:

Esri’s optimizations

Widget efficiency

Data source configuration

Large datasets or many widgets can slow the app.

6. Deployment & Maintenance
Custom JavaScript
You must:

Host the app (S3, Azure, on‑prem, etc.)

Manage updates

Handle versioning

Maintain dependencies

Ensure security patches

Experience Builder
Hosted automatically in AGOL or Enterprise.

Publishing is one click.

Versioning and hosting are handled for you.

Maintenance is minimal.

7. When Each Approach Is Best
Use Custom JavaScript when you need:
A unique workflow or UI

High performance with large datasets

Integration with external APIs

Custom geoprocessing or automation

A long‑term, scalable application

Use Experience Builder when you need:
A fast, polished GIS app

Dashboards, viewers, or internal tools

Easy maintenance

Consistent Esri‑style UI

No custom code (or minimal code)

The Bottom Line
Experience Builder is a GIS‑centric app builder.  
Custom JavaScript is a full software development approach that includes GIS.

Experience Builder:

Faster

Easier

Less flexible

Custom JavaScript:

More work

More power

More freedom

Absolutely — here’s the deeper architectural comparison you asked for. This is the part most GIS developers never get explained clearly: how Experience Builder’s widget lifecycle differs from the ArcGIS Maps SDK for JavaScript’s view lifecycle, and why that difference matters when you’re building apps.

I’ll keep this clean, structured, and practical so you can immediately apply it in your work.

1. The Core Difference in Philosophy
ArcGIS Maps SDK for JavaScript
You control the map lifecycle directly.

You create the map

You create the view

You attach widgets

You manage events

You destroy or rebuild components manually

You own the entire lifecycle.

Experience Builder
You control widgets, not the map.

The map is created by the framework

The view is managed by the framework

Widgets subscribe to data and events

Widgets communicate through messages

The framework handles cleanup

Experience Builder owns the lifecycle; you plug into it.

2. How the Map Loads (The Big Architectural Shift)
ArcGIS JS API
You explicitly write:

js
const map = new Map({...});
const view = new MapView({
  container: "viewDiv",
  map: map
});
You know exactly:

When the map loads

When the view is ready

When layers finish drawing

You can hook into events like:

js
view.when(() => {...});
layer.when(() => {...});
view.on("click", (event) => {...});
Experience Builder
You never create the map or view.

Instead:

The Map widget creates the view

Other widgets listen for map events

You interact through the message system

Example:
A List widget listens for “feature selection” messages from the Map widget.

You don’t write:

js
view.on("click")
You configure:

Trigger: “When user selects a feature”

Action: “Filter this list”

3. Widget Lifecycle vs. View Lifecycle
ArcGIS JS API View Lifecycle
You manage:

Initialization  
Create map, view, layers, UI.

Rendering  
Layers draw, events fire.

Interaction  
Clicks, selections, popups, queries.

Destruction  
Remove event listeners, destroy view.

You’re responsible for:

Memory leaks

Event cleanup

Re-rendering logic

State management

Experience Builder Widget Lifecycle
Each widget has:

onInit()  
Widget is created.

onDataSourceCreated()  
Data becomes available.

onActiveViewChanged()  
Map view changes.

onReceiveMessage()  
Widget receives a message (selection, extent change, etc.).

onDestroy()  
Cleanup.

The framework handles:

View creation

Event listeners

Rendering

Cleanup

You only handle:

Widget-specific logic

How your widget responds to messages

UI rendering (React)

4. Event Handling: Direct vs. Indirect
ArcGIS JS API
You directly attach events:

js
view.on("pointer-move", handler);
view.on("click", handler);
layer.on("layerview-create", handler);
You have full control.

Experience Builder
You never attach events to the view.

Instead:

The Map widget listens to events

It broadcasts messages

Other widgets subscribe to those messages

Example messages:

ExtentChanged

SelectionChanged

DataRecordSetChange

MapClick

Your widget receives:

js
onReceiveMessage(message) {
  if (message.type === 'MAP_CLICK') {
    // handle it
  }
}
This is a reactive architecture, not imperative.

5. State Management
ArcGIS JS API
You manage state manually:

Selected features

Filters

UI state

Layer visibility

Custom variables

You can use:

Global variables

Reactive frameworks (React/Vue)

Custom stores

Experience Builder
State is centralized:

Data sources

Widget state

App state

Widgets don’t store their own data; they subscribe to shared data sources.

This makes:

Cross-widget communication easier

Custom logic more constrained

6. Custom Widgets vs. Custom JS Apps
Custom JS App
You build everything:

UI

Map

Logic

Events

State

Layout

You can integrate:

D3

Chart.js

External APIs

Custom geoprocessing

Anything you want

Experience Builder Custom Widget
You build:

A React component

That plugs into the Experience Builder framework

And responds to messages

You must follow:

Esri’s widget lifecycle

Esri’s data model

Esri’s React conventions

It’s powerful, but more constrained than a standalone JS app.

7. Why This Difference Matters in Real Projects
ArcGIS JS API
Best when you need:

Custom workflows

High performance

Deep integration with external systems

Full UI control

Unique tools not available in Esri widgets

Experience Builder
Best when you need:

Fast deployment

Consistent UI

Easy maintenance

Standard GIS workflows

Non-developers to maintain the app

In One Sentence
ArcGIS JS API = You build the app and control the map.
Experience Builder = The framework builds the app and you build widgets that react to it.
