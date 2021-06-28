
# Vercel + Planetscale
A [next.js](https://nextjs.org/) app deployed to [vercel](https://vercel.com) with a [planetscale](https://planetscale.com) integration. This example app uses the [planetscale-node](https://github.com/planetscale/planetscale-node) client to query the database

## Setup database
- Install [Planetscale CLI](https://planetscale.com/cli)
- Authenticate the CLI
```sh
pscale auth login
```
- Create a new database
```sh
pscale database create your-db-name
```
- Connect to your database 
```sh
pscale shell your-org-name your-db-name
```
- Insert example tables
```sql
CREATE TABLE Users (
  id int NOT NULL AUTO_INCREMENT,
  email varchar(255) NOT NULL,
  password varchar(255) NOT NULL,
  name varchar(255),
);
```

## Deploy to vercel
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2Fplanetscale%2Fvercel-next-js&project-name=planetscale-next-js&repository-name=planetscale-next-js&integration-ids=oac_ni8CGiTU3oM25q1k2L6unVMp)


## Install integration
- Select the integration from the marketplace and link it with the Vercel project(s).
- The integration will automatically add the following environment variables to your Vercel project(s)
  - `PLANETSCALE_DB`
  - `PLANETSCALE_ORG`
  - `PLANETSCALE_TOKEN`
  - `PLANETSCALE_TOKEN_NAME` 

_These environment variables are used by [planetscale-node](https://github.com/planetscale/planetscale-node) client to connect to your database_
- Re-deploy your application after the installation is complete and you will have a working app.
