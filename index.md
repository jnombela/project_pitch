---
title       : Spain weather. Normal rain values 1981-2010
subtitle    : Project pitch - shiny app
author      : Justo Nombela
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## Where it rains more, and less, in Spain?
  
This shiny app analyzes normal rain quantities in Spain. It lets you know how much it rains per region, and also know detail data of an specific region quickly. A map will let you zoom in and zoom out to see the details.
   
Please visit [our app](https://jnombela.shinyapps.io/dataprod-project/) and you'll see that it rains much more in the north of Spain, which is the expected, an discover surprises, like high rain values in the south of Andalucia region (between Cádiz and Málaga). 
   
Data from [AEMET](http://www.aemet.es/es/portada "Agencia Estatal de Meteorología"). This Agency publishes studies and data from 2,621 weather stations spread all over the country. In our case we used monthly rainfall normal values study, ftom 1981 to 2010. For more information please follow [this link](http://www.aemet.es/es/conocermas/recursos_en_linea/publicaciones_y_estudios/publicaciones/detalles/Valores_mensuales_1981_2010).

---
## Rainfall values
![width](./assets/img/Captura.png)

---
## App structure

This app is inspired in [Shiny superZip example](http://shiny.rstudio.com/gallery/superzip-example.html). It has two tabs: one for the map of Spain, and another for explorating data.

* Over the map you can see a circle for each weather station. Colour and size of circles indicates the rainfall in each station per year. On the down-left corner you can see a legend with color code. You can click on every circle to see a popup with name of the station and total rainfall in a year.

* In the second tab, data explorer, you can see rainfall data of every station. Also you can filter by Province and Watershed, and also by name in every column

---
## Behind the scenes - technologies used

+ *Shiny*
+ *data.table::fread* to read fast original files
+ *rgdal* package to transform UTC geographical coordinates into decimal format (as needed in leaflet map)
+ *dplyr* package to treat data



---
## Behind the scenes - software components

+ *iconv* functions to transform Latin-1 character set (original data) to UTF-8 (as needed in shinyapps.io linux servers)

+ *Leaflet* library for R and *OpenStreetMaps* to render maps and locate and paint the circles in another layer.

+ *DT* library to render data and let explore the user





