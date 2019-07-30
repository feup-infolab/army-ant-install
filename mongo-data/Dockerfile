FROM mongo
COPY inex_3t_nl-documents.json ./init.json
CMD mongoimport --quiet --host mongo --db aa_inex --collection documents --type json --file /init.json
