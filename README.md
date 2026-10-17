# Hotel Booking Demand Analysis

## Project Overview

This project is my **3rd Semester Data Analytics Project at AltSchool Africa**.

The project analyzes the **Hotel Booking Demand dataset** to understand hotel booking behavior, cancellation patterns, customer characteristics, market segments, stay duration, seasonal demand, and estimated revenue.

The analysis follows an end-to-end data analytics process, starting with raw data inspection and quality assessment, followed by data cleaning, exploratory data analysis, transformation, visualization, interpretation, and business recommendations.

## Dataset

The dataset contains **119,390 hotel booking records** covering two hotel types:

- City Hotel
- Resort Hotel

The data includes information about bookings, arrival dates, length of stay, guests, room types, market segments, customer types, cancellations, ADR, previous booking history, and reservation status.

## Data Cleaning

Before performing the analysis, the dataset was examined to identify data quality problems that could affect the results.

The main issues identified were:

- **31,994 duplicate records**
- Missing values in selected columns
- Records with no recorded guests
- A negative ADR value
- Date fields stored in an unsuitable format

The duplicate records were removed to prevent repeated bookings from affecting the analysis.

Missing values were handled according to the meaning of each column. Numerical guest information was handled using the median, while missing categorical information such as country, agent, and company was assigned `Unknown` where appropriate.

Zero-guest records were investigated rather than automatically deleting every booking with zero adults. Records with **zero adults, zero children, and zero babies** were removed because there was no recorded guest associated with the booking. Records with children or babies were retained because they could still represent valid bookings.

One record had a negative ADR of **-6.38**. Because ADR represents the average daily room rate, a negative value is not meaningful for revenue analysis. The record was removed after investigating its booking details.

The reservation status date was also converted to a proper datetime format.

After cleaning and validation, the dataset contained **87,228 records**.

## Exploratory Data Analysis

Exploratory analysis was performed to understand the structure and behavior of the cleaned data.

The analysis examined:

- Booking volume by hotel
- Cancellation behavior and cancellation rates
- Arrival-month demand
- Market segments
- Customer types
- Meal types
- Distribution channels
- Room types
- Deposit types
- Countries
- Lead time
- Length of stay
- Special requests
- Numerical relationships

## Data Transformation

Additional variables were created from the existing data to make the analysis more meaningful.

### Total Stay Nights

Weekend and weekday nights were combined to create `total_stay_nights`, providing one measure of the complete stay duration.

The average stay was approximately **3.63 nights**, while the longest recorded stay was **69 nights**.

### Total Guests

Adults, children, and babies were combined into `total_guests` to provide a clearer measure of the number of guests associated with each booking.

### Estimated Revenue

Estimated revenue was calculated as:

`ADR × Total Stay Nights`

This was used as an analytical estimate rather than actual recorded hotel revenue.

### Total Previous Bookings

Previous cancellations and previous non-canceled bookings were combined to measure the customer's total previous booking history.

### Booking Status

The cancellation indicator was transformed into a more readable `booking_status` variable containing:

- Not Canceled
- Canceled

### Stay Length Category

Bookings were grouped into:

- 1–2 nights
- 3–5 nights
- 6–7 nights
- 8+ nights

This made it easier to compare booking behavior by length of stay.

## Key Insights

### Booking Demand

City Hotel recorded **53,273 bookings**, compared with **33,955 bookings** for Resort Hotel.

This shows that City Hotel had substantially higher booking demand in the cleaned dataset.

### Cancellation Behavior

There were **24,008 canceled bookings** and **63,220 bookings that were not canceled**, giving an overall cancellation rate of **27.52%**.

City Hotel had a higher cancellation rate of **30.10%**, compared with **23.48%** for Resort Hotel.

Online TA brought 59% of bookings but about 76% of all cancellations (35.4% cancellation rate).

This indicates that cancellation management should be considered at both the hotel and booking-channel level.

### Seasonal Demand

Booking demand varied considerably across arrival months.

**August** recorded the highest booking volume with **11,242 bookings**, while **January** recorded the lowest with **4,685 bookings**.

The difference suggests clear seasonal variation in hotel demand.

### Market Segments

Online TA was the dominant market segment, generating **51,553 bookings**.

Offline TA/TO followed with **13,854 bookings**, while Direct bookings recorded **11,780**.

Although Online TA generated the highest booking volume, its relatively high cancellation rate shows that booking volume alone is not enough to evaluate channel performance.

### Stay Duration

The **3–5 night** category recorded the highest booking volume with **38,121 bookings**, followed by **1–2 nights** with **32,902 bookings**.

Together, the 1–5 night categories accounted for **71,023 bookings**, showing that shorter stays were more common in the dataset.

### Estimated Revenue

City Hotel generated estimated revenue of **18,759,633.36**, compared with **15,686,621.57** for Resort Hotel,but the Resort earns more per booking (about 462 vs 352)

City Hotel therefore generated **3,073,011.79 more estimated revenue**.

The difference may be influenced by City Hotel's higher booking volume as well as differences in ADR and length of stay.

### Correlation Analysis

The correlation heatmap showed several strong relationships.

The strongest included:

- Weekday nights and total stay nights: **0.95**
- Adults and total guests: **0.80**
- Weekend nights and total stay nights: **0.78**
- Total stay nights and estimated revenue: **0.75**
- Weekday nights and estimated revenue: **0.71**
- ADR and estimated revenue: **0.57**

The strong relationship between total stay nights and estimated revenue indicates that length of stay is an important factor associated with estimated revenue.

Correlation, however, does not prove causation.

## Business Recommendations

Based on the findings, the analysis recommends that hotel management:

- Monitor cancellation behavior by hotel and booking channel, with particular attention to City Hotel and Online TA.
- Use historical seasonal booking patterns to support staffing, room availability, capacity planning, and promotional decisions.
- Evaluate booking channels using both booking volume and cancellation performance.
- Consider ADR and length of stay together when evaluating revenue performance.
- Investigate unusual financial values such as negative ADR records at the source to improve data quality.
- Explore suitable strategies for encouraging longer stays where this aligns with customer demand and room availability.

## Visualizations

The analysis uses a range of visualizations to communicate the findings, including:

- Booking volume by hotel type
- Booking outcomes by hotel type
- Cancellation rate by hotel type
- Monthly booking trends
- Horizontal market-segment comparison
- Booking volume by stay length
- Estimated revenue by hotel
- Correlation heatmap

## Project Outcome

This project provided practical experience in taking a raw dataset through the complete analytics process.

Rather than focusing only on producing charts, the project involved identifying and investigating data-quality issues, making justified cleaning decisions, creating useful analytical variables, interpreting relationships in the data, and translating the results into business insights and recommendations.

## 📁 Repository Structure
```
├── Hotel_Booking_Demand_Analysis.ipynb
├── Hotel_Booking_Demand_Analysis_Report.pdf
├── data/
│   └── hotel_bookings.csv
└── README.md

## Skills Demonstrated

**Python | Pandas | Seaborn | Matplotlib | Data Cleaning | Exploratory Data Analysis | Data Transformation | Feature Engineering | Data Visualization | Correlation Analysis | Business Analysis**

## 👤 Author
**Zainab Danjuma**
