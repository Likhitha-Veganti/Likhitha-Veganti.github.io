---
title: "Exploring Tourist Attractions in New York City"
excerpt: "This project utilizes various Python libraries, including Pandas, Altair, Geopandas, OSMnx, Folium, and others, to visualize and explore tourist attractions in New York City. The map includes markers for different types of attractions, public transport locations, and hotels."
---
Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/New%20York%20Tourist%20Attractions%20Map%20Visualization).

### Code Structure
- The code is structured to fetch geographical data using OSMnx and create GeoDataFrames for different types of tourist attractions, public transport locations, and hotels in New York City.

- The Folium library is used to create an interactive map with markers for each attraction category, providing visual information about their locations.

- Icons with different colors and shapes are used for attractions such as animals, artwork, public transport, hotels, viewpoints, and zoos.

- The map includes a legend and a title to enhance the user experience.

### Map Legend
- **Red Paw Icon:** Animal-related attractions (e.g., zoo)
- **Red Paintbrush Icon:** Artwork-related attractions (e.g., gallery)
- **Blue Bus Icon:** Public transport locations (bus stops)
- **Gray Building Icon:** Hotels
- **Red Paintbrush Icon:** Gallery
- **Red Person Walking Icon:** Viewpoints

### Saving the Map
The interactive map is saved as an HTML file named `newyork_tourist_attractions.html`. You can open this file in a web browser to explore the tourist attractions in New York City.

<iframe src="/files/newyork_tourist_attractions.html" width="1000" height="700" frameborder="0"></iframe>

# Description of the Visualization:
The visualization explores tourist attractions in New York City, categorizing them by type and representing them on a map. Design choices were made to ensure clarity, expressiveness, and contextual relevance. The consistent use of red color for general attractions,regardless of subtype, provides a cohesive and easily recognizable visual identity for all tourist destinations. Icons such as paw prints for animals or zoos and paintbrushes for artworks were chosen to enhance visual appeal and aid in quickly identifying attraction types. The person-walking icon is employed for viewpoints and other entertainment attractions, adding a clear distinction to these points of interest. Additionally, the dharmachakra icon represents the wonder wheel of New York, contributing to a more nuanced and informative visual language. The use of blue for public transport and grey for hotels, along with clustering markers to prevent map clutter, ensures a balanced and user-friendly representation of tourist attractions. Tooltips and popups offer additional details without overwhelming the map, creating a visually pleasing and informative exploration of New York City's tourist hotspots.
