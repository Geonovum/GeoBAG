Scenario’s
==========

Geometrieverzoeken en –leveringen
---------------------------------

Bij 1 Geo en meerdere BAG-applicaties:

-   Bij een verzoek vanuit BAG, vult de BAG-applicatie de stuurgegevens zo
    specifiek in dat Geo altijd 1 bericht terug kan sturen naar de juiste
    ontvanger. Filtering aan de kant van Geo is niet nodig.

-   Bij een levering voor bestaande BAG-objecten is de gemeentecode bekend, en
    kan Geo de juiste ontvangende stuurgegevens ( o.a. administratie) invullen.

-   Bij een levering met geconstateerde objecten vanuit Geo filtert Geo
    (bijvoorbeeld geometrisch op de gemeentegrens om de gemeentecode te bepalen)
    zodanig dat de levering naar de juiste ontvangende organisatie wordt
    gestuurd.

Geo vult de *stuurgegevens* als volgt in: \<organisatie\> is gemeentecode,
\<applicatie\> is naam BAG-applicatie, en \<administratie\> de uitfiltering
verkregen gemeentecode bij meerdere BAG-administraties[^1].

[^1]: immers de exacte BAG-administratie kan Geo niet bepalen

Bij 1 BAG-applicatie en meerdere Geo-applicaties:

-   Als er 1 Geo-applicatie voor een gemeente is, dan filtert BAG op
    gemeentecode om de naam van de BGT-administratie te bepalen.

De stuurgegevens voor de ontvangende Geo-applicatie worden door de Geo
applicatie bepaald want dit zijn dezelfde stuurgegevens als worden toegepast in
het berichtenverkeer met SVB-BGT. De BAG applicatie zorgt er voor dat per
gemeentecode in de BAG, de juiste unieke set Geo-stuurgegevens worden ingevuld.

Bij 1 BAG-applicatie en één Geo-applicatie met meerdere BGT-administratie van
verschillende gemeenten:

-   Als er meerdere BGT-applicaties in een gemeente zijn, dan wordt er één
    centrale BGT applicatie aangewezen waarnaar steeds 1 bericht wordt verstuurd
    door BAG.

Responsberichten
----------------

Een respons-bericht wordt altijd verstuurd naar met in de stuurgegevens van de
ontvanger, de stuurgegevens van de zender van het bericht waarop het respons
wordt teruggegeven.
