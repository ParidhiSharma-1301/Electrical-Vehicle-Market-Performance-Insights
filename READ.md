ELECTRIC VEHICLE MARKET PERFORMANCE AND INSIGHTS

1. Introduction

Electric Vehicles (EVs) are becoming increasingly popular due to rising environmental concerns, technological advancements, and the need to reduce dependence on fossil fuels. Electric vehicles use electric motors and batteries instead of relying entirely on conventional petrol or diesel engines.

The Electric Vehicle Market Performance and Insights project focuses on analyzing electric vehicle sales, comparing manufacturer performance, and understanding market growth using Python. Data analysis and visualization techniques are used to identify trends and generate meaningful insights.

2. Objective of the Project

The main objectives of this project are:

1. To analyze electric vehicle market performance over different years.
2. To compare the sales performance of different EV manufacturers.
3. To calculate yearly sales growth.
4. To visualize market trends using graphs and charts.
5. To identify the top-performing manufacturer in the sample dataset.
6. To understand how Python can be used for market research and business decision-making.

3. Tools and Technologies Used

- Programming Language: Python
- Pandas: Used for data manipulation and analysis.
- Matplotlib: Used to create graphs and charts.
- Visual Studio Code: Used to write and execute the Python program.
- Dataset: Sample electric vehicle sales data containing years, manufacturers, and sales figures.

4. Project Overview

This project analyzes electric vehicle sales data to understand market performance and growth trends. The dataset contains information about four manufacturers: Tata, MG, Mahindra, and Hyundai, for the years 2023, 2024, and 2025.

Python is used to organize the data, calculate total yearly sales, compare manufacturer performance, and calculate the percentage growth in sales. The results are presented through bar charts, line charts, and pie charts.

The project demonstrates how data analysis can help identify sales trends, compare manufacturers, and understand the competitive position of different companies in the electric vehicle market.

Note: The dataset used in this demonstration is illustrative and does not represent official manufacturer sales figures.

5. Methodology

The project follows these steps:

Step 1: Data Collection

Sample electric vehicle sales data is created using Python. It includes the year, manufacturer name, and sales figures.

Step 2: Data Processing

The Pandas library is used to organize the data into a DataFrame and group sales figures by year and manufacturer.

Step 3: Data Analysis

The program calculates total yearly sales, total sales by manufacturer, and yearly sales growth.

Step 4: Data Visualization

Matplotlib is used to generate bar charts, line charts, and pie charts to present the results visually.

Step 5: Insight Generation

The results are analyzed to identify sales trends, compare manufacturers, and determine which manufacturer has the highest total sales in the sample dataset.

6. Key Features of the Project

1. Year-wise analysis of electric vehicle sales.
2. Manufacturer-wise sales comparison.
3. Calculation of yearly sales growth percentage.
4. Identification of the top-performing manufacturer in the sample data.
5. Graphical representation of sales trends.
6. Visualization of manufacturer sales share.
7. Simple and understandable Python implementation.

7. Data Analysis and Insights

The sample dataset contains sales figures for four manufacturers over three years.

The total sales for each year are:

- 2023: 11,000
- 2024: 15,000
- 2025: 20,000

The sample data shows an increase in total sales from 2023 to 2025. The manufacturer-wise analysis identifies Tata as the leading manufacturer in this particular dataset.

The line chart shows the change in sales over time, the bar chart compares manufacturer performance, and the pie chart illustrates each manufacturer's share of total sample sales.

These results demonstrate how data analysis can be used to understand market trends. However, conclusions about the actual electric vehicle market require reliable, real-world sales data.

8. Applications of the Project

- Electric vehicle market research.
- Sales performance analysis.
- Manufacturer comparison.
- Business planning and decision-making.
- Identification of market growth trends.
- Educational learning in Python and data visualization.

9. Advantages of the Project

