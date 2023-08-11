# Time Series Of All Red Hook Citi Bike Docks

## Red Hook Stations

For my analysis I first had to manually create a table of stations located in Red Hook.

| ID                                   | Name                       |
|--------------------------------------|----------------------------|
| 66de1516-0aca-11e7-82f6-3863bb44ef7c | Coffey St & Conover St     |
| 66de11bc-0aca-11e7-82f6-3863bb44ef7c | Wolcott St & Dwight St     |
| 66de4897-0aca-11e7-82f6-3863bb44ef7c | Columbia St & W 9 St       |
| 66de103b-0aca-11e7-82f6-3863bb44ef7c | Dwight St & Van Dyke St    |
| 66de14af-0aca-11e7-82f6-3863bb44ef7c | Van Brunt St & Wolcott St  |
| 66de0cab-0aca-11e7-82f6-3863bb44ef7c | Columbia St & Lorraine St  |
| c01a9c97-6c04-4e3f-ad0b-958801d94ca1 | Bay St & Court St          |
| 40042fb4-6ddd-4f74-bb52-5af3e4e08c8d | Coffey St & Ferris St      |
| 66de47bf-0aca-11e7-82f6-3863bb44ef7c | Commerce St & Van Brunt St |
| 66de18d7-0aca-11e7-82f6-3863bb44ef7c | Sigourney St & Columbia St |
| 66de0a78-0aca-11e7-82f6-3863bb44ef7c | Henry St & Bay St          |
| 66de482a-0aca-11e7-82f6-3863bb44ef7c | Richards St & Delavan St   |
| 633fbc4c-7617-47ba-a393-aad7a8d26a3e | Van Brunt St & Van Dyke St |
| 66de1295-0aca-11e7-82f6-3863bb44ef7c | Pioneer St & Richards St   |
| 66de08c9-0aca-11e7-82f6-3863bb44ef7c | Clinton St & Centre St     |
| 66de1368-0aca-11e7-82f6-3863bb44ef7c | Pioneer St & Van Brunt St  |
| 66de48f9-0aca-11e7-82f6-3863bb44ef7c | Henry St & W 9 St          |
| 66de44ba-0aca-11e7-82f6-3863bb44ef7c | Carroll St & Columbia St   |
| 66de63cd-0aca-11e7-82f6-3863bb44ef7c | Columbia St & Degraw St    |

## Station Info

To take a quick peak at the current state of the Citi Bike docks in Red Hook you can run the following command:

```shell
./bin/dockscan info \
  --id 66de1516-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de11bc-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de4897-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de103b-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de14af-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de0cab-0aca-11e7-82f6-3863bb44ef7c \
  --id c01a9c97-6c04-4e3f-ad0b-958801d94ca1 \
  --id 40042fb4-6ddd-4f74-bb52-5af3e4e08c8d \
  --id 66de47bf-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de18d7-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de0a78-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de482a-0aca-11e7-82f6-3863bb44ef7c \
  --id 633fbc4c-7617-47ba-a393-aad7a8d26a3e \
  --id 66de1295-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de08c9-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de1368-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de48f9-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de44ba-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de63cd-0aca-11e7-82f6-3863bb44ef7c | jq .
```

## Time Series Data

In order to create CSVs with time series data you can run:

```shell
./bin/dockscan ts \
  --exclude Longitude,Latitude,Location,ID \
  --interval 300 \
  --id 66de1516-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de11bc-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de4897-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de103b-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de14af-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de0cab-0aca-11e7-82f6-3863bb44ef7c \
  --id c01a9c97-6c04-4e3f-ad0b-958801d94ca1 \
  --id 40042fb4-6ddd-4f74-bb52-5af3e4e08c8d \
  --id 66de47bf-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de18d7-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de0a78-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de482a-0aca-11e7-82f6-3863bb44ef7c \
  --id 633fbc4c-7617-47ba-a393-aad7a8d26a3e \
  --id 66de1295-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de08c9-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de1368-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de48f9-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de44ba-0aca-11e7-82f6-3863bb44ef7c \
  --id 66de63cd-0aca-11e7-82f6-3863bb44ef7c \
  --csv \
  --output ~/Documents/citibike/
```

Break down of the command:

- `./bin/dockscan ts`: This initiates the time series data collection command of `dockscan`.
- `--exclude Longitude,Latitude,Location,ID`: This excludes the specified columns from the output CSV file.
- `--interval 300`: This fetches data every 300 seconds (or 5 minutes).
- `--id 581211b2-4e42-48f2-8a8f-5f968cb1c5df`: This specifies the ID of the station you are interested in. Replace it
  with the ID of the station in Red Hook you are tracking.
- `--csv`: This specifies that the output should be in CSV format.
- `--output-dir ~/Documents/citibike/`: This specifies the directory where the output CSV file will be stored, which in
  this case is the `citibike` folder inside the `Documents` directory. You can modify this path as per your needs.