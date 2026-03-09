# Streamlit Step-by-Step Guide

A complete guide to building your data app prototype with Streamlit during the workshop.

## What is Streamlit?

Streamlit is a Python framework that turns scripts into interactive web apps. You write Python — Streamlit handles the UI. No HTML, CSS, or JavaScript needed.

## Quick Start

```bash
# From the repo root
pip install -r examples/streamlit/requirements.txt
streamlit run examples/streamlit/app.py
```

Your app opens at `http://localhost:8501`.

## Step 1: Load Your Dataset

Replace the sample data in `app.py` with your chosen dataset:

```python
import pandas as pd

# Choose one:
df = pd.read_csv("../../datasets/alsace_wines.csv")
# df = pd.read_csv("../../datasets/strasbourg_bikes.csv")
# df = pd.read_csv("../../datasets/christmas_markets.csv")

# Quick check
st.write(f"Loaded {len(df)} rows and {len(df.columns)} columns")
st.dataframe(df.head())
```

## Step 2: Add Sidebar Filters

Filters let users explore the data interactively. Here's an example using the wine dataset:

```python
st.sidebar.header("Filters")

# Dropdown filter
grape = st.sidebar.selectbox("Grape Variety", ["All"] + sorted(df["grape_variety"].unique()))
if grape != "All":
    df = df[df["grape_variety"] == grape]

# Multi-select filter
villages = st.sidebar.multiselect("Village", df["village"].unique())
if villages:
    df = df[df["village"].isin(villages)]

# Range slider
min_price, max_price = float(df["price_eur"].min()), float(df["price_eur"].max())
price_range = st.sidebar.slider("Price Range (EUR)", min_price, max_price, (min_price, max_price))
df = df[df["price_eur"].between(*price_range)]
```

## Step 3: Add Metrics

Show key numbers at a glance:

```python
col1, col2, col3 = st.columns(3)
col1.metric("Total Wines", len(df))
col2.metric("Avg Price", f"{df['price_eur'].mean():.0f} EUR")
col3.metric("Avg Rating", f"{df['rating'].mean():.1f} / 5")
```

## Step 4: Add Charts

Use Plotly for interactive visualizations:

```python
import plotly.express as px

# Bar chart
fig = px.bar(df, x="grape_variety", y="price_eur", color="classification",
             title="Price by Grape Variety and Classification")
st.plotly_chart(fig, use_container_width=True)

# Scatter plot
fig2 = px.scatter(df, x="price_eur", y="rating", color="grape_variety",
                  hover_name="producer",
                  title="Price vs Rating")
st.plotly_chart(fig2, use_container_width=True)

# Pie chart
fig3 = px.pie(df, names="grape_variety",
              title="Distribution by Grape Variety")
st.plotly_chart(fig3, use_container_width=True)
```

## Step 5: Add Interactivity

```python
# Tabs for different views
tab1, tab2 = st.tabs(["Charts", "Raw Data"])

with tab1:
    st.plotly_chart(fig, use_container_width=True)

with tab2:
    st.dataframe(df, use_container_width=True)
    st.download_button("Download CSV", df.to_csv(index=False), "filtered_data.csv")
```

## Deploying to Streamlit Cloud

1. Push your code to GitHub
2. Go to [share.streamlit.io](https://share.streamlit.io/)
3. Connect your GitHub repo
4. Select `examples/streamlit/app.py` as the main file
5. Click **Deploy**

Your app is now live with a shareable URL.

## Useful Streamlit Components

| Component | Use For | Example |
|-----------|---------|---------|
| `st.selectbox` | Single selection dropdown | Filter by category |
| `st.multiselect` | Multiple selections | Filter by multiple tags |
| `st.slider` | Numeric range | Filter by amount/date |
| `st.columns` | Side-by-side layout | Metrics row |
| `st.tabs` | Tabbed content | Charts vs. data table |
| `st.metric` | KPI display | Total, average, count |
| `st.plotly_chart` | Interactive charts | Bar, scatter, pie |
| `st.dataframe` | Interactive table | Browse raw data |
| `st.download_button` | Export data | Download filtered CSV |

## LLM Prompts for Streamlit

Copy-paste these to your LLM for quick help:

**Add a filter:**
> "I have a Streamlit app with a pandas DataFrame `df` that has columns [list your columns]. Add a sidebar filter for the [column name] column."

**Add a chart:**
> "Add a Plotly bar chart to my Streamlit app showing [metric] by [category]. The DataFrame has these columns: [list columns]."

**Fix a bug:**
> "I'm getting this error in my Streamlit app: [paste error]. Here's my code: [paste code]. How do I fix it?"

## Reference

- [Streamlit Documentation](https://docs.streamlit.io/)
- [Streamlit Cheat Sheet](https://docs.streamlit.io/develop/quick-reference/cheat-sheet)
- [Plotly Express](https://plotly.com/python/plotly-express/)
