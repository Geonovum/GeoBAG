Release notes StUF-Geo BAG versie 1.1.1 (Geo-BAG koppelvlak)
============================================================

Versie 1.1.1 is een bugfix release van versie 1.1 waarin de volgende issues
opgelost:

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

In geoBAG0101

Aan TGOPND-geoBAG-basis is type veranderd van PND-geoBAG-identificatie naar
PND-geoBAG-gerelateerde-identificatie, waarbij nieuw complextype
PND-geoBAG-gerelateerde-identificatie zonder de attributen sleutelVerzendend en
sleutelOntvangend.
