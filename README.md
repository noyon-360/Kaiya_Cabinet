# Kaiya Cabinet

A cabinet design and estimating platform for iOS, built with SwiftUI. Contractors can create jobs, capture rooms, record measurements, select cabinet products, and generate estimates.

## Features

- **Authentication** — sign in, create account, forgot password with OTP verification, profile setup
- **Jobs** — create and manage jobs with customer and property details
- **Room Capture** — capture room layouts for a job
- **Measurements** — record room measurements
- **Products** — browse and select cabinets and related products with pricing
- **Settings** — edit profile, change password, notification preferences, contact us, delete account

## Requirements

- Xcode 26+
- iOS 18+
- Swift 5 / SwiftUI

## Project Structure

The app follows an MVVM architecture organized by feature:

```
Kaiya_Cabinet/
├── App/            # App entry point & root navigation
├── Core/
│   ├── Networking/ # API client, endpoints
│   ├── Services/   # AuthService, JobService, ProductService
│   ├── Storage/    # Keychain, UserDefaults, local cache
│   ├── Extensions/ # Swift & SwiftUI extensions
│   └── Utilities/  # Validators, formatters, helpers
├── DesignSystem/
│   ├── Components/ # Reusable UI components
│   └── Styles/     # Colors, fonts, spacing constants
├── Models/         # Shared data models (User, Job, Room, Product, …)
└── Features/       # One folder per feature, each with Views/ and ViewModels/
    ├── Authentication/
    ├── Home/
    ├── Jobs/
    ├── RoomCapture/
    ├── Measurements/
    ├── Products/
    └── Settings/
```

Each screen is a View + ViewModel pair. ViewModels use `@Observable` and talk to services in `Core/Services`; views never call the network directly.

## Getting Started

1. Clone the repository
2. Open `Kaiya_Cabinet.xcodeproj` in Xcode
3. Build and run on an iOS simulator or device

## Design

UI is based on the Figma file **Cabinet Design & Estimating Platform**.
