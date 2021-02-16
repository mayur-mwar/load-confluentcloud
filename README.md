# TO SETUP DEMO

1. create a .env file with the follwing properties
```
BOOTSTRAP_SERVERS=
API_KEY=
API_SECRET=
SCHEMA_REGISTRY_URL=
SR_API_SECRET=
```

2. Bring up connect via docker
```
docker compose up -d
```

3. Check that it is running
```
docker logs connect 

docker-compose exec connect curl -s -X GET http://connect:8083/connectors | jq .

docker-compose exec connect curl -s -X GET http://connect:8083/connector-plugins | jq .
```

4. Move the csv file to be loaded under the folder /data/input. 


5. Load the csv file aml.csv by  running the submit-connector.sh script. 

./scripts/connectors/submit-connector.sh scripts/connectors/load-csv.json
```