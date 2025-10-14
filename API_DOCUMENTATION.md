# Vedic Astrology API - Enhanced Predictions Documentation

## 🌟 New Enhanced Endpoints (24-Month Predictions with Precise Dates)

### Overview
The API has been significantly enhanced with **precise date-based predictions for the next 24 months** and a powerful **wildcard endpoint** for specific queries. All predictions now include:
- ✅ Exact date ranges with day names
- ✅ Monthly ratings (1-10 scale)
- ✅ Best and challenging periods
- ✅ Specific remedies for difficult times
- ✅ Actionable advice (what to do and what to avoid)
- ✅ Lucky dates and timing recommendations

---

## 📍 New Prediction Endpoints

### 1. Love Predictions (24 Months)
**Endpoint:** `POST /predictions/love`

**Purpose:** Get precise love and relationship predictions for the next 24 months.

**Request Body:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "10:30",
  "place_of_birth": "Mumbai, India"
}
```

**Response Highlights:**
- Month-by-month love ratings (1-10)
- Best months for marriage/proposals/relationships
- Challenging periods and how to overcome them
- Venus transit effects (planet of love) with exact dates
- Jupiter aspects on 7th house (marriage house)
- Lucky dates for love activities
- Remedies for difficult relationship periods

**Example Use Cases:**
- "When should I get married in 2025-2026?"
- "What are my relationship prospects for next 2 years?"
- "When is good time to propose?"
- "How's my love life looking in coming months?"

---

### 2. Health Predictions (24 Months)
**Endpoint:** `POST /predictions/health`

**Purpose:** Get precise health and wellness predictions for the next 24 months.

**Request Body:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "10:30",
  "place_of_birth": "Mumbai, India"
}
```

**Response Highlights:**
- Month-by-month health ratings (1-10)
- Vulnerable periods requiring health precautions
- Best months for medical procedures/surgeries
- Sun and Moon transit effects on vitality
- 6th house (disease) and 8th house (chronic) transits
- Specific dates to be cautious about health
- Preventive measures and remedies
- Best periods for starting fitness regimes

**Example Use Cases:**
- "When should I schedule my surgery?"
- "What months should I be careful about health?"
- "Best time to start exercising?"
- "How's my health for next 2 years?"

---

### 3. Career Predictions (24 Months)
**Endpoint:** `POST /predictions/career`

**Purpose:** Get precise career and professional predictions for the next 24 months.

**Request Body:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "10:30",
  "place_of_birth": "Mumbai, India"
}
```

**Response Highlights:**
- Month-by-month career ratings (1-10)
- Best months for job changes/promotions/business starts
- Challenging periods at work and navigation strategies
- Saturn and Jupiter transits on 10th house (career)
- Sun transits for authority and recognition
- Specific dates for career decisions
- Strategies for overcoming professional obstacles
- Best timing for negotiations and interviews

**Example Use Cases:**
- "When should I ask for promotion?"
- "Good time to change jobs in next 2 years?"
- "When to start my business?"
- "How's my career for 2025-2026?"

---

### 4. Wealth Predictions (24 Months)
**Endpoint:** `POST /predictions/wealth`

**Purpose:** Get precise financial and wealth predictions for the next 24 months.

**Request Body:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "10:30",
  "place_of_birth": "Mumbai, India"
}
```

**Response Highlights:**
- Month-by-month wealth ratings (1-10)
- Best months for investments/business deals/gains
- Financial challenge periods with mitigation strategies
- Jupiter and Venus transits on 2nd house (wealth) & 11th house (gains)
- Specific dates for financial decisions
- Risk periods for investments and expenses
- Remedies for financial difficulties
- Lucky periods for monetary growth

**Example Use Cases:**
- "When should I invest in property?"
- "Good months for business deals?"
- "When will I make money in next 2 years?"
- "Should I start venture in 2025?"

---

## 🎯 Wildcard Prediction Endpoint (Most Powerful)

### 5. Wildcard - Extreme Precision for Specific Queries
**Endpoint:** `POST /predictions/wildcard`

**Purpose:** Get ultra-precise predictions for specific dates, events, and situations with detailed risk assessment and success probability.

