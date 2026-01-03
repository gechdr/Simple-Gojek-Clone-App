# 🏍️ GoRide - Simple Gojek Clone

<div align="center">

![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-7F52FF?logo=kotlin&logoColor=white)
![SDK](https://img.shields.io/badge/SDK-34-brightgreen)
![MVVM](https://img.shields.io/badge/Architecture-MVVM-orange)
![License](https://img.shields.io/badge/license-MIT-green.svg)

**A Gojek-inspired ride-hailing Android application built with Kotlin and MVVM Architecture**

[Features](#-features) • [Screenshots](#-screenshots) • [Installation](#-installation) • [Architecture](#-architecture) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

GoRide is a simplified clone of Gojek, Indonesia's leading ride-hailing super app. This native Android application demonstrates core ride-hailing functionalities including user authentication, ride booking (bike and car), order management, and digital wallet features.

Built using modern Android development practices with MVVM architecture, ViewModel, LiveData, and Data Binding.

## ✨ Features

### 🔐 Authentication System

| Feature | Description |
|---------|-------------|
| **User Registration** | Register as Customer or Driver (Mitra) |
| **Secure Login** | Username and password authentication |
| **Role-based Access** | Different interfaces for Customers and Drivers |
| **Input Validation** | Phone number (12 digits), password confirmation |

### 👤 Customer Features

- **🏠 Dashboard** - View balance and order history
- **🏍️ Book Bike Ride** - Order motorcycle taxi (ojek)
- **🚗 Book Car Ride** - Order car ride service
- **💳 Top Up Balance** - Add funds to wallet (min. Rp 1,000)
- **📋 Order Tracking** - Monitor order status in real-time
- **📜 Order History** - View all past and current orders

### 🚘 Driver Features

- **🏠 Dashboard** - View balance and available orders
- **📍 Active Order** - Current ongoing delivery display
- **📋 Available Orders** - Browse waiting orders to accept
- **✅ Accept Orders** - Pick up waiting customer orders
- **✔️ Complete Orders** - Mark orders as done and receive payment
- **📱 SMS Customer** - Direct messaging to customer via SMS intent

### 💰 Wallet System

- **Digital Balance** - In-app currency system (Indonesian Rupiah)
- **Top Up** - Add funds with minimum Rp 1,000
- **Auto Payment** - Fare automatically deducted when order completes
- **Driver Earnings** - Fare transferred to driver upon completion
- **Balance Check** - Insufficient balance validation

### 📦 Order Management

| Status | Description |
|--------|-------------|
| **Waiting** | Order placed, awaiting driver |
| **On Going** | Driver accepted, ride in progress |
| **Done** | Ride completed, payment processed |

## 📱 Screenshots

| Login | Register | Customer Home |
|:---:|:---:|:---:|
| ![Login](screenshots/login.png) | ![Register](screenshots/register.png) | ![Customer Home](screenshots/customer_home.png) |

| Book Ride | Driver Home | Order Detail |
|:---:|:---:|:---:|
| ![Book](screenshots/book_ride.png) | ![Driver Home](screenshots/driver_home.png) | ![Detail](screenshots/order_detail.png) |

> **Note**: Add your own screenshots to the `screenshots/` folder

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| [Kotlin](https://kotlinlang.org/) | Primary programming language |
| [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) | UI-related data management |
| [LiveData](https://developer.android.com/topic/libraries/architecture/livedata) | Observable data holder |
| [Data Binding](https://developer.android.com/topic/libraries/data-binding) | Declarative UI binding |
| [View Binding](https://developer.android.com/topic/libraries/view-binding) | Type-safe view access |
| [Material Components](https://material.io/develop/android) | UI components and theming |
| [RecyclerView](https://developer.android.com/guide/topics/ui/layout/recyclerview) | Efficient list display |
| [ConstraintLayout](https://developer.android.com/training/constraint-layout) | Flexible UI layouts |

## 📋 Requirements

- **Android Studio**: Hedgehog (2023.1.1) or later
- **Minimum SDK**: API 34 (Android 14)
- **Target SDK**: API 34
- **JDK**: 1.8+
- **Gradle**: 8.3.0

## 🚀 Installation

### Clone the Repository

```bash
git clone https://github.com/yourusername/Simple-Gojek-Clone-App.git
cd Simple-Gojek-Clone-App
```

### Open in Android Studio

1. Launch **Android Studio**
2. Select **File > Open**
3. Navigate to the cloned repository
4. Click **OK** and wait for Gradle sync

### Build and Run

```bash
# Build the project
./gradlew build

# Install on connected device/emulator
./gradlew installDebug
```

Or click the **Run** button (▶️) in Android Studio.

### Demo Accounts

The app comes with pre-configured test accounts:

| Username | Password | Role | Balance |
|----------|----------|------|---------|
| `morgan` | `123` | Customer | Rp 1,000,000 |
| `martin` | `123` | Customer | Rp 3,000,000 |
| `randy` | `123` | Customer | Rp 4,000,000 |
| `medon` | `123` | Driver | Rp 2,000,000 |
| `esme` | `123` | Driver | Rp 5,000,000 |
| `andy` | `123` | Driver | Rp 6,000,000 |

## 📁 Project Structure

```
Simple-Gojek-Clone-App/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/tugasm6/
│   │   │   │   │
│   │   │   │   ├── Activities/
│   │   │   │   │   ├── LoginActivity.kt              # User login
│   │   │   │   │   ├── RegisterActivity.kt           # User registration
│   │   │   │   │   ├── CustomerHomeActivity.kt       # Customer dashboard
│   │   │   │   │   ├── CustomerRideActivity.kt       # Book a ride
│   │   │   │   │   ├── CustomerTopUpActivity.kt      # Top up balance
│   │   │   │   │   ├── CustomerOrderDetailActivity.kt # Order details
│   │   │   │   │   ├── DriverHomeActivity.kt         # Driver dashboard
│   │   │   │   │   └── DriverOrderDetailActivity.kt  # Accept/complete orders
│   │   │   │   │
│   │   │   │   ├── ViewModels/
│   │   │   │   │   ├── UserViewModel.kt              # User state management
│   │   │   │   │   ├── OrderViewModel.kt             # Order state management
│   │   │   │   │   └── FareViewModel.kt              # Fare calculation
│   │   │   │   │
│   │   │   │   ├── Models/
│   │   │   │   │   ├── User.kt                       # User data class
│   │   │   │   │   └── Order.kt                      # Order data class
│   │   │   │   │
│   │   │   │   ├── Adapters/
│   │   │   │   │   └── OrderAdapter.kt               # Order list adapter
│   │   │   │   │
│   │   │   │   ├── Utils/
│   │   │   │   │   └── CurrencyUtils.kt              # Rupiah formatting
│   │   │   │   │
│   │   │   │   └── Data/
│   │   │   │       └── MockDB.kt                     # In-memory database
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/                           # XML layouts
│   │   │   │   ├── drawable/                         # Icons (bike, car)
│   │   │   │   ├── menu/                             # Navigation menu
│   │   │   │   └── values/                           # Colors, strings, themes
│   │   │   │
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   └── test/                                     # Unit tests
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── libs.versions.toml                            # Dependency versions
│
└── README.md
```

## 🏗️ Architecture

### MVVM Pattern

```
┌─────────────────────────────────────────────────────────────┐
│                          VIEW                                │
│    (Activities with Data Binding)                           │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐       │
│  │ LoginActivity│  │CustomerHome │  │ DriverHome  │       │
│  └──────────────┘  └──────────────┘  └──────────────┘       │
└────────────────────────────┬────────────────────────────────┘
                             │ observes LiveData
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                       VIEWMODEL                              │
│    (State Management & Business Logic)                       │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐       │
│  │ UserViewModel│  │OrderViewModel│  │ FareViewModel│       │
│  └──────────────┘  └──────────────┘  └──────────────┘       │
└────────────────────────────┬────────────────────────────────┘
                             │ accesses
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                         MODEL                                │
│    (Data Classes & Mock Database)                           │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐       │
│  │    User      │  │    Order     │  │    MockDB    │       │
│  └──────────────┘  └──────────────┘  └──────────────┘       │
└─────────────────────────────────────────────────────────────┘
```

### Data Models

#### User
```kotlin
data class User(
    val username: String,
    val password: String,
    val name: String,
    val phoneNumber: String,
    var balance: Int,
    val role: String        // "Customer" or "Driver"
)
```

#### Order
```kotlin
data class Order(
    val id: Int,
    val type: String,       // "Bike" or "Car"
    val customer: String,   // Customer username
    var driver: String,     // Driver username (empty if waiting)
    val pickUp: String,
    val destination: String,
    val fare: Int,
    var status: String      // "Waiting", "On Going", "Done"
)
```

### App Flow

```
                    ┌─────────────┐
                    │   Login     │
                    │  Activity   │
                    └──────┬──────┘
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
    ┌─────────────────┐       ┌─────────────────┐
    │    Customer     │       │     Driver      │
    │      Home       │       │      Home       │
    └────────┬────────┘       └────────┬────────┘
             │                         │
    ┌────────┼────────┐       ┌────────┴────────┐
    │        │        │       │                 │
    ▼        ▼        ▼       ▼                 ▼
┌───────┐┌───────┐┌───────┐┌───────┐      ┌───────┐
│ Ride  ││Top Up ││Order  ││Order  │      │Accept │
│ Book  ││       ││Detail ││ List  │      │ Order │
└───────┘└───────┘└───────┘└───────┘      └───────┘
```

## 📝 Usage Guide

### For Customers

1. **Login/Register** - Create account or login with existing credentials
2. **View Dashboard** - Check your balance and order history
3. **Book a Ride**:
   - Tap 🏍️ for bike or 🚗 for car
   - Enter pickup location
   - Enter destination
   - View calculated fare
   - Confirm booking (requires sufficient balance)
4. **Top Up** - Add funds if balance is low (minimum Rp 1,000)
5. **Track Order** - Monitor your order status

### For Drivers

1. **Login** - Use driver account credentials
2. **View Dashboard** - See your balance and active order
3. **Browse Orders** - View available "Waiting" orders
4. **Accept Order**:
   - Tap on an order to view details
   - Press "Accept" to take the order
   - Only one active order allowed at a time
5. **Contact Customer** - Use SMS button to message customer
6. **Complete Order**:
   - Press "Done" when ride is complete
   - Fare is automatically transferred to your balance

## 🔧 Configuration

### Customizing Fare Calculation

Edit `FareViewModel.kt` to modify fare logic:

```kotlin
fun calculateFare() {
    // Current: Random fare between ranges
    _fare.value = (50000..300000).random()
    
    // You can implement distance-based calculation:
    // _fare.value = calculateDistanceBasedFare(pickup, destination)
}
```

### Adding New Vehicle Types

1. Add drawable resource for the vehicle icon
2. Update `CustomerHomeActivity` with new button
3. Add vehicle type handling in `Order` model
4. Update adapters and layouts accordingly

### Connecting to Real Database

Replace `MockDB.kt` with Room Database:

```kotlin
// 1. Add Room dependencies
implementation("androidx.room:room-runtime:2.6.1")
kapt("androidx.room:room-compiler:2.6.1")

// 2. Create Entity classes with @Entity annotation
// 3. Create DAO interfaces
// 4. Create AppDatabase class
// 5. Update ViewModels to use Room
```

## 🧪 Testing

### Run Unit Tests

```bash
./gradlew test
```

### Run Instrumented Tests

```bash
./gradlew connectedAndroidTest
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Feature Ideas

- [ ] Google Maps integration for real locations
- [ ] Real-time GPS tracking
- [ ] Push notifications
- [ ] Rating system for drivers
- [ ] Multiple payment methods
- [ ] Promo codes and discounts
- [ ] Ride scheduling (book for later)
- [ ] Food delivery (GoFood clone)
- [ ] Package delivery (GoSend clone)
- [ ] Firebase backend integration
- [ ] Chat feature between customer and driver
- [ ] Ride history with receipts
- [ ] Driver verification system
- [ ] Emergency SOS button

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

## 🙏 Acknowledgments

- [Gojek](https://www.gojek.com/) - Inspiration for the app concept
- [Android Developers](https://developer.android.com/) - Official documentation
- [Material Design](https://material.io/) - Design guidelines
- [Kotlin](https://kotlinlang.org/) - Programming language

---

<div align="center">

**Built using Kotlin**

[🔝 Back to Top](#️-goride---simple-gojek-clone)

</div>
