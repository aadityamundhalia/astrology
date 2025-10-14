# 🌟 Vedic Astrology API - Complete Endpoint Guide

## Overview

This API provides **real Vedic astrology calculations** using Swiss Ephemeris (NASA-grade astronomical calculations). All planetary positions, transits, and house calculations are based on actual astronomy, not random data.

**Base URL**: `http://192.168.0.200:8087`

---

## 📊 Available Endpoints

### 1. **Daily Horoscope** 
`POST /horoscope/daily`

Get personalized daily predictions based on your birth chart and today's transits.

**Based on:**
- Moon sign (Rashi) transits
- Current planetary positions
- Daily nakshatra effects
- Chandra Lagna calculations

**Request:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "14:30",
  "place_of_birth": "New Delhi, India"
}
```

**Response includes:**
- Overall daily rating (1-10)
- Mood and energy level
- Daily advice
- Lucky colors, numbers, and times
- Favorable and cautionary areas
- Key planetary influences

---

### 2. **Weekly Horoscope**
`POST /horoscope/weekly`

Get week-ahead predictions with day-by-day insights.

**Based on:**
- Major planetary transits for the week
- Moon's weekly journey through signs
- Daily nakshatra ratings
- Weekly thematic patterns

**Request:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "14:30",
  "place_of_birth": "New Delhi, India"
}
```

**Response includes:**
- Overall weekly rating
- Weekly summary and themes
- Day-by-day highlights with Moon positions
- Best days of the week
- Area-wise focus (career, relationships, finance, health)

---

### 3. **Monthly Horoscope**
`POST /horoscope/monthly`

Get comprehensive month-ahead outlook with detailed forecasts.

**Based on:**
- Jupiter, Saturn, Mars major transits
- Sun's monthly progression
- Retrograde planet impacts
- Moon return dates

**Request:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "14:30",
  "place_of_birth": "New Delhi, India"
}
```

**Response includes:**
- Overall monthly rating
- Monthly themes and summary
- Major transit effects
- Key dates (Moon returns, significant events)
- Detailed area forecasts with advice
- Retrograde notifications
- Lucky days

---

### 4. **Love Predictions**
`POST /predictions/love`

Get romantic life predictions for a custom period.

**Request:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "14:30",
  "place_of_birth": "New Delhi, India",
  "start_date": "2025-11-01",  // Optional, defaults to today
  "end_date": "2026-05-01"     // Optional, defaults to 6 months ahead
}
```

**Response includes:**
- Month-by-month love predictions
- Venus and Moon transit effects
- Romance opportunities and timing
- Relationship advice

---

### 5. **Health Predictions**
`POST /predictions/health`

Get health and wellness predictions.

**Request:** Same format as love predictions

**Response includes:**
- Health ratings by month
- Sun and Moon transit effects
- Vulnerable periods
- Preventive advice

---

### 6. **Career Predictions**
`POST /predictions/career`

Get professional life predictions.

**Request:** Same format as love predictions

**Response includes:**
- Career opportunities by month
- Saturn and Sun transit effects
- Promotion periods
- Professional advice

---

### 7. **Wealth Predictions**
`POST /predictions/wealth`

Get financial predictions.

**Request:** Same format as love predictions

**Response includes:**
- Financial outlook by month
- Jupiter transit effects
- Income opportunities
- Investment timing advice

---

### 8. **Wildcard Predictions** 🎯
`POST /predictions/wildcard`

Get ultra-precise predictions for specific events or queries.

**Use for:**
- Specific date events (interviews, dates, purchases)
- Natural language queries
- Event success probability
- Muhurta (auspicious timing) analysis

**Request:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "14:30",
  "place_of_birth": "New Delhi, India",
  "query": "I have a job interview on December 15th, how will it go?",
  "specific_date": "2025-12-15"  // Optional, can be extracted from query
}
```

**Response includes:**
- Success probability (0-100%)
- Day-specific planetary positions
- Best time of day for the event
- Specific advice and risks
- Remedies and lucky factors

---

## 🧪 Testing

### Quick Test (Daily Horoscope):
```bash
curl -X POST "http://192.168.0.200:8087/horoscope/daily" \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "14:30",
    "place_of_birth": "New Delhi, India"
  }'
