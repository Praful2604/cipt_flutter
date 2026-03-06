# CIPT Flutter - Interview Practice App

Flutter conversion of the CIPT (Pick Up Tool) React project. AI-powered interview preparation with video recording and performance feedback.

## Prerequisites

- Flutter SDK (3.24+)
- Node.js backend running (see parent `backend/` folder)
- For mobile: Android Studio / Xcode for device testing

## Running the App

### 1. Start the Backend

```bash
cd ../backend
npm start
```

The backend runs at `http://localhost:5000`.

### 2. Run Flutter

**Web (recommended for quick testing):**
```bash
flutter run -d chrome
```

**Android:**
```bash
flutter run -d android
```
> For Android emulator/device: Update `lib/config/api_config.dart` to use your machine's IP (e.g., `http://10.0.2.2:5000` for Android emulator) instead of `localhost`.

**iOS:**
```bash
flutter run -d ios
```

**Windows:**
```bash
flutter run -d windows
```

## Project Structure

```
lib/
├── config/          # API base URL
├── providers/       # Auth state (Provider)
├── screens/         # Home, Login, Skills, Video, etc.
├── services/        # API client (Dio)
├── widgets/         # Nav shell, shared components
├── app_router.dart  # GoRouter routes
└── main.dart
```

## Features (from React)

- **Home** – Landing page with feature overview
- **Login/Register** – Session-based auth (cookies)
- **Skills** – Technical vs Soft skills selection
- **Guidelines** – Interview tips
- **Time Slot** – 10/15/20 min duration
- **Domain** – Python, DBMS, OS, etc.
- **Video** – Camera recording + upload to backend
- **Final Report** – Performance report (after session)

## Backend CORS

The backend has been updated to allow Flutter web origins (`localhost:8080`, `127.0.0.1:8080`). For mobile, ensure the backend is reachable from your device/emulator.

**Note:** On Flutter web, session cookies may not persist correctly due to cross-origin restrictions. For full auth flow, prefer running on **Android**, **iOS**, or **Windows**.

## API Configuration

Edit `lib/config/api_config.dart`:

- **Web**: `http://localhost:5000` (default)
- **Android Emulator**: `http://10.0.2.2:5000`
- **Physical device**: `http://YOUR_PC_IP:5000`
