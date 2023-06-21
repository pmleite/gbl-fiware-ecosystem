<img src="./img/banner.png">

# GlobalEDA Fiware

In this repository you can find the necessary files to run **Fiware** on **Docker**. All files can be found here except the volumes used during development. The `Main.postman_collection.json` file contains the Postman collection which can be used to create the entities and service group shown below and the file `Grafana_Dashboard.json` can be imported into Grafana. 

The data stored in FIWARE is randomized and generated by two dummy devices.

**Services related to FIWARE:**

- Fiware Orion Context Broker
- Fiware Iot Agent JSON
- Fiware Cygnus
- Grafana
- MongoDB
- MySQL
- NGINX

If you want to connect physical gateways and sensors you will need to deploy chirpstack.

**Services related to Chirpstack**

- Chirpstack
- Chirpstack-gateway-bridge-eu868
- Chirpstack-rest-api
- Postgres
- Redis
- Mosquitto
- InfluxDB

## Usage (Docker)

1. Clone this repository and open it on a terminal.
2. Navigate to the ./Docker/FIWARE directory and run `docker compose up` to start all FIWARE services.
3. If you want to use chirpstack, navigate to the ./Docker/CHIRPSTACK directory and run `docker compose up`.

## Usage (Postman)

1. Import the `Main.postman_collection.json` collection.
2. Send all requests in order.

## Usage (Grafana, Data Visualization)

1. Browse to `localhost:3000` and sign in with the user `admin` and password `admin`.
2. Open the data sources tab and add a new MySQL source, the host is `mysql-db`, the user is `root` and the password `Passw0rd`.
3. If using chirpstack, make sure to also setup influxdb.
4. Create a new dashboard and by adding a new panel you will be able to access the data from `Device001`.
5. Alternatively, you can import the `Grafana_Dashboard.json` file located in the `exports` directory.

## Entity/Device Structure

- Island:001 (São Miguel)
  - Store:001
    - ~
    - ~
  - Park:001
    - Temperature
    - Humidity
- Island:002 (Santa Maria)
    - Store:002
      - ~
      - ~
  - Park:002
    - Visitors
    - Wind Speed
  
- Devices
  - Device001 (Linked to Park001)
    - Temperature
    - Humidity
  - Device002 (Linked to Park002)
    - Visitors
    - Wind Speed