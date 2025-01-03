Green Space Accessibility and Population Analysis
This project allows users to explore and analyze green space accessibility in cities. The application utilizes a Streamlit web interface that integrates various geospatial and population data to perform buffer analysis and display the results on an interactive map. The key tasks include fetching city boundary data, retrieving green spaces (parks), performing buffer analysis around green spaces, and identifying areas with underserved populations.

Features
City Boundary Data: The user inputs a city name, and the app fetches the city's boundary from OpenStreetMap using the osmnx library.
Green Space Buffer Analysis: The app identifies parks and creates buffers around them (500 meters) to analyze accessibility.
Population Data: The app fetches population data using the WorldPop API and performs a spatial join to identify populations with or without access to green spaces.
Interactive Map: The results are visualized on an interactive map created using the folium library. It displays:
Green space areas (buffer zones) in green.
Population points in blue.
Underserved population points in red (areas without access to green space).
Requirements
Before running the project, you need to install the necessary Python libraries. You can install them using pip:

bash
Copy code
pip install geopandas shapely folium osmnx matplotlib folium streamlit-folium ipython streamlit pyngrok
Usage
User Input: The user provides a city name through the Streamlit interface. The app will automatically fetch the city's boundary and green space data.
Analysis: The app performs the following steps:
Fetch the city boundary and parks data.
Create a 500-meter buffer around the green spaces.
Retrieve population data using the WorldPop API.
Determine which population points have access to green spaces and which do not (underserved).
Visualization: The app displays an interactive map with the following layers:
Green space buffers (green).
Population points (blue).
Underserved population points (red).
Access: The app will be available via a public URL provided by ngrok, which creates a secure tunnel to the local Streamlit server.
Streamlit Script
The Streamlit script (streamlit_app.py) runs the app, performing geospatial analysis and displaying the map. Here's how the app is structured:

City Data Fetching: Uses osmnx to fetch city boundaries and green spaces.
Buffer Analysis: Creates buffers around green spaces and clips them to the city boundary.
Population Data: Fetches population data from WorldPop API and performs a spatial join to check if the population has access to green spaces.
Mapping: Visualizes the results using folium and integrates with Streamlit using folium_static.
Starting the App
The application is designed to be run with Streamlit. Ensure that you have Streamlit installed in your Python environment.
Run the following command to start the Streamlit app:
bash
Copy code
streamlit run streamlit_app.py
The ngrok tunnel will open, and the app will be accessible at the public URL provided by ngrok.
Notes
CRS (Coordinate Reference System): The app uses UTM Zone 51N (EPSG:32651) for buffer analysis, which is suitable for regions like the Philippines.
Error Handling: Basic error handling is implemented to ensure that data fetching and analysis proceed smoothly.
WorldPop API: The population data is fetched from the WorldPop API. Ensure that the API URL and credentials are configured correctly for the region you are analyzing.
