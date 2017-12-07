# README
This repository provides an XML template to generate a product data feed for the Swiss marketplace [siroop](https://siroop.ch/) based on Wyominds Data Feed Manager extension for [Magento 1](https://www.wyomind.com/data-feed-manager-magento.html?a=openstream) and [Magento 2](https://www.wyomind.com/magento2/data-feed-manager-magento.html?a=openstream).

`Beispielfeed_GSF_XML.xml` is a sample feed provided by siroop, it's only part of the repository as a reference. Just create a new data feed template and copy/paste the header, product pattern and footer XML code below into the text areas provided in the feed configuration. If you purchased the extension more recently, it should already be there, but you will have to customize the attributes yourself.

## Header
```xml
<?xml version="1.0" encoding="utf-8"?>
<rss version="2.0"  xmlns:g="http://base.google.com/ns/1.0" 
  xmlns:s="https://merchants.siroop.ch/">
  <channel>
      <title>Products for Siroop Marketplace</title>
    <link>https://www.example-shop.ch</link>
    <description>This is a sample feed containing the required and recommended attributes for a variety of different products</description> 
```
## Product Pattern
```xml
<item>
<g:id>{sku}</g:id>
<g:title>{name}</g:title>
<s:long_description>{description}</s:long_description>
<s:siroop_category>{siroop_category}</s:siroop_category>
{G:IMAGE_LINK}
<g:additional_image_link/>
<!-- Availability & Price -->
<s:quantity>{qty}</s:quantity>
<g:price>{price} CHF</g:price>
<s:productvat>1</s:productvat>
<s:warranty>24</s:warranty>
<!-- Unique Product Identifiers-->
<g:gtin>{ean}</g:gtin>
<g:mpn>{mpn}</g:mpn>
<s:manufacturer_name>{manufacturer}</s:manufacturer_name>
<g:brand>{manufacturer}</g:brand>
<!-- Products Attributes -->
<s:attribute name="Zusatzinformationen">{short_description}</s:attribute>
<s:attribute name="Grösse">{size}</s:attribute>
<s:attribute name="Farbe DE">{color}</s:attribute>
<s:attribute name="Breite">{width}</s:attribute>
<s:attribute name="Höhe">{height}</s:attribute>
<s:attribute name="Tiefe">{depth}</s:attribute>
<s:attribute name="Material">{material}</s:attribute>
<s:attribute name="Volumen">{volume}</s:attribute>
<s:attribute name="Geschlecht">{gender}</s:attribute>
<s:attribute name="Lieferumfang">{delivery_contents}</s:attribute>
</item>
```
## Footer
```xml
</channel>
</rss> 
```
For questions and comments please create an issue.
