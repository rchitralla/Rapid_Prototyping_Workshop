# Loveable Step-by-Step Guide

A complete guide to building your prototype with Loveable during the workshop.

## What is Loveable?

Loveable is an AI-powered platform that generates full-stack web applications from natural language descriptions. You describe what you want — Loveable builds the frontend, connects data, and deploys it. No coding required.

## Quick Start

1. Go to [lovable.dev](https://lovable.dev/) and sign in with GitHub
2. Click **New Project**
3. Describe your app in the prompt box
4. Loveable generates a working app you can customize

## Step 1: Write Your Initial Prompt

The quality of your prompt determines the quality of your prototype. Be specific about:
- **What** the app does
- **Who** it's for
- **What data** it displays
- **What interactions** users should have

### Example Prompts by Brief

**Brief 1 — Alsace Wine Route Explorer:**
> Build a wine discovery dashboard for the Alsace wine region. It should have:
> - A sidebar with filters for grape variety (Riesling, Gewurztraminer, Pinot Gris, etc.), village, classification, and price range
> - A summary row showing total wines, average price, and average rating
> - A bar chart showing average price by grape variety, colored by classification
> - A scatter plot of price vs rating, colored by grape variety
> - A data table at the bottom with search and sort
> Use an elegant design with burgundy and gold accents on a cream background.

**Brief 2 — Strasbourg Bike Share Analysis:**
> Create an analytics dashboard for Strasbourg's bike-sharing system (Velhop). Include:
> - Filters for neighborhood, weather, and day of week in the sidebar
> - Summary cards showing total pickups, busiest station, and average daily rides
> - A bar chart of pickups by hour of day (showing commute peaks)
> - A chart comparing ridership across weather conditions
> - A heatmap or grouped bar chart showing usage by neighborhood and day of week
> Use a modern design with Strasbourg-blue accents and clean typography.

**Brief 3 — Christmas Market Visitor Trends:**
> Build a dashboard exploring Strasbourg's Christmas market visitor data. It should show:
> - Key metrics: total visitors, average daily spend, busiest market location
> - A line chart of daily visitors over the market season, colored by market location
> - A bar chart of spending estimates by vendor category
> - A comparison of visitor counts on weekdays vs weekends
> - A weather impact chart showing how conditions affect attendance
> Use a festive, warm design with reds, golds, and deep greens.

## Step 2: Refine with Follow-Up Prompts

After Loveable generates the first version, iterate:

- "Move the filters to the left sidebar"
- "Make the chart colors consistent across all visualizations"
- "Add a download button for the filtered data"
- "Change the header to say 'Alsace Wine Explorer'"
- "Make it responsive for mobile"

## Step 3: Connect Your Data

You can add data to Loveable in several ways:

### Option A: Paste CSV Data Directly
> "Replace the sample data with this CSV data: [paste your CSV]"

### Option B: Use Supabase (Built-in)
Loveable has built-in Supabase integration for persistent data:
1. Click the **Supabase** icon in the Loveable editor
2. Connect your Supabase project (or let Loveable create one)
3. Ask Loveable: "Store the data in Supabase and fetch it on load"

### Option C: Static JSON
> "Use this data as the app's dataset: [paste JSON array]"

## Step 4: Customize the Design

Prompt Loveable to adjust the look:

- "Use a dark theme with neon accents"
- "Make it look like a professional analytics dashboard"
- "Add a logo at the top — use a placeholder image for now"
- "Increase the font size and add more spacing"

## Step 5: Publish

1. Click **Share** in the top-right of the Loveable editor
2. Toggle the **Public** switch
3. Copy the shareable URL
4. (Optional) Connect a custom domain

## Tips for Better Results

| Do | Don't |
|----|-------|
| Describe layout and structure | Ask for vague "make it better" |
| Specify color schemes and themes | Assume Loveable knows your preferences |
| Iterate one change at a time | Ask for 10 changes in one prompt |
| Reference specific components | Use jargon without context |
| Paste real data early | Wait until the end to add data |

## Loveable + Streamlit: When to Use Which

| Scenario | Use Loveable | Use Streamlit |
|----------|-------------|---------------|
| Quick visual prototype | Yes | — |
| Data-heavy analytics | — | Yes |
| Custom Python logic | — | Yes |
| Beautiful UI with no code | Yes | — |
| Share with stakeholders | Yes | Yes |
| Complex data transformations | — | Yes |
| Rapid iteration on design | Yes | — |

**Workshop tip:** Start with Loveable to prototype the UI/UX, then switch to Streamlit if you need more data processing power. Or use both — Loveable for the frontend concept, Streamlit for the functional prototype.

## Reference

- [Loveable Documentation](https://docs.lovable.dev/)
- [Loveable YouTube Tutorials](https://www.youtube.com/@lovabledev)
