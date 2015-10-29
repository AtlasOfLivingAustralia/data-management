data-management
===============

Data management issue tracking

Before data can be displayed in the Atlas of Living Australia (Atlas) it is subject to a data integration process consisting of:
  1. [Data mobilisation](http://www.ala.org.au/about-the-atlas/how-we-integrate-data/data-mobilisation/) —getting the data into the Atlas
  2. [Data quality assurance](http://www.ala.org.au/about-the-atlas/how-we-integrate-data/data-quality-assurance/) —checking various aspects of the data, eg the current species name
  3. [Data sensitivity check](http://www.ala.org.au/about-the-atlas/how-we-integrate-data/data-sensitivity-checks/) —to identify if the data relates to a species that is sensitive for reasons of conservation or biosecurity.

See also:
  1. [Our data providers](http://www.ala.org.au/about-the-atlas/our-data-providers/) for information on who provides our data
  2. [Atlas data](http://www.ala.org.au/about-the-atlas/atlas-data/) for information on the types and nature of the data used by the Atlas

  Knowledgebase
  -------------
  
 **1. What is the difference between collectionCode and institutioncode?**

-	Collection and institution codes are different when an institution has multiple collections – more common in the zoological collections e.g. Fish, Mammal and Insect collections at a single museum. Most of the herbaria use the same value for institutionCode and collectionCode

**2. What is the difference between eventDate and verbatimEventDate?**

-	The verbatim fields are used for raw, as provided values when there has been some processing to produce a “better” (often standardised) value in the other field.  E.g. verbatim event date of “13th November 2010” could be standardised to event Date “2010-11-15”.  Keeping the verbatim value allows a user of the record to see that a transformation has taken place.

**3. Species, how best to record these?  Will scientificName suffice, or do you require atomised names? **

-	A well formatted scientificName (Genus species author is usually enough although higher taxonomy will help with name matching if there are any conflicts (in general it’s better to also provide more atomic information if it’s available)

**3.1. What about subspecies?**

-	The taxonRank field and infraspecificEpithet in combination should handle most situations.

**3.2. And what about hybrids? What is the best way to record these?**

-	If the name is in the list we get from APNI/APC then -
taxonRank is “species” and scientificName is formatted as:
e.g. 
for Cultivar Hybrid: Grevillea 'Austraflora Canterbury Gold'
for Named Hybrid: Calassodia
for Cultivar Hybrid Formula: Dendrobium gouldii x Dendrobium 'Talasea'
for Hybrid Formula: Daviesia leptophylla Daviesia mimosoides

There's also a named hybrid autonym which looks like a normal species and a hybrid formula with a ? for second parent.

**3.3. What if the ALA can't recognise a name?**

-	If we can’t recognise a name it’ll be bumped up to the Genus or further up the tree until we can find a match (the provided name is available in a verbatimScientificName field)

**4.1. What format are date fields, e.g. dateIdentified, dateCollected, eventDate, etc.?**

-	We can do some format conversion but it’s best to provide them in ISO 8601 (https://en.wikipedia.org/wiki/ISO_8601) compliant format e.g. 2009-02-20, it’ll cope with times as well (2009-02-20T08:40Z)
