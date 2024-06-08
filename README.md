# Digitalskola - Datakage - Project 2

This project demonstrates how DBT (Data Build Tool) can effectively transform data. The data flow for this project is:

**Upload CSV -> Postgres Database -> Transform Raw Tables -> Specific Tables Based on Business Needs**

## Table of Contents
- [Setup](#setup)
- [Data Upload](#data-upload)
- [Running DBT](#running-dbt)

## Setup

1. **Create a Docker Compose Configuration**
   Create a `docker-compose.yml` file that includes:
   - A Postgres container: Used to store data.
   - A Python container: Environment to run DBT commands.

2. **Start the Container**
   docker-compose up -d

3. **Data Upload**
   - Connect to the Database with DBeaver
      Open DBeaver and create a new connection using the following details:
      Host: localhost
      Port: 5432
      Database: db
      User: user
      Password: password

  - Upload CSV Files into the Database

4. **Running DBT**
   - Test DBT Environment
   docker-compose exec python bash -c "dbt debug --profile-dir ./ --project-dir ./"
   - Run DBT Transformations
   docker-compose exec python bash -c "dbt run --profile-dir ./ --project-dir ./"




