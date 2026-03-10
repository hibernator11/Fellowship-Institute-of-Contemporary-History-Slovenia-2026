# Fellowship-Institute-of-Contemporary-History-Slovenia-2026

This repository contains the information concerning the [Visiting Fellowship 2025/26 (March 2026) at the Institute of Contemporary History in Ljubljana](https://inz.si/gostujoci-raziskovalec/gustavo-candela-phd/). It describes the main goals and outputs of the fellowship.


## Lecture - Wednesday, March 11, 2026
[Data Publishing and Use in the Humanities: A Labs Approach](https://dariah.si/history-on-the-edge-data-publishing-and-use-in-the-humanities-a-labs-approach/)

This presentation will introduce the publication and use of digital collections in the humanities following best practices and guidelines promoted by the International GLAM Labs Community and Collections as data initiatives. It will describe previous and ongoing work concerning the employment of reproducible code and workflows to reuse a wide diversity of content including metadata, bibliographic records or images. It will also present advanced techniques based on information retrieval, visualisation, data quality and enrichment with external repositories. Existing data research infrastructures and platforms in Europe will be outlined.

## Datasets

A selection of digital collections are available at [https://dariah.si/projects/research-data-collections/](https://dariah.si/projects/research-data-collections/), in particular, the [Database of Victims of the Republic of Slovenia during and immediately after the Second World War](https://sistory.si/eng/ww2?t=desc). The list, containing more than 100,000 persons, is a systematic inventory of military and civilian persons who had residency rights in the territory of today's Republic of Slovenia during World War II and immediately after (May 1940 − January 1946) and lost their lives due to wartime and post-war (revolutionary) violence or consequences of war.

<img src="img/database.png" width="50%">

## Examples of records

These records were extracted manually from the website and linked to Wikidata.

- https://sistory.si/eng/ww2/CE087EAC-BF00-4948-AA8D-BA678EB4E05D (place of death Hrib: https://www.wikidata.org/wiki/Q2055580)
- https://sistory.si/eng/ww2/055BE140-1B85-4572-BE94-6D5798EB6524 (place of death Travna gora: https://www.wikidata.org/wiki/Q2058146)
- https://sistory.si/eng/ww2/2D461E96-1274-46FE-895B-133250653872 (place of death Celje: https://www.wikidata.org/wiki/Q1012)
- https://sistory.si/eng/ww2/E4D233E0-AF3B-4A76-90C9-CBBC97680632 (place of death Resnik, Pohorje: https://www.wikidata.org/wiki/Q218853)
- https://sistory.si/eng/ww2/1C5D7D68-A4E8-4E83-9DF3-C003B5161780 (place of death Kajski rajon, Kirovska oblast: https://www.wikidata.org/wiki/Q5387)

As a result, we can create a simple visualisation using the [Wikidata SPARQL endpoint](https://w.wiki/JH3F):

```
#defaultView:Map      
select ?s ?sLabel ?coord ?image 
where {
     values ?s {wd:Q2055580 wd:Q2058146 wd:Q1012 wd:Q218853 wd:Q5387}
      ?s wdt:P625 ?coord .
      ?s wdt:P18 ?image
   
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],es". }
}
```
<img src="img/map.png" width="50%">

## Using LLM to enrich the data

Using the following prompt 

*Identify 10 places of death from the website https://sistory.si. Then, try to identify the Wikidata identifier for each of them and return them as a list.

## Ideas

- [Datasheets for Digital Cultural Heritage Datasets](https://doi.org/10.5281/zenodo.15828222)
- Visualisations (e.g., maps and charts)
- Enrichment with external repositories (e.g., Wikidata)
- New section in the website as GLAM Labs (e.g., see the [Data Foundry at the National Library of Scotland](https://data.nls.uk/))
- Examples of use based on reproducible code and Jupyter Notebooks (e.g., see https://doi.org/10.1002/asi.24835)
- API access
- Integration with European infrastructures (e.g., ECCCH and EOSC)
- Open Access practices: Zenodo, Social Sciences and Humanities Open Marketplace, OpenAIRE

## References

- https://inz.si/gostujoci-raziskovalec/gustavo-candela-phd/
- https://dariah.si/history-on-the-edge-data-publishing-and-use-in-the-humanities-a-labs-approach/
- Gustavo Candela. 2025. Browsing Linked Open Data in Cultural Heritage: A Shareable Visual Configuration Approach. J. Comput. Cult. Herit. 18, 1, Article 9 (March 2025), 15 pages. https://doi.org/10.1145/3707647
- Candela, G. (2023). An automatic data quality approach to assess semantic data from cultural heritage institutions. Journal of the Association for Information Science and Technology, 74(7), 866–878. https://doi.org/10.1002/asi.24761
- Candela, G., Chambers, S., Irollo, A., Freire, N., Dritsou, V., Isaac, A., Benardou, A., Garnett, V., & Tasovac, T. (n.d.). A Workflow to publish Collections as Data: looking back at Europeana.eu and forward to the common European data space for cultural heritage (Version 1, Vol. 965). Transformations: A DARIAH Journal . https://doi.org/10.46298/transformations.14774
- Candela, G., Rosiński, C., & Margraf, A. (2025). A reproducible framework to publish and reuse Collections as data: the case of the European Literary Bibliography (Version 4, Vol. 965, Issue 170). Transformations: A DARIAH Journal . https://doi.org/10.46298/transformations.14729
- Candela, G., Cuper, M., Holownia, O., Gabriëls, N., Dobreva, M., Mahey, M. (2024). A Systematic Review of Wikidata in GLAM Institutions: a Labs Approach. In: Antonacopoulos, A., et al. Linking Theory and Practice of Digital Libraries. TPDL 2024. Lecture Notes in Computer Science, vol 15178. Springer, Cham. https://doi.org/10.1007/978-3-031-72440-4_4
- Gustavo Candela, Sally Chambers, Tim Sherratt: An approach to assess the quality of Jupyter projects published by GLAM institutions. J. Assoc. Inf. Sci. Technol. 74(13): 1550-1564 (2023)
