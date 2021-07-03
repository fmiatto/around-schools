---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

# Where should you start your next business?
{: .fs-9 }

Analyzing places of interest around schools to gain business insight to start your new endavour (built with open data form OpenStreetMap)
{: .fs-6 .fw-300 }

[View it on GitHub](https://github.com/fmiatto/around-schools){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started


### Stack
* Docker version `20.10.7`, build `f0df350`
* Python `3.9.6 64-bit`
* MySQL `10.4.19-MariaDB `
* Microsoft Power BI Desktop `2.93.981.0 64-bit (May 2021)`

### Dependencies
* [OpenStreetMap](https://www.openstreetmap.org/) community of maintainers of world-wide geo location open data
* [Overpass Turbo](http://overpass-turbo.eu/) web-based tool to query OpenSteetMaps data, using the Overpass API, and displaying live on the map
* [Wiktorn's Overpass-API](https://github.com/wiktorn/Overpass-API) Docker Image 
* [Geofabrik's](http://download.geofabSrik.de/) daily OpenStreetMap data extracts 
* OpenStreetMaps daily minute [replication diffs](https://download.openstreetmap.fr/)

### Introductory Reading

Please check these links if you do not have experience [developing with OpenStreetMaps (OSM)](https://wiki.openstreetmap.org/wiki/Develop), the OSM [data elements (nodes, ways, relation)](https://wiki.openstreetmap.org/wiki/Elements), the [Planet file](https://wiki.openstreetmap.org/wiki/Planet.osm), the [data dumps formats](https://wiki.openstreetmap.org/wiki/OSM_file_formats#Map-data), and the tools to [process these files](https://wiki.openstreetmap.org/wiki/Converting_map_data_between_formats). In addition, please be advised that processing OSM data for a state or country can consume a lot of computaional ressources. This project was developed with `32GB of RAM` and an `AMD Ryzen 7 processor`.

## Creating a local OSM data server

In this chapter, we will see how to obtain an updated compressed copy of OSM data, and make it available in your own local OverpassAPI server so you can guarantee your queries will always run, and to no overload free server in the internet with your data processing. In the end, you will be able to quickly get the latitude and longitude of all bars in your area, for example.

### Defining the area to be explored

You can decide on any subset region of the planet Earth for your Planet file. Any small country, state of a bigger country, or if you have the performance, a top5 country by area, or an entire continent! The area for my analysis will be limited to the [Federative Republic of Brazil](https://en.wikipedia.org/wiki/Brazil) as an example.

As such, going to the [Geofabrik's](http://download.geofabSrik.de/) daily OpenStreetMap data extracts web page, we can quickly navigate to South America, and download the `.osm.pbf` file for Brazil (1.3 GB)

`.osm.pbf` is the highly compressed, optimized binary format for the Planet file. It's faster to write and read to the disk.

![ alt text for screen readers](/around-schools/assets/images/01-index-01-download-brazil.png "Text to show on mouseover")
