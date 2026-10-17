# Software architecture and synchronization

## Components

The implemented application uses Flutter/Dart and the **Model–View–ViewModel (MVVM)** architectural pattern. The thesis also describes **Provider** in the non-functional requirements, a local **SQLite** database for offline records, and **HTTP POST + JSON** as the connection mechanism with the ThingsBoard platform.

```mermaid
flowchart TD
    A[Field operator] --> UI[Mobile screens / Flutter View]
    UI <--> VM[ViewModel / presentation logic]
    VM <--> MODEL[Models and data-handling logic]
    MODEL <--> SQLITE[(SQLite local database)]
    MODEL --> Q[Pending synchronization items]
    Q --> POST[HTTP POST with JSON payload]
    POST --> TB[ThingsBoard IoT platform]
    TB --> DASH[Charts and historical data tables]
    POST -. On failure, keep record pending .-> SQLITE
```

*Conceptual summary from thesis Sections 2.2.4–2.2.5 and 3.2.1–3.2.4; not a source-code diagram.*

## Offline-first workflow

1. Choose the crop: cucumber, tomato, or bell pepper.
2. Display crop-specific input fields and validate their types and required values.
3. Associate the observation with the device's collection date.
4. Persist the record in SQLite with a pending synchronization state.
5. Keep the record accessible for local browsing and editing while offline.
6. When synchronization is initiated and connectivity is available, submit pending records over HTTP/JSON to ThingsBoard.
7. Record the successful transfer; if transmission fails, preserve it for later retry.

```mermaid
flowchart TD
    START[Collect observation] --> FORM[Validate crop-specific fields]
    FORM --> SAVE[Save locally in SQLite]
    SAVE --> WAIT[Pending synchronization]
    WAIT --> TRIGGER{Connectivity and sync action?}
    TRIGGER -- No --> WAIT
    TRIGGER -- Yes --> SEND[Send JSON via HTTP]
    SEND --> OK{Transmission confirmed?}
    OK -- Yes --> DONE[Mark as sent]
    OK -- No --> WAIT
```

The thesis describes both a user-facing action to send records and a retry queue. This diagram does not assert a specific background scheduling implementation or conflict-resolution algorithm not documented in source code.

## SQLite data organization

The thesis describes **three crop-specific relational tables** associated with a central collection/session entity through foreign keys. The central entity tracks date, timestamps, and synchronization state. It is not appropriate to invent exact SQL table or column names without source-code or schema evidence.

See [data-model.md](data-model.md) for the measured variables and their units.

## ThingsBoard views

The implemented platform has two high-level dashboard formats: **three data tables** (one per crop) and **three line charts** displaying time trends and minimum, maximum, and mean values.

![Thesis chart](../assets/thingsboard/telemetry-chart.png)

![Thesis table](../assets/thingsboard/records-table.png)

## Scope, provenance, and limitations

- The thesis reports **Flutter, Dart, MVVM, SQLite, HTTP and ThingsBoard**.
- This is documentation, not executable source code, a full database schema, or a guaranteed reproducible synchronization protocol.
- The figures above are original screenshots. The Mermaid diagrams are **explanatory reconstructions**, not copied source-code UML.
- **Thesis sections:** 2.2.4, 2.2.5, 3.2.1, 3.2.3, 3.2.4.
