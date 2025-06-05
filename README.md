# era-dcat-ap-feed
LDES feed for ERA's DCAT-AP metadata

This is a proof-of-concept [RDF-Connect](https://rdf-connect.github.io/) pipeline to produce a [DCAT-AP-Feed](https://semiceu.github.io/LDES-DCAT-AP-feeds/index.html) from the EU Railway Agency's DCAT-AP metadata, available as a queryable named graph at <http://data.europa.eu/949/graph/uat/dcat>.

The [pipeline](https://github.com/rdf-connect/era-dcat-ap-feed/blob/main/pipeline/rdfc-pipeline.ttl) is executed periodically (every 12 hours) as a Github [action](https://github.com/rdf-connect/era-dcat-ap-feed/blob/main/.github/workflows/create-feed.yml) to:
1. fetch the DCAT-AP data from ERA's servers
2. detect any changes in the described assets
3. write detected changes to the LDES feed

The LDES feed is kept as a collection of static documents which are served using Github pages. The entrypoint to the LDES is: <https://rdf-connect.github.io/era-dcat-ap-feed/index.trig>
