# PixelGate

A Flutter demo app showcasing:

- **Login screen** with form validation
- **BLoC** state management
- **Navigation** to a home screen on successful login
- **Image fetching** via API (Picsum)
- **Randomized image selection**
- Responsive, modern UI with **gradients**
- Grid layout (**2 images per row**)
- Drawer with **user icon** and **logout**
- **Pull-to-refresh** support

---


## ✨ Features

- **Form Validation**
  - Email must match valid email format.
  - Password rules:
    - Minimum of **8 characters**
    - At least **1 uppercase** letter
    - At least **1 lowercase** letter
    - At least **1 number**
    - At least **1 symbol**
- **Images**
  - Shows **10 random images** from top 100 Picsum results.
- **UI**
  - Gradient backgrounds (Login, Home, Drawer)
  - Rounded cards with shadows
  - Image overlay text
- **Drawer**
  - User icon at the top, logout button at the bottom
- **Hover effects** for buttons on desktop/web
- **Footer** on login page:  
  _© 2025 PixelGate. All Rights Reserved._

---

## 🛠 Tech Stack

- **Flutter** (Dart)
- **flutter_bloc**
- **http**
- **Picsum API** (https://picsum.photos)

---

## 📂 Project Structure
```mermaid
flowchart TD
    A[lib] --> B[blocs]
    B --> C[auth]
    C --> C1[auth_bloc.dart]
    C --> C2[auth_event.dart]
    C --> C3[auth_state.dart]
    B --> D[images]
    D --> D1[images_bloc.dart]
    D --> D2[images_event.dart]
    D --> D3[images_state.dart]
    A --> E[data]
    E --> F[repositories]
    F --> F1[image_repository.dart]
    A --> G[models]
    G --> G1[image_model.dart]
    A --> H[ui]
    H --> I[screens]
    I --> I1[login_screen.dart]
    I --> I2[home_screen.dart]
    H --> J[widgets]
    J --> J1[custom_text_field.dart]
    A --> K[main.dart]
```

---

## 🚀 Getting Started

### 1️⃣ Prerequisites
- Flutter SDK installed ([Install Guide](https://docs.flutter.dev/get-started/install))
- Android Studio / Xcode for building
- Basic knowledge of Dart & Flutter

### 2️⃣ Install dependencies

flutter pub get

### 3️⃣ Run the app
```sh
flutter run
```

text

---

## 📦 Building APK

### Universal (fat) APK
```sh
flutter build apk
```

text
**Output:**  
`build/app/outputs/flutter-apk/app-release.apk`

---

### Split per ABI (smaller APKs)
flutter build apk --split-per-abi

text
**Output Directory:**  
`build/app/outputs/apk/release/`

Files:
- `app-armeabi-v7a-release.apk` (32-bit ARM)
- `app-arm64-v8a-release.apk` (64-bit ARM)
- `app-x86_64-release.apk` (x86 devices)

---

## 🔑 Validation Rules

- **Email Regex**:  
  `^[^@\s]+@[^@\s]+\.[^@\s]+$`
- **Password:**
  - Length >= 8
  - `[A-Z]` - uppercase letter
  - `[a-z]` - lowercase letter
  - `[0-9]` - number
  - `[!@#$%^&*(),.?":{}|<>]` - symbol

---

## 🌐 API Used

- **Picsum Photos API**:  
  Example endpoint:  
  `https://picsum.photos/v2/list?page=1&limit=100`

---

## 📜 License

This project is open-source under the MIT License.  
© 2025 **PixelGate** — All Rights Reserved.

---

## 📌 Trademark

> PixelGate is the project name used in this demo.  
> Ensure compliance with third-party licenses (e.g., Picsum).

---

