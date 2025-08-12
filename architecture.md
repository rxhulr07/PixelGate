# PixelGate Architecture

## Overview
PixelGate follows a layered architecture that separates **Presentation**, **Business Logic**, and **Data** to ensure maintainability, scalability, and clear separation of concerns.

---

## 1. Presentation Layer
Responsible for rendering the UI and handling user interactions.

### Components:
- **Login Screen**  
  - Collects user credentials and triggers authentication.
- **Home Screen**  
  - **Drawer**: Provides navigation options.  
  - **GridView**: Displays a grid of images.

---

## 2. Business Logic Layer
Manages the core application logic, using the BLoC (Business Logic Component) pattern.

### Components:
- **AuthBloc**  
  - Handles authentication flow.
  - Validates login credentials.
  - On success, triggers `ImagesBloc` to load user-specific images.
  
- **ImagesBloc**  
  - Manages image fetching, filtering, and updating.
  - Interacts with both the **Image Repository** and **API Integration** to retrieve and update images.

---

## 3. Data Layer
Handles data persistence and remote API calls.

### Components:
- **Image Repository**  
  - Stores image data locally or in memory.
  - Acts as an abstraction between business logic and data sources.

- **API Integration**  
  - Connects to **Picaun API** to fetch and upload images.
  - Handles network requests and data parsing.

---

## Data Flow Diagram (Mermaid)

```mermaid
flowchart TD
    subgraph Presentation
        LS[Login Screen]
        HS[Home Screen]
        HS --> Drawer[Drawer]
        HS --> GridView[GridView]
    end

    subgraph BusinessLogic[Business Logic Layer]
        AB[AuthBloc]
        IB[ImagesBloc]
    end

    subgraph Data[Data Layer]
        IR[Image Repository]
        API[API Integration\n(Picaun API)]
    end

    LS --> AB
    HS <-- IB
    AB --> IB
    AB --> IR
    IB --> IR
    IB --> API
