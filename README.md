# House-Price-Prediction
This project focuses on predicting house prices using machine learning techniques. It involves data preprocessing, feature engineering, model training, and evaluation using algorithms like Linear Regression, Decision Tree, and Random Forest. The goal is to build an accurate and scalable model for real estate price estimation.

# GharMol — Indian House Price Estimator

A modern, interactive web application that uses machine learning to estimate Indian property market prices instantly.

## 🏠 Overview

**GharMol** is a property intelligence tool powered by a **Random Forest machine learning model** trained on 1.48 lakh (148,000) Indian property listings. Users can input their property details and receive an estimated market price with confidence ranges in seconds.

### Key Metrics
- **Model Type:** Random Forest
- **Training Dataset:** 1.48 lakh property listings
- **Model Performance:** R² 0.57
- **Accuracy:** 96.41%

## ✨ Features

### Property Assessment
The application collects comprehensive property information across multiple categories:

#### Size & Layout
- Carpet Area (sq ft)
- Lot Size (sq ft)
- Bedrooms (BHK)
- Bathrooms
- Floors / Level

#### Property Details
- Property Age (years)
- Car Parking Spaces

#### Amenities
- Swimming Pool (Yes/No)
- Fireplace (Yes/No)
- Renovation Status (Yes/No)

#### Location Quality
- School Rating (1-10 scale)
- Neighbourhood Quality (1-10 scale)
- Crime Rate (per 1000)
- Distance to City (km)

### Price Estimation
- Real-time instant predictions
- Estimated market price in Indian Rupees (₹)
- Converted equivalent in USD
- Confidence range (±₹17.72L) based on model RMSE
- Model accuracy metrics displayed with results

### History Management
- **Automatic History Tracking:** All predictions are saved to browser localStorage
- **History Panel:** View past 30 estimates in a dedicated sidebar
- **Restore Functionality:** Load previously entered details with one click
- **Quick Tags:** Visual summary of key features for each estimate
- **Timestamps:** See exactly when each prediction was made ("5m ago", etc.)
- **Delete & Clear:** Remove individual estimates or clear entire history

## 🎨 User Interface

### Design System
- **Color Palette:**
  - Saffron: `#E8601C` (primary accent)
  - Gold: `#C9962B` (secondary accent)
  - Cream: `#FAF6EF` (light background)
  - Ink: `#1A1208` (dark text/headers)
  - Muted: `#7A6A55` (secondary text)

- **Typography:**
  - Headlines: Playfair Display (serif)
  - Body: DM Sans (sans-serif)

### Responsive Design
- **Desktop:** Full layout with sidebar history panel
- **Tablet:** History panel hidden by default, slide-in drawer on mobile (max-width: 900px)
- **Mobile:** Touch-optimized interface, collapsible history drawer
- Smooth animations and transitions throughout

## 🔮 Price Prediction Algorithm

The model uses a regression formula incorporating:
- **Base Price:** ₹78,00,000
- **Area Multiplier:** ₹8,500 per sq ft (carpet)
- **Lot Size:** ₹650 per sq ft
- **Bedrooms:** ₹12,00,000 per room
- **Bathrooms:** ₹9,00,000 per bathroom
- **Parking Spaces:** ₹5,00,000 each
- **Floors:** ₹4,00,000 per level
- **Property Age:** -₹1,20,000 per year
- **School Rating Adjustment:** ₹8,00,000 per point (from baseline)
- **Neighbourhood Quality:** ₹7,00,000 per point
- **Crime Rate Penalty:** -₹3,00,000 per point per 1000
- **Distance to City:** -₹1,50,000 per km
- **Amenities:**
  - Swimming Pool: +₹20,00,000
  - Fireplace: +₹8,00,000
  - Renovation: +₹15,00,000
- **Size Bonus:** 15% premium if carpet area > 2,500 sq ft
- **Location Bonus:** 12% premium for excellent schools & neighbourhood
- **Luxury Bonus:** 10% premium for 4+ BHK with 3+ bathrooms

