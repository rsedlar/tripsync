# Changelog

All notable changes to the TripSync are documented here.

## [2.0.0] - Current Release

### 🎯 Major Features
- Complete rewrite with modern architecture
- 6-variant intelligent optimization system
- Real-world geographic constraint handling
- Multi-proxy fuel price fetching
- Bilingual interface (Czech/English)
- Group travel management
- Early departure groups support
- Direction-aware route optimization

### ✨ Key Capabilities
- **Smart Route Optimization**: Haversine distance with 1.35x road factor correction
- **Constraint System**: Union-Find algorithm for passenger groups (2-3 members)
- **Geographic Rules**: Prevents Moravian cars from stopping in Bohemian regions
- **6-Variant Strategy**:
  - A-C: Capacity-based optimization
  - D-F: Efficiency-based optimization
- **Cost Calculation**: Accurate per-person expense tracking
- **Real-Time Fuel Prices**: Multi-proxy fallback system
- **Local Storage**: Automatic data persistence

### 🚗 Default Configuration
- **Destination**: Preunegg 66, 8973 Pichl bei Schladming, Austria
- **6 Vehicles**: Pre-configured with driver names
- **18 Passengers**: Sample team with cities and preferences
- **Geographic Origin Cities**: 19 Moravian cities + Bohemian alternatives

### 🔧 Technical Improvements
- Road distance correction: Formula × 1.35 factor
- Direction penalty: 5000km for wrong-direction stops
- Alternative pickup penalties: 0km / +50km / +100km
- Two-pass assignment: On-route first, then fallback
- Constraint-based prioritization: Most-constrained first
- Early group feature: Dedicated cars with shared capacity

### 🐛 Fixes (v2.0)
- Fixed duplicate unassigned passenger entries
- Corrected constraint-based assignment sorting
- Improved early group exclusivity logic
- Enhanced kilometer accuracy with road factor
- Simplified variant labeling for clarity
- Fixed fuel price fetching with proxy fallbacks

### 🌍 Localization
- Full Czech translation (Čeština)
- Full English translation
- Direction-aware UI for both languages
- Local market data (Czech fuel prices)

## [1.0.0] - Original Release

### Initial Features
- Basic carpooling optimization
- Simple route calculation
- Cost per person calculation
- Vehicle management
- Passenger assignment

---

## Version History Overview

| Version | Date | Status | Focus |
|---------|------|--------|-------|
| 2.0.0 | 2026-03 | Current | Complete rewrite, geographic constraints, 6-variant system |
| 1.0.0 | 2025-xx | Legacy | Initial carpooling optimizer |

---

## Planned Features (Future)

- [ ] Export to PDF with detailed route maps
- [ ] Integration with Google Maps for real-time distances
- [ ] Email invitation generation
- [ ] QR code for easy sharing
- [ ] Mobile app version
- [ ] Multi-language expansion
- [ ] Historical trip data analysis
- [ ] Recurring trip templates

---

## Known Limitations

- Fuel prices require internet connection
- Maximum 50-60 passengers recommended
- Designed for single-day trips (not multi-day)
- Route optimization is estimated (not exact GPS)
- Early group limited to single vehicle

---

## Feedback & Improvements

This application was developed iteratively based on real user feedback including:
- Route optimization accuracy
- Geographic constraint modeling
- Variant strategy effectiveness
- UI/UX clarity and usability
- Performance optimization

Continuous improvements are welcomed!

---

## Migration Notes

If updating from v1.0.0 to v2.0.0:
- All data will be reset (localStorage structure changed)
- Reconfigure passengers and vehicles
- New geographic constraints apply
- 6 variants replace simple variant system

---

**Last Updated**: March 18, 2026
**Current Stable Version**: 2.0.0
**Repository**: https://github.com/{username}/tripsync
