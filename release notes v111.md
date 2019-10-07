Release notes StUF-Geo BAG versie 1.1.1 (Geo-BAG koppelvlak)
============================================================

Versie 1.1.1 is een bugfix release van versie 1.1 waarin de volgende issues
opgelost:

[\#52](https://github.com/Geonovum/GeoBAG/issues/52) Verkeerd sequentiediagram
voor Alternatief scenario Geo keurt geometrieverzoek af

De afbeeldingslink naar ‘Figuur 3.5 Sequentiediagram Verzoek om geometrie door
BAG – Alt 3. Geo keurt verzoek af’ is aangepast naar juiste afbeelding.

[\#53](https://github.com/Geonovum/GeoBAG/issues/53) schemaLocation in WSDL 1.1
moet zijn geoBAG0101.xsd

In geoBAG0101_bg0310_ontvangAsynchroon_bag.wsdl en
geoBAG0101_bg0310_ontvangAsynchroon_geo.wsdl is schemaLocation gewijzigd van
geoBAG0100_msg.xsd naar geoBAG0101_msg.xsd

\<xs:import namespace="http://register.geostandaarden.nl/xmlschema/geobag/1.1"  
schemaLocation="geoBAG0100_msg.xsd"/\>

\#54 sleutelOntvangend ontbreekt als attribuut bij Standplaats in
geometrieverzoek/levering

In geoBAG0101_bg0310_ent.xsd bij complex type STA-geoBag-basis is attribuut
sleutelOntvangend toegevoegd

\<attribute ref="StUF:sleutelOntvangend" use="optional"/\>

[\#55](https://github.com/Geonovum/GeoBAG/issues/55) sleutelOntvangend ontbreekt
bij VBO in responsbericht

In geoBAG0101_bg0310_ent.xsd bij complex type VBO-geoBAG-identificatie is
sleutelOntvangend als verplicht attribuut toegevoegd:

\<attribute ref="StUF:sleutelOntvangend" use="required"/\>

[\#56](https://github.com/Geonovum/GeoBAG/issues/56) sleutelVerzendend moet
verplicht en sleutelOntvangend moet optioneel zijn bij VBO

In geoBAG0101_bg0310_ent.xsd bij complex type VBO-geoBAG-basis is attribuut
sleutelVerzendend gewijzigd naar ‘verplicht’ en sleutelOntvangend naar
‘optioneel’.

\<attribute ref="StUF:sleutelVerzendend" use="required"/\>  
\<attribute ref="StUF:sleutelOntvangend" use="optional" /\>

[\#57](https://github.com/Geonovum/GeoBAG/issues/57) Opnemen apart complex type
voor relaties en goed/afkeuringsberichten

In geoBAG0101_bg0310_ent.xsd is een nieuw complextype
‘PND-geoBAG-gerelateerde-identificatie’ toegevoegd met dezelfde kenmerken als
‘PND-geoBAG-identificatie’, echter zonder de attributen sleutelVerzendend en
sleutelOntvangend.

\<complexType name="PND-geoBAG-gerelateerde-identificatie"\>  
\<sequence\>  
\<element name="identificatie" type="BG:ObjectNummering-e" nillable="true"/\>  
\<element name="versie" type="BG:versie-BAG20-e" nillable="true"  
/\>  
\</sequence\>  
\<attribute ref="StUF:entiteittype" use="required" fixed="PND"/\>  
\<attribute ref="StUF:sleutelSynchronisatie" use="prohibited"/\>  
\<attribute ref="StUF:noValue" use="prohibited"/\>  
\<attribute ref="StUF:scope" use="prohibited"/\>  
\<attribute ref="StUF:verwerkingssoort" use="prohibited"/\>  
\</complexType\>

In geoBAG0101_bg0310_ent.xsd is in complex type TGOPND-geoBAG-basis bij element
‘gerelateerde’ het type veranderd van ‘PND-geoBAG-identificatie’ naar
‘PND-geoBAG-gerelateerde-identificatie’.

\<complexType name="TGOPND-geoBAG-basis"\>  
\<sequence\>  
\<element name="gerelateerde" type="BG:PND-geoBAG-gerelateerde-identificatie"
nillable="true"/\>  
\</sequence\>  
…

\</complexType\>

[\#58](https://github.com/Geonovum/GeoBAG/issues/58) Inconsistentie in
voorbeeldbestanden GeoCOG StUF:noValue voor BAG-identificatie en versienummer

In B1_gmlDi01_pand_GEO-COG.xml en B2_foutDu01_verblijfsobject.xml is element
\<versie\> aangepast naar StUF:noValue en leeg.
