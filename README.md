## Geosoft2

##Introduction
#Modern satellite-based Earth observation (EO) data are an invaluable source for monitoring, modeling, and understanding global environmental phenomena. Examples such as Global Forest Watch (http://www.globalforestwatch.org/map/) demonstrate their usage in practical applications. The acquisition and analysis of the data by scientists typically follows the following steps:
1. Selecting and ordering satellite images on portals of the data providers such as NASA, USGS, or ESA
2. Waiting until requested data have been collected from the provider’s archive
3. Downloading the data to local hard drives
4. Analysing the data with common desktop applications
Due to the data volume of recent EO missions such as the European Copernicus program and its Sentinel satellites, this workflow becomes increasingly inefficient. As an alternative, many cloud computing providers like Amazon Web Services (AWS) or the Earth Observation Data Centre (EODC) recently started to make the data available in their infrastructures. Hosted applications and services therefore get efficient access to the data.
In this project, a new web-based platform that allows working interactively with Sentinel 2 images shall be developed. Users of that platform shall particularly be able to
- search and select available Sentinel2 imagery,
- visualize selected images interactively in a map with zoom and pan functionality as
well as selecting spectral bands and visualization parameters, and
- perform simple arithmetic expressions to combine spectral bands (e.g. for deriving
vegetation indexes) and visualize the results.
Objectives
The platform to be implemented in an easy to use web interface shall allow users to interactively select and visualize Sentinel 2 images and to perform simple computations on the data. Images shall be drawn in a web-based map application. Zoom and pan functionality as well as the selection of spectral bands, their assignment to RGB channels must be implemented. The complete functionality shall be accessible through the browser in a single web site.
 1
Scope and boundary conditions
The principal provides a computing infrastructure with sample Sentinel 2 imagery.
Functional Requirements
Data discovery
/LF00010/ /LF00020/ /LF00030/
/LF00040/ /LF00050/
/LF00060/
Users shall be able to search for (sub)strings of the image/scene Intentifier (see https://earth.esa.int/web/sentinel/user-guides/sentinel-2- msi/naming-convention)
Users shall be able to search images based on their spatial extent by drawing a rectangle in a map such that search results only contain images that spatially intersect with the rectangle.
Users shall be able to search images based on their recording date such that only images that have been captured after a given starting date and before a given end date are part of the search results. Users may specify both or only one of two dates.
All search criteria are optional and combined with a logical AND. If none of the criteria is given, all available images shall be contained in the result.
Search results are displayed in a (paged) list as well as in a map. The map shall show the spatial extent of result images. The list shall be sorted by recording date in descending order.
Users get further information and metadata of images when they select an image in the list or in the map. A selected image can be visualized as described below.
Data visualization
/LF01010/ /LF01020/
/LF01030/ /LF01040/ /LF01050/
Users shall be able to change base maps of the interactive map.
The map shall include zoom and pan functionality and display Sentinel 2 images with the respective resolution.
Users shall be able to visualize Sentinel 2 images either as one channel grayscale image or as RGB color image.
Users shall be able to select, which spectral bands of the input shall be visualized and relate to red, green, blue, or the grayscale channel.
To allow some contrast brightness adjustments, users shall be able to define maximum and minimum values for each visualized spectral band. For 8-bit color channels, minimum values should be mapped to 0 and
2
/LF01060/ /LF01070/ /LF01080/
maximum values should be mapped to 255 with a linear scaling between the specified numbers.
Images can be drawn with transparency, which is specified by the user between 0% and 100%.
All visualization parameters shall be adjustable interactively in the user interface without need to reload the application.
A mouse click on the map returns the original Sentinel-2 measurement values at the particular location.
Miscellaneous
/LF02010/ The complete functionality is available in a single web application without registration.
/LF02020/ The current state of the application (including visualization parameters) is shareable by a unique link.
Bonus Features
In addition to mandatory functional requirements, the contractor may implement bonus features as described below. Successful implementation of the features will be considered in the final product evaluation.
Data processing (bonus features)
/LX01010/
/LX01020/ /LX01030/
Users shall be able to define simple arithmetic expressions to compute new (derived) bands for an image. Expressions shall be evaluated per pixel and shall get access to the values of the original spectral bands at the same pixel. The syntax of the expressions should be as simple as possible and support at least addition, subtraction, multiplication, division, root and power functions, and their combination including brackets.
Image bands derived by arithmetic expressions shall be visualizable in the same way as the original spectral bands.
Users shall be able to mask visualized pixels with a simple logical expression (<, <=, ==, >=, >, !=, !, and, or, and combinations with brackets). Similar to the arithmetic expressions, logical masking expressions shall be evaluated per pixel and shall include values of the original spectral bands (e.g. band1 < 5), as well as values of the derived bands (e.g. ndvi > 0.3).
3
/LX01040/ Summary statistics (min, max, median, mean, standard deviation) of the currently visible part of an image shall be computed per band and displayed to users.
Nonfunctional Requirements
Portability
The user interface must support all popular web browsers by providing a similar user experience. The layout should primarily target at laptop or desktop computers with moderate to large display devices.
Maintainability
An established build and configuration system as well as dependency management must be applied for the used Programming language, e.g. Maven or Gradle for Java, or Grunt/Bower for JavaScript. According documentation on building, configuring and installing the system must be provided in Markdown-formatted documentation files using the appropriate markup for lists, links, etc.
Licensing
The complete system must be published under an open-source license approved by the Open Source Initiative (see https://opensource.org/licenses). The contractor must ensure compatibility of the selected license with all used libraries.
Usability
The system must support intuitive use to the extent that targeted groups can use its main features without further documentation. Common practices for web-based user interfaces and interaction paradigms should be applied.
Performance
The interactive visualisations must react within 0.5 seconds to give a user the impression of direct manipulation. Complex operations may be performed asynchronously such that the user-interface never freezes.
Boundary conditions
The system developed by the contractor must be given an appealing product name with high recall value. The product name is used throughout the source code and documentation of the system.
The language of the user interface is English.
 4
Deliveries
The delivery of the product consists of the following parts:
- Documented source code published in a single repository on GitHub
(https://github.com)
- Installation instructions
- User manual (can be integrated into the product)
- Report on the fulfillment of functional requirements
- A running installation on the provided infrastructure
Acceptance Criteria
The product is considered as being accepted by fulfillment of all functional and nonfunctional requirements, a successful presentation and demonstration of the product by the contractor, and the delivery of all product parts as described above. Implementation of the bonus features is optional but will be considered during product evaluation.
Miscellaneous
The contractor is asked for creating a detailed concept and product specification until Oct. 23, 2017. In case any changes are needed during the project implementation, the contractor is obliged to immediately submit a change request to the principal.