**Request Body:**
```json
{
  "date_of_birth": "1990-05-15",
  "time_of_birth": "10:30",
  "place_of_birth": "Mumbai, India",
  "query": "I'm going on a date on October 20th 2025, what are my chances to get lucky?",
  "specific_date": "2025-10-20"  // Optional - can be extracted from query
}
```

**Response Highlights:**
- **Success Probability:** 0-100% rating with interpretation
- **Day-Specific Analysis:** All 9 planet positions on that exact date
- **Muhurta Analysis:** Best time of day (hour-level precision)
- **Risk Assessment:** Detailed risks and mitigation strategies
- **Beneficial/Malefic Influences:** What helps and what hinders
- **Lucky Factors:** Colors, numbers, directions, gemstones
- **Specific Advice:** Tailored to your exact situation
- **Remedies:** How to enhance positive outcomes

**Supported Query Types:**

#### Romance/Dating Queries
```json
{
  "query": "I'm going on a date on October 20th, what are my chances to get lucky?"
}
```

#### Job/Career Queries
```json
{
  "query": "My company is going through redundancy in December 2025, will I be safe?"
}
```
```json
{
  "query": "I have a job interview on March 15th 2025, how will it go?"
}
```

#### Safety/Health Queries
```json
{
  "query": "I'm buying a motorcycle on November 5th, will I be safe riding it?"
}
```

#### Business/Financial Queries
```json
{
  "query": "Should I sign a contract on January 15th 2026?"
}
```
```json
{
  "query": "Starting a new business on April 1st 2025, will it succeed?"
}
```

#### General Event Queries
```json
{
  "query": "Planning to propose on Valentine's Day 2025, good idea?"
}
```

**Response Structure:**
```json
{
  "query": "User's original question",
  "event_date": {
    "date": "2025-10-20",
    "day": "Monday",
    "full_date": "Monday, October 20, 2025",
    "extracted_from_query": true
  },
  "area_of_concern": "love",
  "concern_type": "romance",
  "success_probability": {
    "percentage": 75,
    "rating": "High",
    "interpretation": "Good chances for positive outcome..."
  },
  "planetary_positions_on_date": {
    "Sun": {"longitude": 202.5, "sign": "Libra", "house": 7, "nakshatra": "Swati"},
    "Moon": {"longitude": 123.8, "sign": "Cancer", "house": 4, "nakshatra": "Pushya"},
    // ... all 9 planets
  },
  "best_time_of_day": [
    {
      "time_range": "09:00 - 12:00",
      "period": "Late Morning",
      "ruling_planet": "Venus",
      "quality": "Highly Favorable",
      "recommendation": "Best time for love-related activities"
    }
  ],
  "specific_advice": [
    "High probability of success - proceed with confidence",
    "This is a favorable time for romantic matters",
    "Trust your instincts and take decisive action",
    "Express yourself authentically and openly"
  ],
  "risks_and_challenges": [
    {
      "factor": "Saturn creating obstacles",
      "risk_level": "Moderate",
      "description": "Possible delays or additional responsibilities",
      "impact_areas": ["delays", "obstacles"]
    }
  ],
  "mitigation_strategies": [
    "Be prepared for delays and have backup plans",
    "Focus on long-term thinking and discipline"
  ],
  "remedies": [
    "Wear white or pink colors on the day",
    "Carry rose quartz crystal",
    "Offer flowers at a temple"
  ],
  "lucky_factors": {
    "colors": ["White", "Silver", "Light Blue"],
    "numbers": [1, 3, 5, 7, 9],
    "direction": "East",
    "gemstone": "Pearl",
    "deity_to_worship": "Goddess Lakshmi"
  },
  "overall_recommendation": "Proceed with confidence. This is a favorable time...",
  "birth_chart_context": {
    "ascendant": "Gemini",
    "moon_sign": "Libra",
    "key_strengths": ["Venus well-placed for relationships"]
  }
}
```

---

## 📊 Response Structure for 24-Month Predictions

All 24-month prediction endpoints (love, health, career, wealth) return:

```json
{
  "area": "love",
  "prediction_period": "November 2024 to November 2026",
  "generated_at": "2024-10-14 10:30:00",
  "overview": {
    "average_rating": 7.2,
    "trend": "Improving - Things get better as time progresses",
    "best_months": [
      {
        "month": "April 2025",
        "rating": 9,
        "dates": "2025-04-01 to 2025-04-30"
      }
      // Top 3 best months
    ],
    "challenging_months": [
      {
        "month": "September 2025",
        "rating": 3,
        "dates": "2025-09-01 to 2025-09-30"
      }
      // Top 3 challenging months
    ],
    "overall_guidance": "This is a good period for love. Make steady progress with balanced approach..."
  },
  "monthly_predictions": [
    {
      "month": "November 2024",
      "date_range": {
        "start": "2024-11-01",
        "end": "2024-11-30",
        "start_day": "Friday, November 01, 2024",
        "end_day": "Saturday, November 30, 2024"
      },
      "rating": 8,
      "quality": "Excellent",
      "score": 6,
      "advice": "This is a highly favorable month for love. Take initiative and make important decisions.",
      "key_transits": [
        {
          "planet": "Venus",
          "sign": "Scorpio",
          "house": 7,
          "effect": "positive",
          "description": "Venus transiting 7th house brings harmony in relationships"
        }
      ],
      "best_dates": [
        {
          "date": "2024-11-15",
          "day": "Friday",
          "full_date": "Friday, November 15, 2024",
          "quality_score": 9,
          "moon_sign": "Taurus",
          "moon_nakshatra": "Rohini",
          "recommendation": "Favorable day for important activities"
        }
      ],
      "remedies": [
        "Continue with positive momentum",
        "Express gratitude for favorable period"
      ],
      "what_to_do": [
        "Express your feelings openly",
        "Plan romantic dates or getaways",
        "Propose or take relationship to next level"
      ],
      "what_to_avoid": [
        "Overconfidence",
        "Complacency"
      ]
    }
    // ... 23 more months
  ],
  "birth_chart_summary": {
    "ascendant": "Gemini",
    "moon_sign": "Libra",
    "sun_sign": "Taurus"
  }
}
```

---

## 🎨 Understanding Ratings

### Rating Scale (1-10)
- **9-10:** Exceptional - Best time for major decisions and actions
- **7-8:** Excellent - Very favorable, proceed with confidence
- **5-6:** Good - Positive period with some caution needed
- **4:** Average - Mixed results, maintain balance
- **2-3:** Challenging - Exercise caution, focus on damage control
- **1:** Very Difficult - Postpone if possible, extreme caution required

### Quality Indicators
- **Excellent:** Highly favorable, take initiative
- **Good:** Positive period, good for moderate actions
- **Average:** Mixed results, focus on stability
- **Challenging:** Difficult period, exercise caution

---

## 🔮 Key Features

### 1. Precise Date Interpretation
Every prediction includes:
- Start and end dates in YYYY-MM-DD format
- Day names (Monday, Tuesday, etc.)
- Full human-readable dates
- Best specific dates within each month

### 2. Actionable Advice
For every period:
- **What to Do:** Specific actions to take
- **What to Avoid:** Things to stay away from
- **Remedies:** Astrological remedies for challenges
- **Strategies:** How to overcome difficult times

### 3. Transit Analysis
Detailed planetary transits with:
- Planet name and position
- Sign and house placement
- Effect (positive/challenging/mixed)
- Description of impact
- Areas affected

### 4. Best Dates Calculation
For each month, get:
- Top 3 best dates
- Quality scores (1-10)
- Moon sign and nakshatra
- Specific recommendations

---

## 🛠️ Technical Details

### Date Extraction
The wildcard endpoint can automatically extract dates from natural language:
- "October 20th" → 2024-10-20
- "20th October 2025" → 2025-10-20
- "Dec 15, 2025" → 2025-12-15
- "15/12/2025" → 2025-12-15

### Calculation Depth
All predictions use:
- ✅ Transit positions for all 9 planets
- ✅ House cusps calculation (Placidus system)
- ✅ Nakshatra (lunar mansion) analysis
- ✅ Ayanamsa correction (Lahiri)
- ✅ Dignity analysis (exaltation, debilitation)
- ✅ House significations and planetary effects

---

## 📝 Example API Calls

### cURL Examples