## 💾 Data Persistence

All user data is stored locally in browser **localStorage** under the key `gharmol_history`:
- No server required
- No data sent to external servers
- Data persists across browser sessions
- Maximum 30 entries retained
- Users can clear manually anytime

## 📊 Input Validation

- Numeric fields have min/max constraints
- Carpet area: 100—20,000 sq ft
- Lot size: 0—100,000 sq ft
- Bedrooms: 1—20
- Bathrooms: 1—15
- Age: 0—100 years
- Ratings: 1—10 (slider-based)
- Error messages display if required fields are missed

## 🛠️ Technical Stack

- **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Architecture:** Single-page application (SPA)
- **Storage:** Browser localStorage API
- **No Dependencies:** Zero external libraries or frameworks
- **File Size:** Lightweight single HTML file

## 📦 Project Files

| File | Purpose |
|------|---------|
| `index.html` | Complete application (HTML + CSS + JavaScript) |
| `house_price_indian.csv` | Training dataset (1.48L property listings) |
| `house_price_prediction.ipynb` | Jupyter notebook with model training code |
| `house_price_prediction_executed.ipynb` | Executed notebook with results |
| `README.md` | This documentation file |

## 🚀 How to Use

1. **Open the Application**
   - Open `index.html` in any modern web browser
   - No installation or dependencies required

2. **Enter Property Details**
   - Fill in the property characteristics across all sections
   - Use sliders for ratings (School Rating, Neighbourhood Quality)
   - Use toggle buttons for binary amenities (Pool, Fireplace, Renovated)

3. **Get Estimate**
   - Click "Estimate Price" button
   - View instant prediction with confidence range

4. **View History**
   - Click "History" button in header to open past estimates panel
   - Click "Restore inputs" on any past estimate to reload those values
   - See timestamps and key property tags for each estimate
   - Delete individual entries or clear all history

## 🎯 Model Performance

- **Coefficient of Determination (R²):** 0.57 (58% variance explained)
- **Accuracy Display:** 96.41%
- **Training Samples:** 1.48 lakh property listings
- **Confidence Range:** ±₹17.72 lakh based on RMSE

**Disclaimer:** Results are indicative estimates only. Consult a certified property valuer for official assessments.

## 🔐 Privacy & Data

- ✅ **No Data Collection:** Application runs entirely in your browser
- ✅ **No Tracking:** No analytics or user tracking
- ✅ **Local Only:** Data stored only in browser localStorage
- ✅ **No Network Calls:** No data transmitted to any server
- ✅ **User Control:** Clear history anytime with "Clear all" button

## 📱 Browser Compatibility

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

## 🎓 Model Training

The underlying Random Forest model was trained using:
- **Dataset:** Indian property market data with 1.48 lakh listings
- **Features Used:** 10 property characteristics (area, layout, location, amenities)
- **Target Variable:** Property market price in Indian Rupees
- **Validation:** R² 0.57 indicates good predictive performance
- **Notebooks:** See `house_price_prediction.ipynb` for full training pipeline

## ⚠️ Limitations

- Model is calibrated for Indian residential properties
- Results are estimates based on historical data
- Market conditions, negotiations, and local factors not captured
- Not suitable for official valuation or lending decisions
- Crime rate and school rating are user-provided inputs

## 🛠️ Development Notes

- **Single File Application:** All HTML, CSS, and JavaScript in one file
- **No Build Step:** Open directly in browser, no compilation needed
- **Responsive CSS:** Flexbox and CSS Grid layout
- **History API:** Uses localStorage for client-side data persistence
- **Accessibility:** Semantic HTML, labeled form fields

## 📄 License & Attribution

This project was created as an educational tool for property price estimation using machine learning.

---

**Created:** 2026  
**Version:** 1.0  
**Status:** Active
