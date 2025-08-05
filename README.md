# Crypto Tracker - Kotlin

[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-blue.svg)](https://kotlinlang.org/)
[![Android](https://img.shields.io/badge/Android-API%2021+-green.svg)](https://developer.android.com/)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-Latest-brightgreen.svg)](https://developer.android.com/jetpack/compose)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A modern Android cryptocurrency tracking application built with **Jetpack Compose** and **Kotlin**. Track real-time cryptocurrency prices, view detailed charts, and monitor market trends with an intuitive adaptive UI that works seamlessly across different screen sizes.

![App Banner](screenshots/app_banner.png)

## 📱 Screenshots

| Coin List Screen | Coin Detail Screen | Adaptive Layout | Price Chart |
|------------------|-------------------|-----------------|-------------|
| ![Coin List](screenshots/coin_list.png) | ![Coin Detail](screenshots/coin_detail.png) | ![Adaptive](screenshots/adaptive_layout.png) | ![Chart](screenshots/price_chart.png) |

## ✨ Features

### 📊 Real-Time Data
- **Live Crypto Prices**: Real-time cryptocurrency price tracking
- **Market Cap Monitoring**: Track market capitalization changes
- **24h Price Changes**: Monitor daily price fluctuations with visual indicators
- **Historical Data**: 5-day price history with interactive charts

### 📈 Interactive Charts
- **Custom Line Charts**: Beautiful, smooth line charts with cubic curves
- **Touch Interactions**: Tap and drag to explore data points
- **Dynamic Labels**: Auto-adjusting labels based on screen size
- **Value Highlighting**: Selected data point highlighting with animations

### 🎨 Modern UI/UX
- **Material Design 3**: Latest Material Design guidelines
- **Adaptive Layout**: Responsive design for tablets and phones
- **List-Detail Navigation**: Seamless navigation between coin list and details
- **Dark/Light Theme**: Automatic theme switching
- **Smooth Animations**: Fluid transitions and micro-interactions

### 🏗️ Technical Excellence
- **Clean Architecture**: MVVM pattern with proper separation of concerns
- **Dependency Injection**: Koin for clean dependency management
- **Network Layer**: Ktor client with robust error handling
- **State Management**: StateFlow and Compose state management
- **Adaptive UI**: Material 3 Adaptive Navigation components

## 🏗️ Project Structure

```
crypto-tracker/
├── app/src/main/java/com/plcoding/cryptotracker/
│   ├── CryptoTrackerApp.kt                      # Application class with Koin setup
│   ├── MainActivity.kt                          # Main entry point
│   │
│   ├── crypto/
│   │   ├── core/
│   │   │   ├── data/networking/
│   │   │   │   ├── HttpClientFactory.kt         # Ktor client configuration
│   │   │   │   ├── constructUrl.kt              # URL construction utility
│   │   │   │   ├── responseToResult.kt          # Response mapping
│   │   │   │   └── safeCall.kt                  # Safe API calls
│   │   │   │
│   │   │   ├── domain/util/
│   │   │   │   ├── Error.kt                     # Error interface
│   │   │   │   ├── NetworkError.kt              # Network error types
│   │   │   │   └── Result.kt                    # Result wrapper
│   │   │   │
│   │   │   ├── navigation/
│   │   │   │   └── AdaptiveCoinListDetailPane.kt # Adaptive navigation
│   │   │   │
│   │   │   └── presentation/util/
│   │   │       ├── CoinCodeToResource.kt        # Coin icon mapping
│   │   │       ├── NetworkErrorToString.kt      # Error message mapping
│   │   │       └── ObserveAsState.kt            # Event observation
│   │   │
│   │   ├── data/
│   │   │   ├── mappers/
│   │   │   │   └── CoinMapper.kt                # Domain model mappers
│   │   │   │
│   │   │   └── networking/
│   │   │       ├── RemoteCoinDataSource.kt      # API data source
│   │   │       └── dto/                         # Data transfer objects
│   │   │           ├── CoinDto.kt
│   │   │           ├── CoinHistoryDto.kt
│   │   │           ├── CoinPriceDto.kt
│   │   │           └── CoinsResponseDto.kt
│   │   │
│   │   ├── domain/
│   │   │   ├── Coin.kt                          # Coin domain model
│   │   │   ├── CoinDataSource.kt                # Data source interface
│   │   │   └── CoinPrice.kt                     # Price domain model
│   │   │
│   │   └── presentation/
│   │       ├── coin_detail/
│   │       │   ├── CoinDetailScreen.kt          # Detail screen UI
│   │       │   ├── LineChart.kt                 # Custom chart component
│   │       │   ├── ChartStyle.kt                # Chart styling
│   │       │   ├── DataPoint.kt                 # Chart data model
│   │       │   └── component/
│   │       │       ├── InfoCard.kt              # Information cards
│   │       │       └── ValueLabel.kt            # Value formatting
│   │       │
│   │       ├── coin_list/
│   │       │   ├── CoinListScreen.kt            # List screen UI
│   │       │   ├── CoinListViewModel.kt         # List screen logic
│   │       │   ├── CoinListState.kt             # State management
│   │       │   ├── CoinListAction.kt            # User actions
│   │       │   ├── CoinListEvent.kt             # Side effects
│   │       │   └── components/
│   │       │       ├── CoinListItem.kt          # List item component
│   │       │       └── PriceChange.kt           # Price change indicator
│   │       │
│   │       └── models/
│   │           └── CoinUi.kt                    # UI models
│   │
│   ├── di/
│   │   └── AppModule.kt                         # Dependency injection
│   │
│   └── ui/theme/                                # App theming
│       ├── Color.kt
│       ├── Theme.kt
│       └── Type.kt
│
├── screenshots/                                 # App screenshots
├── build.gradle.kts                            # App-level Gradle config
└── README.md                                   # This file
```

## 🚀 Getting Started

### Prerequisites

- **Android Studio**: Flamingo (2022.2.1) or newer
- **JDK**: Version 17 or higher
- **Android SDK**: API level 21 (Android 5.0) or higher
- **Kotlin**: Version 1.9.0 or newer
- **Internet Connection**: Required for real-time data

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/plcoding/crypto-tracker.git
   cd crypto-tracker
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing Android Studio project"
   - Navigate to the cloned directory and select it

3. **Sync the project**
   - Android Studio will automatically sync the project
   - Wait for the Gradle sync to complete

4. **Run the application**
   - Connect an Android device or start an emulator
   - Click the "Run" button or press `Shift + F10`

## 🛠️ Technology Stack

### Core Technologies
- **Language**: 100% Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture**: MVVM + Clean Architecture
- **Dependency Injection**: Koin
- **Network**: Ktor Client
- **Serialization**: Kotlinx Serialization

## 🎨 UI Components

### Coin List Screen
![Coin List](screenshots/coin_list_screen.png)

The main screen displaying all available cryptocurrencies with real-time data.

**Key Features:**
- Live price updates
- Market cap information
- 24h change indicators with color coding
- Smooth scroll performance
- Pull-to-refresh functionality

### Coin Detail Screen
![Detail Screen](screenshots/coin_detail_screen.png)

Detailed view of individual cryptocurrencies with comprehensive information.

**Key Features:**
- Large coin icon with brand colors
- Price, market cap, and change cards
- Interactive price history chart
- Smooth chart interactions with data point selection
- Responsive layout for different screen sizes

### Interactive Line Chart
![Chart Component](screenshots/line_chart.png)

Custom-built chart component with smooth animations and interactions.

**Key Features:**
- Cubic bezier curve smoothing
- Touch gesture support for data exploration
- Dynamic label positioning
- Responsive axis scaling
- Custom styling system

### Adaptive Layout
![Adaptive Layout](screenshots/adaptive_layout.png)

Responsive design that adapts to different screen sizes and orientations.

**Key Features:**
- List-detail pattern for tablets
- Single pane navigation for phones
- Automatic layout switching
- Maintained state across configuration changes

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

---

**Happy Coding! 📈💰**
