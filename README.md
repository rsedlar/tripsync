# TripSync

**Sync your team's journey.** TripSync is a smart carpooling optimizer that organizes team members from various Czech cities into shared cars for travel to Pichl bei Schladming, Austria. It handles complex geographic constraints, real-time cost calculations, and generates multiple optimized route variants.

## Features

### 🚗 Core Functionality
- **Smart Route Optimization**: Haversine distance calculations with real-world road distance correction (1.35x factor)
- **6 Intelligent Variants**: Multiple optimization strategies (capacity-based and efficiency-based)
- **Geographic Constraints**: Prevents unsuitable car-route combinations (e.g., Moravian cars cannot stop in Prague/Plzeň regions)
- **Real-Time Fuel Pricing**: Fetches current fuel prices from Czech market sources with automatic fallback proxies
- **Cost Calculation**: Accurate per-person expense calculation including fuel and driver contributions

### 👥 Passenger Management
- **Flexible Pickup Locations**: Support for primary and alternative pickup cities with intelligent preference penalties
- **Group Travel Support**: Union-Find algorithm enables "must travel together" groups (up to 3 members)
- **Early Departure Groups**: Dedicated cars for passengers who need to depart/arrive early
- **Constraint-Based Assignment**: Prioritizes most-constrained passengers for optimal placement

### 🚕 Vehicle Management
- **Flexible Driver Assignment**: Easy driver selection with name-based lookup
- **Car Status Tracking**: Toggle between active/inactive vehicles
- **Early Group Indicator**: Mark vehicles for early departure groups
- **Capacity Management**: Full control over available seats per vehicle

### 🌍 Smart Variant System
- **Varianta A** – Minimum vehicles, optimal efficiency
- **Varianta B** – One additional car for more comfort
- **Varianta C** – Two additional cars for maximum space
- **Varianta D** – Alternative efficiency approach
- **Varianta E** – Alternative with extra comfort
- **Varianta F** – Alternative with maximum flexibility

### 🔧 Configuration & Settings
- **Data Persistence**: All settings are saved automatically to browser local storage
- **Bilingual Interface**: Full support for Czech and English languages
- **Route Penalty System**: Direction-aware scoring with 5000km penalty for wrong-direction stops
- **Real-Time Summary**: Live status dashboard with unassigned passenger counts

## Usage

### Getting Started
1. **Open the application** in any modern web browser
2. **Select your language**: Czech (Čeština) or English in the top-right corner
3. **Configure vehicles**: Go to "Auta" tab, enter driver names and select availability
4. **Add passengers**: Use "Cestující" tab to input team members and their home cities
5. **Set constraints**: Configure groups, early departure needs, and special requirements
6. **Optimize**: Click "Vygeneruj varianty" (Generate Variants) to see all route options

### Tabs Overview

#### Auta (Vehicles)
- Add/remove vehicles
- Assign drivers
- Set capacity (usually 4-5 passengers per car)
- Mark early departure vehicles if needed

#### Cestující (Passengers)
- Input passenger names and home cities
- Set alternative pickup preferences
- Toggle passenger status (included/excluded)
- View assignment status

#### Nastavení (Settings)
- **Musí jet spolu** (Must travel together): Create groups that must share a car
- **Musí přijet nebo odjet dřív** (Must depart/arrive early): Assign early departure requirements
- **Kritické pravidlo** (Critical Rules): Geographic constraints for Moravian/Bohemian regions

#### Varianty (Variants)
- View all 6 optimization variants
- Click on variant card to see detailed route breakdown
- Analyze cost per person, total distance, and passenger distribution

### Key Settings Explained

**Critical Geographic Rule**: Vehicles departing from Moravian districts (Uherské Hradiště, Brno, Olomouc, Pelhřimov) cannot make stops in Bohemian districts (Prague, Plzeň, Pelhřimov). This prevents unnecessary cross-region detours.

**Alternative Pickup Preferences**: Primary city: 0 km penalty · Alternative city 1: +50 km · Alternative city 2: +100 km. TripSync uses these to minimize total route distance.

**Early Departure Groups**: Creates dedicated vehicles that leave earlier. Other passengers can still fill remaining seats — useful for team members with early commitments.

## Technical Specifications

### Algorithms
- **Distance Calculation**: Haversine formula + 1.35x road factor correction
- **Constraint Processing**: Union-Find for group relationships
- **Route Optimization**: Two-pass assignment (on-route first, then fallback)
- **Variant Generation**: Capacity-based (A-C) and efficiency-based (D-F) strategies

### Data Structure
- **Default Destination**: Preunegg 66, 8973 Pichl bei Schladming (47.3906°N, 13.6897°E)
- **Fuel Pricing**: Multi-proxy fallback system (corsproxy.io, allorigins.win, codetabs.com)
- **Vehicle Capacity**: Configurable per vehicle (default 4-5 passengers + driver)

### Browser Storage
- All configuration is automatically saved to localStorage
- No server backend required – fully client-side application
- Data persists between sessions

## Technical Implementation

- **Single-File HTML Application**: No build process, no dependencies, no installation
- **Pure JavaScript**: ES6+ with modular function organization
- **Responsive Design**: Works on desktop, tablet, and mobile browsers
- **Real-Time Updates**: Instant feedback as you modify settings

## System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge 2020+)
- JavaScript enabled
- Internet connection for fuel price updates (optional, has fallback)

## Installation

1. Download `tripsync.html`
2. Open the file in any web browser
3. Bookmark for quick access, or host on GitHub Pages for team sharing

## Privacy & Security

- All data processing happens in your browser
- No data is sent to external servers (except optional fuel price fetching)
- No accounts, logins, or tracking

## Version

**Version 2.0** – Full rewrite with geographic constraint system, 6-variant optimization, real-time fuel prices, group travel support, early departure management, and bilingual interface.

## License

Internal use tool for team travel coordination.

---

**Created for**: Team travel to Pichl bei Schladming, Austria
**Destination**: Preunegg 66, 8973 Pichl bei Schladming
**Route**: Multiple Czech cities → Austria
