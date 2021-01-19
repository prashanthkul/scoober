# Scooter Locator

## Steps to test the application

1. Starting the Database

   Build the database image

   ```
   cd data
   docker build -t scooters-postgis-image .
   ```

   Run the image

   ```
   docker run -d --name scooters-postgis-container -p 5555:5432 scooters-postgis-image
   ```

   If the external port is changed (other than 5555), change the `server/.env` file `PG_PORT=<NewPort>`

2. Backend code is present in the server folder. Backend is configured to run at port 4000.

   Install dependencies

   ```
   npm install
   ```

   Start the backend

   ```
   npm start
   ```

3. Front end code is present in the client folder
   Install dependencies
   ```
   npm install
   ```
   Start the frontend
   ```
   npm start
   ```

## Test Instructions

Your goal is to code a system that can fetch the closest x scooters for a given lat,lon within y meters and plot it on a map. This exercise will include front-end, backend and data storage, and you can choose any technology you’d like for each.

Steps:

1. Create the data storage for the scooters and populate data for scooters placed randomly throughout Singapore.
2. Write a backend service that can provide data to the front end for plotting the closest x scooters within y meters of a given lat,lon
3. Write front end that allows you to set:
   x scooters
   y search radius
   lat, and long
   It should fetch the data based on these params from the backend service, and it should plot on a map.

## References

Singapore max bounds are derieved from this [link](https://gist.github.com/graydon/11198540)

Postgis base image [link](https://hub.docker.com/r/postgis/postgis)

Mapping library [leaflet](https://leafletjs.com/)
