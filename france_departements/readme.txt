#############################################
# FOND DE CARTE - FRANCE
# Date de création : Avril 2018
# Version : 2016 (GEOFLA 2.2 - 2016-06-28)
# Fournisseur : UMS RIATE
#############################################

# Descriptif général
Ce dossier propose les zonages et découpages administratifs officiels utilisées en France.   
Ces couches sont disponibles en lattitude / longitude (WGS84) au format GEOJSON. Ces couches sont ensuite reprojetées selon la projection officielle pour la France métropolitaine (RGF93 / Lambert-93) dans le fichier projet. 
L'objectif du fichier projet consiste à proposer une mise en page permettant de représenter simultanément sur le même modèle cartographique les territoires de France métropolitaine et les DOM (cf plus bas pour les précisions techniques).  

# Maillages disponibles (se reporter à la documentation de l'INSEE pour de plus amples informations)
DEPT.geojson : Départements (101 unités territoriales)
REGI.geojson : Régions version 2018 (18 unités territoriales) 

Chaque maillage est défini par son système de codification officiel, sa population au 1er janvier 2016 et sa surface réelle exprimée en hectares. Sont associés aux nomenclatures les éventuelles catégorisation officielles de ces nomenclatures (aires urbaines...)

# Processus construction (Programme R)
1 - Reprojection des DOM et réduction des DOM pour apparaître dans le modèle cartographique. Le rapport de réduction utilisé figure sur le modèle cartographique. Les projections initiales des DOM correspondent aux projections locales officielles utilisées par l'IGN
2 - Création d'une couche pays frontaliers dont les géométries sont compatibles avec le fond France
3 - Création de la couche "boxes"

# Conseils d'utilisation
Il est préférable de manipuler ce lourd fichier sur une version de Magrit installée localement (cf le post https://magrit.hypotheses.org/392 à ce sujet). 
Vous pouvez aussi utiliser des logiciels de généralisation de fond de carte (http://mapshaper.org/) pour simplifier le trait de côte. 

# Bounding Box (ensemble des couches)
SCR : WGS84 (EPSG 4326)
XMin : -4.89208
XMax : 7.56972
YMin : 41.452
YMax : 46.8914

# Sources
Géométries : IGN
Codes : INSEE (nomenclatures au 1er janvier 2016). 

# Licence
Creative Commons BY-SA