1. It provides a simple way to analyze sales data.
2. It uses Python libraries commonly used in data analytics.
3. It presents information through easy-to-understand graphs.
4. It helps develop programming and analytical skills.
5. It can be expanded using real-world datasets.
6. It demonstrates the practical application of data analysis in the automotive industry.

10. Limitations of the Project

1. The current dataset contains illustrative sales figures.
2. The analysis includes only four manufacturers.
3. The dataset covers only three years.
4. The results cannot be treated as official market statistics.
5. More detailed analysis would require additional information, such as vehicle prices, charging infrastructure, battery capacity, and regional sales.

11. Future Scope

The project can be improved by using real electric vehicle market datasets. Additional features may include interactive dashboards, state-wise sales analysis, price comparisons, charging station analysis, and machine learning models for sales forecasting.

The project can also be extended to compare electric vehicles with conventional petrol and diesel vehicles to understand changes in consumer preferences and transportation trends.

12. Conclusion

The Electric Vehicle Market Performance and Insights project demonstrates the use of Python for analyzing and visualizing electric vehicle sales data. By using Pandas and Matplotlib, the project calculates yearly sales, compares manufacturer performance, and identifies trends through graphical representations.

The project provides practical knowledge of data analysis, data visualization, and basic business intelligence. With the addition of accurate real-world data, it can become a useful tool for studying the growth and performance of the electric vehicle industry.

Code For The Dashboard-
import streamlit as st
import pandas as pd
import plotly.express as px

st.set_page_config(
    page_title="EV Market Performance and Insights",
    page_icon="🚗",
    layout="wide"
)

st.title("🚗 Electric Vehicle Market Performance and Insights")
st.markdown(
    "Analyze EV sales, manufacturers, customer ratings, "
    "battery types, vehicle range, and regional performance."
)

# -----------------------------------
# 1. Sample dataset
# -----------------------------------

data = {
    "Manufacturer": [
        "Tata Motors", "MG", "Mahindra", "Hyundai",
        "Tesla", "BYD", "BMW", "Kia",
        "Tata Motors", "MG", "Mahindra", "Hyundai",
        "Tesla", "BYD", "BMW", "Kia"
    ],
    "Vehicle Category": [
        "Compact SUV", "Sedan", "SUV", "Hatchback",
        "Luxury Sedan", "SUV", "Luxury Sedan", "Compact SUV",
        "E-Bus", "E-Truck", "3-Wheeler", "Crossover",
        "Full SUV", "Pickup", "Sports Car", "Van/MPV"
    ],
    "Market Region": [
        "South Asia", "Europe", "South Asia", "Europe",
        "North America", "Asia Pacific", "Europe", "Asia Pacific",
        "South Asia", "North America", "South Asia", "Europe",
        "North America", "Asia Pacific", "Europe", "Middle East"
    ],
    "Battery Type": [
        "LFP", "NMC", "LFP", "NCA",
        "NCA", "LFP", "NMC", "NMC",
        "Solid-State", "LFP", "Sodium-Ion", "NMC",
        "NCA", "LFP", "Solid-State", "Sodium-Ion"
    ],
    "Annual Sales Units": [
        850000, 620000, 710000, 540000,
        950000, 1200000, 460000, 390000,
        120000, 85000, 160000, 480000,
        780000, 190000, 110000, 250000
    ],
    "Customer Rating": [
        4.2, 4.0, 4.1, 3.9,
        4.3, 4.4, 4.2, 4.0,
        3.8, 3.7, 4.1, 4.0,
        4.2, 3.9, 4.1, 3.8
    ],
    "Range Km": [
        450, 500, 480, 350,
        650, 600, 550, 420,
        250, 300, 180, 520,
        620, 400, 580, 380
    ],
    "Latitude": [
        22.3, 51.5, 19.1, 37.6,
        37.4, 23.1, 48.1, 37.5,
        28.6, 40.7, 22.7, 48.8,
        30.3, 31.2, 45.5, 25.2
    ],
    "Longitude": [
        73.2, -0.1, 72.9, 127.0,
        -122.1, 113.3, 11.6, 127.0,
        77.2, -74.0, 75.9, 2.3,
        -97.7, 121.5, 9.2, 55.3
    ]
}

