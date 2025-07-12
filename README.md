📊 Dynamic Pricing for Urban Parking Lots

A real-time, data-driven pricing engine that dynamically adjusts urban parking prices based on demand, occupancy, traffic, special days, and competitor behavior. This project uses Pathway for real-time data streaming and Bokeh for visualization.

🚀 Tech Stack

Programming  -  Python 3.11

Data Handling  -  Pandas, NumPy

Real-Time Engine  -  Pathway

Visualization  -  Bokeh

Mapping & Distance  -  Haversine Formula

Environment  -  Google Colab

+------------------------+
|  Dataset (CSV Format) |
+------------------------+
            |
            v
+------------------------+
|  Preprocessing Layer   |  <- Clean traffic strings, map vehicle weights
+------------------------+
            |
            v
+------------------------+
| Real-Time Ingestion    |
| Pathway CSV Reader     |
+------------------------+
            |
            v
+------------------------+
| Pathway Logic          |
| - Compute OccupancyRate|
| - Map VehicleType      |
| - Demand Calculation   |
| - Price Derivation     |
+------------------------+
            |
            v
+------------------------+
| Stream Output Writer   |
| JSONL Output File      |
+------------------------+
            |
            v
+------------------------+
|  Bokeh Visualization   |
| - Line plots per lot   |
| - Price comparisons



📈 Models Implemented

✅ Model 1: Linear Pricing

Formula: Price_t+1 = Price_t + α * (Occupancy / Capacity)
Baseline model for simple elasticity

✅ Model 2: Demand-Based Pricing

Demand Function:  Demand = α * (OccupancyRate) + β * (QueueLengthNorm) - γ * (Traffic) + δ * (IsSpecialDay) + ε * (VehicleTypeWeight)
Price Function:  Price = BasePrice * (1 + λ * NormalizedDemand)

✅ Model 3: Competitive Pricing

Haversine-based competitor lookup
Adjust price based on nearby competitor's price & occupancy

📊 Real-Time Visualization

Implemented with Bokeh
Dynamic pricing line plots by parking lot ID
Supports top N busiest parking lots
Color-coded legends with auto-scaling

📌 Assumptions

Traffic data is mapped to numerical values
Queue length and demand normalized to 0-1
Nearby lots identified within 0.5 km
