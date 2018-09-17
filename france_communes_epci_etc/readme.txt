#############################################
# FOND DE CARTE - FRANCE
# Date de cr�ation : Avril 2018
# Version : 2016 (GEOFLA 2.2 - 2016-06-28)
# Fournisseur : UMS RIATE
#############################################

# Descriptif g�n�ral
Ce dossier propose les zonages et d�coupages administratifs officiels utilis�es en France.   
Ces couches sont disponibles en lattitude / longitude (WGS84) au format GEOJSON. Ces couches sont ensuite reprojet�es selon la projection officielle pour la France m�tropolitaine (RGF93 / Lambert-93) dans le fichier projet. 
L'objectif du fichier projet consiste � proposer une mise en page permettant de repr�senter simultan�ment sur le m�me mod�le cartographique les territoires de France m�tropolitaine et les DOM (cf plus bas pour les pr�cisions techniques).  

# Maillages disponibles (se reporter � la documentation de l'INSEE pour de plus amples informations)
COMMUNES.geojson : Communes fran�aises version 2016 (35927 unit�s territoriales)
EPCI.geojson : �tablissements publics de coop�ration intercommunale version 2016 (2064 unit�s territoriales)
BV.geojson : Bassins de vie version 2012 (1664 unit�s territoriales)
ZEMP.geojson : Zones d'emploi version 2010 (322 unit�s territoriales)
AU.geojson : Aires urbaines version 2010 (793 unit�s territoriales, ne recouvrant pas tout le territoire)
UU.geojson : Unit�s urbaines version 2010 (22778 unit�s territoriales, ne recouvrant pas tout le territoire)
DEPT.geojson : D�partements (101 unit�s territoriales)
REGI.geojson : R�gions version 2018 (18 unit�s territoriales) 

Chaque maillage est d�fini par son syst�me de codification officiel, sa population au 1er janvier 2016 et sa surface r�elle exprim�e en hectares. Sont associ�s aux nomenclatures les �ventuelles cat�gorisation officielles de ces nomenclatures (aires urbaines...)

# Processus construction (Programme R)
1 - Extraction des centroides des communes fran�aises (GEOFLA)
2 - Cr�ation des polygones de Voronoi � partir de ces centroides
3 - Intersection avec le contours de la France m�tropolitaine (GEOFLA)
4 - Reprojection des DOM et r�duction des DOM pour appara�tre dans le mod�le cartographique. Le rapport de r�duction utilis� figure sur le mod�le cartographique. Les projections initiales des DOM correspondent aux projections locales officielles utilis�es par l'IGN
5 - Cr�ation d'une couche pays frontaliers dont les g�om�tries sont compatibles avec le fond France
6 - Cr�ation de la couche "boxes"

# Conseils d'utilisation
Pour le fond de carte des communes fran�aises, il est pr�f�rable de manipuler ce lourd fichier sur une version de Magrit install�e localement (cf le post https://magrit.hypotheses.org/392 � ce sujet). 
Vous pouvez aussi utiliser des logiciels de g�n�ralisation de fond de carte (http://mapshaper.org/) pour simplifier le trait de c�te. 

# Bounding Box (ensemble des couches)
SCR : WGS84 (EPSG 4326)
XMin : -4.89208
XMax : 7.56972
YMin : 41.452
YMax : 46.8914

# Sources
G�om�tries : IGN (centroides des communes)
Codes : INSEE (nomenclatures au 1er janvier 2016). 

# Licence
Creative Commons BY-SA