df = pd.DataFrame(data)

# -----------------------------------
# 2. Sidebar filters
# -----------------------------------

st.sidebar.header("Dashboard Filters")

manufacturers = st.sidebar.multiselect(
    "Select Manufacturer",
    options=sorted(df["Manufacturer"].unique()),
    default=sorted(df["Manufacturer"].unique())
)

categories = st.sidebar.multiselect(
    "Select Vehicle Category",
    options=sorted(df["Vehicle Category"].unique()),
    default=sorted(df["Vehicle Category"].unique())
)

regions = st.sidebar.multiselect(
    "Select Market Region",
    options=sorted(df["Market Region"].unique()),
    default=sorted(df["Market Region"].unique())
)

filtered_df = df[
    df["Manufacturer"].isin(manufacturers)
    & df["Vehicle Category"].isin(categories)
    & df["Market Region"].isin(regions)
]

if filtered_df.empty:
    st.warning("No data matches your filters.")
    st.stop()

# -----------------------------------
# 3. Summary metrics
# -----------------------------------

total_sales = filtered_df["Annual Sales Units"].sum()
avg_rating = filtered_df["Customer Rating"].mean()
avg_range = filtered_df["Range Km"].mean()
total_manufacturers = filtered_df["Manufacturer"].nunique()

c1, c2, c3, c4 = st.columns(4)

c1.metric("Total Sales Units", f"{total_sales:,.0f}")
c2.metric("Average Rating", f"{avg_rating:.2f}/5")
c3.metric("Average Range", f"{avg_range:.0f} km")
c4.metric("Manufacturers", total_manufacturers)

st.divider()

# -----------------------------------
# 4. Vehicle Sales by Category
# -----------------------------------

st.subheader("Vehicle Sales by Category")

category_sales = (
    filtered_df.groupby("Vehicle Category", as_index=False)
    ["Annual Sales Units"].sum()
    .sort_values("Annual Sales Units")
)

fig1 = px.bar(
    category_sales,
    x="Annual Sales Units",
    y="Vehicle Category",
    orientation="h",
    title="Vehicle Sales by Category",
    color="Annual Sales Units",
    color_continuous_scale="Blues"
)

# -----------------------------------
# 5. Manufacturer Sales
# -----------------------------------

manufacturer_sales = (
    filtered_df.groupby("Manufacturer", as_index=False)
    ["Annual Sales Units"].sum()
    .sort_values("Annual Sales Units", ascending=False)
)

fig2 = px.bar(
    manufacturer_sales,
    x="Annual Sales Units",
    y="Manufacturer",
    orientation="h",
    title="Manufacturer Sales",
    color="Annual Sales Units",
    color_continuous_scale="Teal"
)

fig2.update_layout(yaxis={"categoryorder": "total ascending"})

# -----------------------------------
# 6. Customer Rating
# -----------------------------------

ratings = (
    filtered_df.groupby("Manufacturer", as_index=False)
    ["Customer Rating"].mean()
    .sort_values("Customer Rating")
)

fig3 = px.bar(
    ratings,
    x="Customer Rating",
    y="Manufacturer",
    orientation="h",
    title="Customer Rating by Manufacturer",
    range_x=[0, 5],
    color="Customer Rating",
    color_continuous_scale="Blues"
)

# -----------------------------------
# 7. Regional Sales
# -----------------------------------

regional_sales = (
    filtered_df.groupby("Market Region", as_index=False)
    ["Annual Sales Units"].sum()
    .sort_values("Annual Sales Units")
)

fig4 = px.bar(
    regional_sales,
    x="Annual Sales Units",
    y="Market Region",
    orientation="h",
    title="Regional Sales",
    color="Annual Sales Units",
    color_continuous_scale="Blues"
)