```

### Run Test Suite:
```bash
python test_horoscope_endpoints.py
```

---

## 🔬 Calculation Authenticity

### ✅ Real Astronomical Calculations:
- **Swiss Ephemeris** (NASA JPL-based)
- Planetary positions accurate to 0.001°
- Real-time transit calculations
- Actual house cusps (Placidus system)
- Precise nakshatra positions
- True retrograde detection

### 📖 Interpretive Layer:
- Traditional Vedic astrology principles
- House significations (classical texts)
- Planetary effects (Brihat Parashara Hora Shastra)
- Transit interpretations (Phaladeepika)

See `ASTROLOGY_CALCULATION_SUMMARY.md` for detailed breakdown.

---

## 📝 Input Format Requirements

### Date of Birth
- Format: `YYYY-MM-DD`
- Example: `"1990-05-15"`

### Time of Birth
- Format: `HH:MM` (24-hour)
- Example: `"14:30"` (2:30 PM)
- Precision matters for accurate Ascendant

### Place of Birth
- Use actual city/town name
- Include state/country for disambiguation
- Examples:
  - `"New Delhi, India"`
  - `"New York, USA"`
  - `"London, UK"`

### Date Ranges (Optional)
- Format: `YYYY-MM-DD`
- Start date defaults to today
- End date defaults to 6 months from start
- Can specify any custom range

---

## 🎯 Use Cases

### Personal Astrology App
```javascript
// Daily Dashboard
const dailyHoroscope = await fetch('/horoscope/daily', {
  method: 'POST',
  body: JSON.stringify(userBirthData)
});

// Show mood, lucky colors, advice
```

### Event Planning
```javascript
// Check if date is auspicious for wedding
const prediction = await fetch('/predictions/wildcard', {
  method: 'POST',
  body: JSON.stringify({
    ...userBirthData,
    query: "Wedding on June 15th",
    specific_date: "2026-06-15"
  })
});

// Get success probability and best timing
```

### Relationship Compatibility
```javascript
// Get 6-month love forecast
const loveForecast = await fetch('/predictions/love', {
  method: 'POST',
  body: JSON.stringify({
    ...userBirthData,
    start_date: "2025-11-01",
    end_date: "2026-05-01"
  })
});
```

---

## 🚀 Deployment

### Docker Compose (Current)
```bash
# Build and start
sudo docker compose up -d --build

# Restart after code changes
sudo docker compose restart

# View logs
sudo docker compose logs -f

# Stop
sudo docker compose down
```

### Environment
- Python 3.11+
- FastAPI
- Swiss Ephemeris (pyswisseph)
- Ephemeris data files in `ephe/` directory

---

## 📚 Additional Resources

- **API Documentation**: Auto-generated at `http://192.168.0.200:8087/docs`
- **Calculation Details**: See `ASTROLOGY_CALCULATION_SUMMARY.md`
- **Swiss Ephemeris**: https://www.astro.com/swisseph/
- **Vedic Astrology**: Traditional principles from classical texts

---

## 🔮 Endpoint Comparison

| Endpoint | Time Scope | Best For | Calculations |
|----------|-----------|----------|--------------|
| Daily | Today | Daily planning, mood check | Real-time transits |
| Weekly | 7 days ahead | Week planning | Mid-week transits |
| Monthly | Current month | Monthly outlook | Mid-month transits |
| Love | Custom range | Romance planning | Venus/Moon transits |
| Health | Custom range | Health planning | Sun/Moon/Mars transits |
| Career | Custom range | Professional planning | Saturn/Sun transits |
| Wealth | Custom range | Financial planning | Jupiter transits |
| Wildcard | Specific date | Event analysis | Event-day calculations |

---

## ⚡ Performance

- Average response time: 200-500ms
- Calculations cached where appropriate
- Ephemeris data loaded on startup
- Concurrent requests supported

---

## 🆘 Support

For issues or questions:
1. Check API docs: `/docs`
2. Review calculation summary: `ASTROLOGY_CALCULATION_SUMMARY.md`
3. Run test suite: `python test_horoscope_endpoints.py`

---

## 📄 License

See `LICENSE` file for details.

---

**Built with ❤️ using real astronomical calculations**
