## azure-maps-track-air-pollution
Air pollution can be incredibly harmful to human and animal health, and is caused by a number of factors, both natural and artificial. Factory output, burning different types of fuel and natural wildfires all contribute to a rise in air pollution. This pollution is airborne, and won't stay where it was produced, but can be carried many kilometers across the globe by the wind. In late 2019, for example, the smoke from wildfires in Australia reached New Zealand, over 2,000 kilometers away.

Air pollution is measured using the Air Quality Index (AQI) on a scale from 0-500. The higher the level, the greater the health risk. AQI values under 50 means little to no risk, but values above 300 means the air is hazardous to everyone.

The Air Quality index looks at a few different pollutants:

- Ground-level ozone
- Particulates
- Carbon monoxide
- Sulphur dioxide
- Nitrogen dioxide

Prerequisites:
- Ability to use Python at a beginner level
- Experience using Visual Studio Code, at the beginner level
- Python 3.6 or higher installed, and available on your path
- Visual Studio Code installed
- Python tools for Visual Studio Code installed

# Visualize mapping data with the Azure Maps SDK
The Azure Maps web SDK has a whole host of different tools to visualize spatial data on an interactive map on a web page. Before getting started adding the map to a web page, lets look at some of the capabilities.

# Render a map
The Azure Maps web SDK has an interactive JavaScript map control that can be added to a web page. Maps are drawn, or rendered, using the Spherical Mercator projection coordinate system, the de facto standard for web-based mapping applications. This system stretches the map at both the North and South poles to create a square map that can be drawn on screen. This stretching does mean that the further away from the equator you get, the more stretched the map is. The end result is countries like Greenland appear substantially larger than they are in reality.

Maps can be rendered in a number of different styles.

# Navigate around the map
The Azure Maps control can be configured to be fully interactive, allowing the user to zoom, move, rotate, and tilt the map view. When zoomed in and tilted, the map can show 3D representations of the shape of buildings. Navigation is done using a mouse, trackpad, or touch screen, and supports pinching to zoom, and dragging to move the map around. The map control has zoom, compass, pitch, and style picker controls that can be enabled and shown on the map.

Navigation can also be done in code, such as setting the view to a specific location. The different user navigation capabilities can be enabled or disabled by settings on the map control.

# Layers
Maps can be augmented with layers, visualizing data on top of the map. In a later unit in this module, you'll use a layer on a map to visualize air quality data.

There are a number of different layer types available, and these layers all render data sources that contain either GeoJSON data or MapBox vector tiles. GeoJSON will be covered in a later unit in this module

The different layer types include:

- Symbol layer

Symbol layers put either a pin icon, or a custom icon loaded from an image file at a specific location on the map. For example, different icons could show the location of various types of social support in a city, such as food banks, homeless shelters, or refuges.

- Bubble layer

Bubble layers put circular bubbles at locations on the map. The bubbles can be configured to show the data they're representing, such as setting the bubble size or color. For example, during a pandemic different bubble sizes could show the number of people who have contracted an illness, with the color reflecting the mortality rate.

- Heat map

Heat map layers represent the density of data using a range of colors to show 'hot spot' areas on a map. For example, a heat map could be used to show the relative risk of earthquakes based off the number and strength of previous earthquakes.

The location of the features in the layer is defined by a data source. The data source can also provide data to configure controls on the layer, for example what image to display or how large to make a bubble.

In this unit, you learned about the Azure Maps web SDK. including styles, navigation and layers. Next, you'll create an Azure Maps account so you can use the web SDK in a web app.

# Get air quality data
The World Air Quality Index aggregates air quality data from around the world, and makes this data available through a free API you can use in your app. The data is available as the current AQI (Air Quality Index) reading for multiple recording stations around the world. When you request data, you can do it for either:

- A single location to get the nearest reading for a city or location
- All the stations within a rectangle defined using the north-east and south-west coordinates of the rectangle.
The map should plot as much data as possible based on the visible area of the map. AQI data can be requested for just those stations within the visible area. This makes the API call faster, as only the data needed is requested.
