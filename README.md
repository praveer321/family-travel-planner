# 👨‍👩‍👧‍👦 Family Travel Planner

A comprehensive multi-agent travel planning system built with CrewAI that specializes in organizing perfect family trips with children. The system uses 5 specialized AI agents working together to handle every aspect of your family vacation planning.

## ✨ Features

- **Smart Weather Analysis** - Get detailed weather forecasts and activity recommendations
- **Family Budget Optimization** - Find the best group deals and child-friendly pricing
- **Perfect Accommodations** - Locate family-friendly stays with kitchens and safety features
- **Kid-Friendly Activities** - Curated activities that work for mixed age groups
- **Complete Itinerary Planning** - Day-by-day schedules with nap times and backup plans

## 🤖 How It Works

The Family Travel Planner uses 5 specialized AI agents that work sequentially, each building on the previous agent's work:

## 🔄 Agent Workflow

```
🌤️ Weather Agent → 💰 Budget Agent → 🏠 Accommodation Agent → 🎢 Activities Agent → 📋 Coordinator Agent
```

### Sequential Process:
1. **Weather Agent** analyzes conditions and creates weather recommendations
2. **Budget Agent** uses weather data to optimize costs and find deals  
3. **Accommodation Agent** uses weather + budget insights to find perfect stays
4. **Activities Agent** uses all previous data to plan family-friendly activities
5. **Coordinator Agent** synthesizes everything into a complete itinerary

### What Each Agent Produces:

| Agent | Output |
|-------|--------|
| 🌤️ **Weather** | Daily forecasts, activity timing, packing lists |
| 💰 **Budget** | Group discounts, child pricing, cost breakdown |
| 🏠 **Accommodation** | Multi-room options, kitchen facilities, child safety |
| 🎢 **Activities** | Age-appropriate fun, group activities, indoor backups |
| 📋 **Coordinator** | Day-by-day plans, group logistics, emergency info |

## 🚀 Quick Start

### Prerequisites

```bash
pip install crewai python-dotenv
```

### Environment Setup

Create a `.env` file in your project root:

```env
# Add your Gemini API key
GOOGLE_API_KEY=your_gemini_api_key_here
```

### Basic Usage

```python
from family_travel_planner import create_travel_plan

# Plan your family trip
result = create_travel_plan(
    destination="Queenstown, New Zealand",
    travel_dates="October 15-22, 2025",
    budget="$10,000 AUD",
    departure_city="Sydney, Australia",
    group_size="6 adults, 2 children",
    kids_info="Ages 3 and 10 - need child-friendly activities",
    traveler_preferences="Adventure activities for adults, family-friendly attractions"
)

print(result)
```

## 🎯 Agent Breakdown

### 1. 🌤️ Weather Research Specialist
**Role**: Analyzes weather conditions and seasonal patterns
- Daily weather forecasts for your travel dates
- Best times for outdoor activities
- Weather-appropriate packing suggestions
- Indoor alternatives for rainy days

### 2. 💰 Budget Analyst
**Role**: Optimizes family travel costs and finds deals
- Group flight pricing from your departure city
- Family and group discounts
- Child pricing considerations
- Per-person vs total cost analysis
- Money-saving strategies

### 3. 🏠 Accommodation Expert
**Role**: Finds perfect family-friendly lodging
- Multi-room setups for large groups
- Kitchen facilities for family meals
- Child safety features and amenities
- Airbnb vs hotel recommendations
- Location convenience for activities

### 4. 🎢 Activities Specialist
**Role**: Curates age-appropriate family fun
- Activities suitable for different age groups
- Group capacity and discounts
- Balance of adult interests and kid-friendly options
- Attention span and energy level considerations
- Safety requirements for children

### 5. 📋 Master Coordinator
**Role**: Creates the final comprehensive itinerary
- Day-by-day detailed scheduling
- Group logistics and coordination
- Backup plans for weather or meltdowns
- Nap times and rest periods
- Emergency contacts and safety info

## 📊 Sample Output

The system generates a comprehensive travel plan including:

- **Weather-Optimized Schedule**: Activities planned around weather patterns
- **Budget Breakdown**: Detailed costs per person and total group expenses
- **Accommodation Options**: 3-5 top family-friendly stay options
- **Daily Itineraries**: Hour-by-hour plans with child considerations
- **Packing Lists**: Weather-appropriate items for adults and kids
- **Emergency Planning**: Backup activities and safety information

## 🔧 Customization

### Modify Agent Behavior

Each agent can be customized by updating their `backstory` and `goal`:

```python
weather_agent = Agent(
    role="Weather Research Specialist",
    goal="Your custom goal here",
    backstory="Your custom expertise description",
    # ... other parameters
)
```

### Add New Agents

Create additional specialized agents:

```python
transport_agent = Agent(
    role="Transportation Specialist",
    goal="Optimize group transportation options",
    backstory="Expert in family-friendly transport solutions",
    llm=llm,
    verbose=False
)
```

## 🌟 Example: Queenstown Family Adventure

```python
# Perfect for a multi-generational family trip
result = create_travel_plan(
    destination="Queenstown, New Zealand",
    travel_dates="October 15-22, 2025",
    budget="$10,000 AUD",
    departure_city="Sydney, Australia",
    group_size="6 adults, 2 children",
    kids_info="3-year-old (needs naps) and 10-year-old (more adventurous)",
    traveler_preferences="""
    - Adventure activities for adults (bungee, wine tours)
    - Family-friendly attractions and playgrounds
    - Scenic photography spots
    - Airbnb with kitchen for group meals
    - Balance of excitement and relaxation
    """
)
```

## 📝 Tips for Best Results

### 🎯 Be Specific with Group Details
- Clearly specify ages of children
- Mention any special needs or preferences
- Include mobility considerations

### 💡 Detailed Preferences Help
- List specific interests for adults
- Mention dietary requirements
- Specify accommodation preferences (hotel vs Airbnb)

### 📅 Flexible with Dates
- Consider shoulder seasons for better deals
- Allow buffer days for travel fatigue
- Account for school holiday periods

## 🔍 Troubleshooting

### Common Issues

**ValidationError: Missing 'goal' field**
- Ensure all agents have both `role` and `goal` parameters

**API Key Issues**
- Verify your `.env` file has the correct `GOOGLE_API_KEY`
- Check that the key has proper permissions

**Long Execution Times**
- Large groups and complex preferences take longer
- Consider reducing `max_iter` for faster results

## 🤝 Contributing

We welcome contributions! Areas for improvement:
- Additional specialized agents (transport, dining, etc.)
- Integration with booking APIs
- Real-time pricing updates
- Multi-destination trip planning

## 📄 License

MIT License - feel free to use and modify for your family travel needs!

---

*Happy family travels! 🌍✈️👨‍👩‍👧‍👦*