# -----------------------------------
# 8. EV Sales by Battery Type
# -----------------------------------

battery_sales = (
    filtered_df.groupby("Battery Type", as_index=False)
    ["Annual Sales Units"].sum()
    .sort_values("Annual Sales Units")
)

fig5 = px.bar(
    battery_sales,
    x="Annual Sales Units",
    y="Battery Type",
    orientation="h",
    title="EV Sales by Battery Type",
    color="Annual Sales Units",
    color_continuous_scale="Teal"
)

# -----------------------------------
# 9. Range Category
# -----------------------------------

range_data = filtered_df.copy()

range_data["Range Category"] = pd.cut(
    range_data["Range Km"],
    bins=[0, 250, 400, 500, 700],
    labels=[
        "Short Range",
        "Medium Range",
        "Long Range",
        "Extended Range"
    ],
    include_lowest=True
)

range_sales = (
    range_data.groupby(
        "Range Category", observed=False, as_index=False
    )["Annual Sales Units"].sum()
)

fig6 = px.bar(
    range_sales,
    x="Annual Sales Units",
    y="Range Category",
    orientation="h",
    title="Sales by Vehicle Range Category",
    color="Annual Sales Units",
    color_continuous_scale="Blues"
)

# -----------------------------------
# 10. Dashboard layout
# -----------------------------------

col1, col2, col3 = st.columns([1.2, 1, 1])

with col1:
    st.plotly_chart(fig1, use_container_width=True)

with col2:
    st.plotly_chart(fig2, use_container_width=True)

with col3:
    st.plotly_chart(fig3, use_container_width=True)

col4, col5, col6 = st.columns([1.2, 1, 1])

with col4:
    st.plotly_chart(fig4, use_container_width=True)

with col5:
    st.plotly_chart(fig5, use_container_width=True)

with col6:
    st.plotly_chart(fig6, use_container_width=True)

# -----------------------------------
# 11. Manufacturing Map
# -----------------------------------

st.subheader("Manufacturing Map")

fig7 = px.scatter_geo(
    filtered_df,
    lat="Latitude",
    lon="Longitude",
    color="Manufacturer",
    size="Annual Sales Units",
    hover_name="Manufacturer",
    hover_data=[
        "Market Region",
        "Annual Sales Units",
        "Battery Type"
    ],
    projection="natural earth",
    title="EV Manufacturer Locations"
)

st.plotly_chart(fig7, use_container_width=True)

# -----------------------------------
# 12. Key Market Insights
# -----------------------------------

st.subheader("Key Market Insights")

top_maker = manufacturer_sales.loc[
    manufacturer_sales["Annual Sales Units"].idxmax(),
    "Manufacturer"
]

top_region = regional_sales.loc[
    regional_sales["Annual Sales Units"].idxmax(),
    "Market Region"
]

top_battery = battery_sales.loc[
    battery_sales["Annual Sales Units"].idxmax(),
    "Battery Type"
]

st.write(
    f"**Top manufacturer in sample data:** {top_maker}"
)
st.write(
    f"**Leading region in sample data:** {top_region}"
)
st.write(
    f"**Leading battery type in sample data:** {top_battery}"
)

st.subheader("View Dataset")
st.dataframe(filtered_df, use_container_width=True)

csv = filtered_df.to_csv(index=False).encode("utf-8")

st.download_button(
    label="Download EV Dataset as CSV",
    data=csv,
    file_name="ev_market_data.csv",
    mime="text/csv"
)

st.caption(
    "Educational demonstration only. Sales, ratings, ranges, "
    "and map coordinates are illustrative sample data, "
    "not verified market statistics or factory locations."
)



Project url - https://public.tableau.com/app/profile/paridhi.sharma4119/viz/EV_Market_Performance_Market_Story_2026-10-25_17931234374410/EVExecutiveDashboard


