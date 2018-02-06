FROM mongo
COPY inex_3t_nl-documents.json ./init.json
CMD mongoimport --quiet --host mongo --db inex --collection documents --type json --file /init.json
