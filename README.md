# Green Space Accessibility and Population Analysis

This project allows users to explore and analyze green space accessibility in cities. The application utilizes a Streamlit web interface that integrates various geospatial and population data to perform buffer analysis and display the results on an interactive map. The key tasks include fetching city boundary data, retrieving green spaces (parks), performing buffer analysis around green spaces, and identifying areas with underserved populations.

## Features

- **City Boundary Data**: The user inputs a city name, and the app fetches the city's boundary from OpenStreetMap using the `osmnx` library.
- **Green Space Buffer Analysis**: The app identifies parks and creates buffers around them (500 meters) to analyze accessibility.
- **Population Data**: The app fetches population data using the WorldPop API and performs a spatial join to identify populations with or without access to green spaces.
- **Interactive Map**: The results are visualized on an interactive map created using the `folium` library. It displays:
  - Green space areas (buffer zones) in green.
  - Population points in blue.
  - Underserved population points in red (areas without access to green space).

## Requirements

Before running the project, you need to install the necessary Python libraries. You can install them using pip:

```bash
pip install geopandas shapely folium osmnx matplotlib folium streamlit-folium ipython streamlit pyngrok


