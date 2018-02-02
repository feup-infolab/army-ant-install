FROM mongo
COPY inex_3t_nl-documents.json ./init.json
CMD mongoimport --host mongo --db inex --collection documents --type json --file /init.json
