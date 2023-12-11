# CO2-nouveaux-quartiers
This is a streamlit web app to compute spatial average of built-environment variables that have a causal effect on CO2 mobility-emissions.
It is part of the project "Elaboration d’un outil d’évaluation de l’impact carbone de la mobilité dans les nouveaux quartiers à Genève" for the Canton of Geneva that aims to evaluate carbon emissions in function of a user's choices in terms of the location and building specifics of a new quartier. 


Literature suggests that mobility-emissions are not only closely linked to socio-economic factors, but also to the built environment, commonly called "the 5-D" effect:
* Density (density of population, buildings, employment, ...)
* Design (street network characteristics)
* Diversity (diversity in terms of services, land use, jobs-to-population ratios, ...)
* Distance to transit (quality of public transport service)
* Destination accessibility (ease of access to population and jobs by public transport or car)

![image](https://github.com/Fien6-t/CO2-nouveaux-quartiers/assets/152168560/3058401e-a797-4f00-a6df-41fffc8a14f4)


Using the data of the swiss ["Microrecensement mobilité et transports" (MRMT) 2015](https://www.bfs.admin.ch/bfs/fr/home/statistiques/mobilite-transports/enquetes/mzmv.html), carbon emissions of the mobility patterns of interviewed subjects are linked to their housing locations. Subsequently, these housing locations can be linked to built-environment variables, collected from open-source data and aggregated at a 500x500m cell level (this spatial scale was chosen since literature suggests that a radius of 500 m is the operational radius of a quartier). Using the causal-dose curve package of [Kobrosly R.W. (2020)](https://causal-curve.readthedocs.io/en/latest/), a causal link, controlling for socio-demographic factors and confounding built-environment-factors, is established between these aggregated built-environment variables and the mobility carbon emissions of interviewed subjects. In other words, the MRMT data was used to calibrate a causal link between built-environment variables and mobility related carbon emissions. This means that given a built environment, the average mobility carbon related emissions can be predicted.

![image](https://github.com/Fien6-t/CO2-nouveaux-quartiers/assets/152168560/0e332276-6596-46ba-9c27-99fa77073714)


Extracting the built-environment variables for a given quartier is, however, not easy. It is for this reason that we have developed this app.
The app lets a user draw the limits of their quartier and computes, based on that drawing, a spatial average of the intersected, geospatial built-environment variables. For more flexibility, we added the option of replacing specific geospatial variables by user defined geospatial data that they can upload in a seperate tab.

![image](https://github.com/Fien6-t/CO2-nouveaux-quartiers/assets/152168560/9b47f7d9-f933-498e-8ebd-d05bc9702ebf)

