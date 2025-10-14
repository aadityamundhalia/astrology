# 🌟 Vedic Astrology API - Enhanced Edition

> **Ultra-precise astrological predictions with 24-month forecasts and event-specific analysis**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green.svg)](https://fastapi.tiangolo.com/)
[![Swiss Ephemeris](https://img.shields.io/badge/Swiss_Ephemeris-Latest-orange.svg)](https://www.astro.com/swisseph/)

---

## 🚀 What's New in v2.0?

### ✨ Five Powerful New Endpoints

1. **`/predictions/love`** - 24-month love & relationship forecast
2. **`/predictions/health`** - 24-month health & wellness forecast  
3. **`/predictions/career`** - 24-month career & professional forecast
4. **`/predictions/wealth`** - 24-month financial & wealth forecast
5. **`/predictions/wildcard`** 🎯 - Specific event predictions with success probability

### 🎯 Key Features

- ✅ **24-Month Forecasts** with precise date ranges
- ✅ **Success Probability** ratings (0-100%)
- ✅ **Hour-Level Timing** precision
- ✅ **Natural Language Queries** - Ask in plain English
- ✅ **Risk Assessment** with mitigation strategies
- ✅ **Actionable Remedies** for challenging times
- ✅ **Lucky Factors** (colors, numbers, directions)
- ✅ **Best Dates** identification for activities

---

## 🏃 Quick Start

### 1. Install Dependencies
```bash
pip install fastapi uvicorn swisseph pytz requests pydantic
```

### 2. Start the API
```bash
python app.py
```

The API will be available at `http://localhost:8000`

### 3. Test the Endpoints
```bash
python test_new_endpoints.py
```

### 4. View Documentation
Open in browser: `http://localhost:8000/docs`

---

## 💡 Usage Examples

### Example 1: Get 24-Month Love Predictions

**Request:**
```bash
curl -X POST http://localhost:8000/predictions/love \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "10:30",
    "place_of_birth": "Mumbai, India"
  }'
```

**What You Get:**
- Month-by-month ratings for 24 months
- Best months for marriage/proposals
- Challenging periods with coping strategies
- Lucky dates for romance
- Specific remedies

---

### Example 2: Ask Specific Questions (Wildcard)

**Request:**
```bash
curl -X POST http://localhost:8000/predictions/wildcard \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "10:30",
    "place_of_birth": "London, UK",
    "query": "I have a job interview on December 15th 2024, how will it go?"
  }'
```

**What You Get:**
- Success probability (0-100%)
- Best time of day for interview
- Planetary positions on that date
- Specific advice tailored to interview
- Risks and mitigation strategies
- Remedies to improve chances
- Lucky colors, numbers, direction

---

### Example 3: Check Safety

**Request:**
```python
import requests

response = requests.post(
    "http://localhost:8000/predictions/wildcard",
    json={
        "date_of_birth": "1992-11-08",
        "time_of_birth": "18:20",
        "place_of_birth": "Sydney, Australia",
        "query": "I'm buying a motorcycle, will I be safe riding it?"
    }
)

result = response.json()
print(f"Safety Rating: {result['success_probability']['rating']}")
print(f"Safety Probability: {result['success_probability']['percentage']}%")
```

---

## 🎯 Supported Query Types

### Romance & Dating
- "I'm going on a date on October 20th, what are my chances?"
- "Planning to propose on Valentine's Day, good idea?"
- "When should I get married in 2025?"

### Career & Job
- "I have a job interview on March 15th, how will it go?"
- "My company is going through redundancy, will I be safe?"
- "Should I change jobs in December?"

### Safety & Health
- "I'm buying a motorcycle, will I be safe riding it?"
- "Should I schedule surgery on this date?"
- "When should I be careful about my health?"

### Business & Finance
- "Should I sign a contract on January 15th?"
- "Starting a business on April 1st, will it succeed?"
- "When should I invest in property?"

---

## 📊 All Available Endpoints

### Chart Endpoints
- `POST /chart/complete` - Complete birth chart
- `POST /chart/quick` - Quick essentials

### Time-Based Predictions
- `POST /predictions/today` - Today's forecast
- `POST /predictions/week` - 7-day forecast
- `POST /predictions/month` - Current month
- `POST /predictions/quarter` - 3-month forecast
- `POST /predictions/yearly` - 12-month forecast

### **NEW: 24-Month Area-Specific Predictions** ✨
- `POST /predictions/love` - 24-month love forecast
- `POST /predictions/health` - 24-month health forecast
- `POST /predictions/career` - 24-month career forecast
- `POST /predictions/wealth` - 24-month wealth forecast

### **NEW: Wildcard Predictions** 🎯
- `POST /predictions/wildcard` - Specific event analysis

### Natal Analysis
- `POST /analysis/love` - Love & marriage analysis
- `POST /analysis/wealth` - Financial analysis
- `POST /analysis/career` - Career analysis
- `POST /analysis/health` - Health analysis

---

## 📖 Documentation

| Document | Purpose | Lines |
|----------|---------|-------|
| **[QUICKSTART.md](QUICKSTART.md)** | Get started in 5 minutes | ~400 |
| **[API_DOCUMENTATION.md](API_DOCUMENTATION.md)** | Complete API reference | ~1500 |
| **[UPDATE_SUMMARY.md](UPDATE_SUMMARY.md)** | What's new in v2.0 | ~500 |
| **[README.md](README.md)** | This file | ~300 |

---

## 🔧 Technical Details

### Architecture
- **Framework:** FastAPI (Python)
- **Ephemeris:** Swiss Ephemeris (highest precision)
- **Ayanamsa:** Lahiri (traditional Vedic)
- **House System:** Placidus
- **Zodiac:** Sidereal (Vedic)

### Calculations Include
- ✅ All 9 planets (Sun to Ketu)
- ✅ 12 houses with cusps
- ✅ 27 nakshatras (lunar mansions)
- ✅ Planetary dignities (exaltation, debilitation)
- ✅ Transit analysis
- ✅ House activation timing
- ✅ Muhurta (auspicious timing)

### Performance
- **24-Month Predictions:** 10-30 seconds
- **Wildcard Queries:** 5-15 seconds
- **Quick Predictions:** 1-3 seconds
- **Chart Calculations:** 1-2 seconds

---

## 🌟 Key Features Explained

### 1. Precise Date Interpretation
Every prediction includes:
- Exact dates (YYYY-MM-DD format)
- Day names (Monday, Tuesday, etc.)
- Full readable dates
- Date ranges for periods

### 2. Rating System (1-10)
- **9-10:** Exceptional - Best time
- **7-8:** Excellent - Very favorable
- **5-6:** Good - Positive with caution
- **4:** Average - Mixed results
- **2-3:** Challenging - Exercise caution
- **1:** Very Difficult - Postpone if possible

### 3. Success Probability (0-100%)
- **80-100%:** Very High - Proceed confidently
- **65-79%:** High - Good prospects
- **50-64%:** Moderate - Prepare well
- **35-49%:** Low - Extra caution needed
- **0-34%:** Very Low - Consider postponing

### 4. Comprehensive Advice
For every prediction:
- 📝 **What to Do** - Specific actions
- ⛔ **What to Avoid** - Things to stay away from
- 🔮 **Remedies** - Astrological solutions
- 🛡️ **Mitigation** - How to overcome challenges

---

## 🎓 Use Cases

### Personal Planning
- ❤️ Marriage timing and relationship planning
- 🏥 Health checkups and medical procedures
- 💼 Career moves and job changes
- 💰 Investment and financial decisions

### Event Planning
- 📅 Choose auspicious dates for events
- 🎉 Plan important celebrations
- ✈️ Travel safety assessment
- 🏠 Property purchase timing

### Business Strategy
- 🚀 Launch timing for products/services
- 📊 Investment opportunity analysis
- 🤝 Contract signing dates
- 💼 Hiring and expansion timing

### Risk Management
- 🛡️ Safety assessment for activities
- ⚠️ Risk identification and mitigation
- 🏍️ Vehicle purchase timing
- 🏢 Job security during transitions

---

## 📦 Project Structure

```
vedastro/
├── app.py                      # Main FastAPI application
├── predictions.py              # Prediction engine & calculations
├── local_calculate.py          # Core astrology calculations
├── test_new_endpoints.py       # Automated tests
├── requirements.txt            # Python dependencies
├── API_DOCUMENTATION.md        # Complete API reference
├── QUICKSTART.md              # Quick start guide
├── UPDATE_SUMMARY.md          # Update details
├── README.md                  # This file
├── ephe/                      # Swiss Ephemeris data files
│   ├── seas_18.se1
│   ├── semo_18.se1
│   └── sepl_*.se1
└── __pycache__/               # Python cache
```

---

## 🧪 Testing

### Run All Tests
```bash
python test_new_endpoints.py
```

### Test Individual Endpoints
```python
import requests

# Test love predictions
response = requests.post(
    "http://localhost:8000/predictions/love",
    json={
        "date_of_birth": "1990-05-15",
        "time_of_birth": "10:30",
        "place_of_birth": "Mumbai, India"
    }
)
print(response.json())
```

---

## 🔮 Vedic Astrology Concepts

### Houses (Bhavas)
1. **1st House:** Self, Health, Personality
2. **2nd House:** Wealth, Family, Speech
3. **3rd House:** Courage, Siblings, Communication
4. **4th House:** Home, Mother, Property
5. **5th House:** Children, Romance, Creativity
6. **6th House:** Health Issues, Enemies, Service
7. **7th House:** Marriage, Partnerships
8. **8th House:** Transformation, Longevity
9. **9th House:** Fortune, Father, Spirituality
10. **10th House:** Career, Status, Authority
11. **11th House:** Gains, Friends, Aspirations
12. **12th House:** Expenses, Foreign, Spirituality

### Planets (Grahas)
- **Sun (Surya):** Authority, vitality, father
- **Moon (Chandra):** Mind, emotions, mother
- **Mars (Mangal):** Energy, courage, property
- **Mercury (Budha):** Intelligence, business
- **Jupiter (Guru):** Wisdom, wealth, children
- **Venus (Shukra):** Love, luxury, relationships
- **Saturn (Shani):** Discipline, delays, karma
- **Rahu:** Sudden events, materialism
- **Ketu:** Spirituality, detachment

---

## 🛠️ Dependencies

```txt
fastapi>=0.100.0
uvicorn>=0.23.0
pyswisseph>=2.10.0
pytz>=2023.3
requests>=2.31.0
pydantic>=2.0.0
```

Install all:
```bash
pip install -r requirements.txt
```

---

## 🐛 Troubleshooting

### API Won't Start?
```bash
# Check if port 8000 is in use
lsof -i :8000

# Install dependencies
pip install -r requirements.txt

# Run with debug
uvicorn app:app --reload
```

### Slow Predictions?
- 24-month calculations are computationally intensive (10-30 seconds is normal)
- First calculation per session may be slower
- Wildcard queries are optimized (5-15 seconds)

### Geocoding Errors?
- Check internet connection (needs OpenStreetMap)
- Use specific city names: "Mumbai, India" not just "Mumbai"
- Try alternative place names if one doesn't work

---

## 📈 Version History

### v2.0 (October 2024) - Enhanced Edition
- ✨ Added 4 new 24-month prediction endpoints
- 🎯 Added wildcard endpoint for specific queries
- 📅 Natural language date parsing
- 🎲 Success probability calculations
- 🛡️ Risk assessment and mitigation
- 🔮 Comprehensive remedies
- 📖 Complete documentation suite

### v1.0 (Previous)
- Basic chart calculations
- 12-month predictions
- Area analysis endpoints
- Daily/weekly/monthly forecasts

---

## 🤝 Contributing

This is a production-ready API. For enhancements:
1. Test thoroughly with `test_new_endpoints.py`
2. Maintain backward compatibility
3. Update documentation
4. Follow existing code style

---

## 📞 Support & Resources

### Documentation
- **Quick Start:** [QUICKSTART.md](QUICKSTART.md)
- **Full API Reference:** [API_DOCUMENTATION.md](API_DOCUMENTATION.md)
- **Update Details:** [UPDATE_SUMMARY.md](UPDATE_SUMMARY.md)

### Interactive Docs
- **Swagger UI:** http://localhost:8000/docs
- **ReDoc:** http://localhost:8000/redoc

### Learning Resources
- Swiss Ephemeris: https://www.astro.com/swisseph/
- Vedic Astrology: Traditional texts and resources
- FastAPI: https://fastapi.tiangolo.com/

---

## 🎯 Next Steps

1. **Start the API:** `python app.py`
2. **Run Tests:** `python test_new_endpoints.py`
3. **Read Quick Start:** [QUICKSTART.md](QUICKSTART.md)
4. **Explore Examples:** Check documentation
5. **Integrate:** Use in your application

---

## 📜 License

This software uses Swiss Ephemeris which has specific licensing:
- **Free for personal and research use**
- **Commercial use requires license from Astrodienst**
- See: https://www.astro.com/swisseph/

---

## 🌟 Features at a Glance

| Feature | v1.0 | v2.0 |
|---------|------|------|
| Birth Chart | ✅ | ✅ |
| Daily Predictions | ✅ | ✅ |
| Monthly Predictions | ✅ | ✅ |
| Yearly Predictions | ✅ | ✅ |
| **24-Month Forecasts** | ❌ | ✅ |
| **Event-Specific Queries** | ❌ | ✅ |
| **Success Probability** | ❌ | ✅ |
| **Natural Language** | ❌ | ✅ |
| **Hour-Level Timing** | ❌ | ✅ |
| **Risk Assessment** | ❌ | ✅ |
| **Actionable Remedies** | ⚠️ | ✅ |
| **Lucky Factors** | ❌ | ✅ |

---

## 💎 Why This API?

### Precision
- Uses Swiss Ephemeris (NASA-grade accuracy)
- Hour-level timing precision
- Traditional Vedic calculations
- Comprehensive planetary analysis

### Comprehensive
- All 9 planets analyzed
- 12 houses calculated
- 27 nakshatras included
- Transit and natal combinations

### Actionable
- Specific date recommendations
- What to do and avoid
- Remedies for challenges
- Success probability ratings

### Modern
- RESTful API design
- Interactive documentation
- Natural language queries
- JSON responses

---

## 🚀 Ready to Start?

```bash
# 1. Start the API
python app.py

# 2. Test it
python test_new_endpoints.py

# 3. Explore
http://localhost:8000/docs
```

**Happy Predicting! 🔮✨**

---

*Made with ❤️ using FastAPI, Swiss Ephemeris, and Vedic Astrology wisdom*