#### 1. Get 24-Month Love Predictions
```bash
curl -X POST http://localhost:8000/predictions/love \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "10:30",
    "place_of_birth": "Mumbai, India"
  }'
```

#### 2. Get Wildcard Prediction for Specific Date
```bash
curl -X POST http://localhost:8000/predictions/wildcard \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "10:30",
    "place_of_birth": "Mumbai, India",
    "query": "I have a job interview on March 15th 2025, how will it go?"
  }'
```

#### 3. Get Career Predictions
```bash
curl -X POST http://localhost:8000/predictions/career \
  -H "Content-Type: application/json" \
  -d '{
    "date_of_birth": "1990-05-15",
    "time_of_birth": "10:30",
    "place_of_birth": "London, UK"
  }'
```

### Python Examples

```python
import requests

# 1. Love Predictions
response = requests.post(
    "http://localhost:8000/predictions/love",
    json={
        "date_of_birth": "1990-05-15",
        "time_of_birth": "10:30",
        "place_of_birth": "Mumbai, India"
    }
)
love_predictions = response.json()

# 2. Wildcard Query
response = requests.post(
    "http://localhost:8000/predictions/wildcard",
    json={
        "date_of_birth": "1990-05-15",
        "time_of_birth": "10:30",
        "place_of_birth": "New York, USA",
        "query": "I'm buying a motorcycle on November 5th, will I be safe?",
        "specific_date": "2024-11-05"
    }
)
wildcard_result = response.json()

print(f"Success Probability: {wildcard_result['success_probability']['percentage']}%")
print(f"Recommendation: {wildcard_result['overall_recommendation']}")
```

---

## 🌟 Use Case Examples

### Personal Life Planning
- **Marriage Timing:** Check best months in next 2 years for marriage
- **Health Monitoring:** Know when to be careful about health
- **Career Moves:** Plan job changes or business launches
- **Financial Decisions:** Time investments and major purchases

### Event Planning
- **Date Selection:** Choose best date for important events
- **Risk Assessment:** Evaluate safety for activities
- **Success Probability:** Know chances before taking action
- **Timing Optimization:** Find best time of day for activities

### Daily Guidance
- **Important Meetings:** Check planetary support for meetings
- **Travel Planning:** Assess safety for travel dates
- **Relationship Actions:** Time proposals, dates, discussions
- **Business Launches:** Choose auspicious dates for launches

---

## 🔧 Error Handling

All endpoints return appropriate HTTP status codes:
- **200:** Success
- **400:** Bad request (invalid input)
- **404:** Place not found in geocoding
- **500:** Server error (calculation failure)

Error response format:
```json
{
  "detail": "Error description"
}
```

---

## 📚 Additional Resources

### Vedic Astrology Concepts
- **Houses (Bhavas):** 12 sectors representing life areas
- **Signs (Rashis):** 12 zodiac signs
- **Planets (Grahas):** 9 celestial bodies affecting life
- **Nakshatras:** 27 lunar mansions for precise timing
- **Transits (Gochara):** Current planet positions
- **Ayanamsa:** Correction for precession of equinoxes

### Planet Significations
- **Sun:** Authority, vitality, father, government
- **Moon:** Mind, emotions, mother, public
- **Mars:** Energy, courage, property, siblings
- **Mercury:** Intelligence, business, communication
- **Jupiter:** Wisdom, wealth, children, spirituality
- **Venus:** Love, luxury, relationships, arts
- **Saturn:** Discipline, delays, longevity, karma
- **Rahu:** Sudden events, foreign, materialism
- **Ketu:** Spirituality, detachment, moksha

---

## 🚀 Getting Started

1. **Start the API:**
```bash
cd /home/aaditya/ai/vedastro
python app.py
```

2. **Access Documentation:**
```
http://localhost:8000/docs
```

3. **Test Endpoints:**
Use the interactive API docs at `/docs` or use curl/Python as shown above.

---

## 📞 Support

For questions or issues with the enhanced prediction endpoints, refer to:
- API Documentation: `http://localhost:8000/docs`
- This guide: `API_DOCUMENTATION.md`
- Source code: `app.py` and `predictions.py`

---

**Version:** 2.0 Enhanced with 24-Month Predictions & Wildcard Endpoint  
**Last Updated:** October 2024
