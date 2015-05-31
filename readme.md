# Dockerfile: virtuoso-go-hpo
A dockerfile to invoke virtuoso to import downloaded and converted Gene Ontology (GO), Human Phenotype Ontology (HPO), and HPO Annotation (HPA) data files

# Build
At the directory containing the Dockerfile file:
```bash
$ sudo docker build -build -t virtuoso-go-hpo .
```

# Run
```bash
$ $ sudo docker run -it --link virtuoso:virtuoso -v ${HOME}/samples:/opt/Ontologies/samples virtuoso-go-hpo
$ curl \
     --form "query=SELECT COUNT(?s) FROM <http://purl.obolibrary.org/obo/go/go.owl> WHERE { ?s ?p ?o . }" \
     http://localhost:8890/sparql
$ curl \
     --form "query=SELECT COUNT(?s) FROM <http://purl.obolibrary.org/obo/hp.owl> WHERE { ?s ?p ?o . }" \
     http://localhost:8890/sparql
$ curl \
     --form "query=SELECT COUNT(?s) FROM <http://localhost/hpa.owl> WHERE { ?s ?p ?o . }" \
     http://localhost:8890/sparql
```

# Author and License
Author: MISHIMA, Hiroyuki / missy (at) be.to 

License: The MIT License
