# Hasura Frontend Docker Setup

If you want a one-stop shp for setting up a local dev env for Frontend work at Hasura, look no further.

There are 3 basic steps:

1. Build the sqlite dc-agent
1. Run the docker compose
1. Import the `default_metadata.json` metadata to your local HGE instance

Here's how you do it...

1. Checkout the [main Hasura monorepo](https://github.com/hasura/graphql-engine-mono), `cd` into `dc-agents/sqlite` and run

```console
docker build . -t sqlite-agent
```

2. Now, back in this repo, at the root dir, run:

```console
   docker compose up -d
```

3. Go to Settings > Metadata Actions -- [or just click here](http://localhost:8080/console/settings/metadata-actions) (you will need to enter your admin secret: `moocow`)
4. Select `Import Metadata` and select `default_metadata.json`

After you've done this you should have a fully functional instance of Hasura Community Edition (open source) with a Postgres, sqlite, MySql, and BigQuery database fully connected and tracked.

Each database also has a `namespace` so it should be simple to tell them apart form the API Explorer (since so many of the test databases are the same or similar data).

Stay tuned, I plan to add more here so we can have Athena, Snowflake, Cockroach, Sql Server, and whatever else.

You may also need to flip the [feature flags here](http://localhost:4200/settings/feature-flags) to see everything in your local instance correctly.

## Running the latest HGE versions

It's necessary to update the HGE image being used in the docker-compose.yml file as updates are made. So feel free to change it as needed. I will try and keep this updated, but I may not do it quicker than you : )
