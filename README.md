## Change Data Capture Dealer (CDC Dealer) Project

### Description

The main concept is to have "data dealers" that ingest and distribute raw data changes for the consumers.

Each consumer has it's own needs so each one of them should receive the fields that they are interested.
When the pipeline runs, each configured dealer can be executed and distribute changes by the interested consumers.

## CDC Role:
 - Knows where the raw data is, how to get it and access it
 - Knows what changed since the last run
 - Knows who needs what
 - Distribute specific data for each consumer through kafka topics 


## Configure a consumer

Each Consumer just has to:
- Add a config file to one dealer or more with which data needed
- Consume data from the specific topic

For each new registered consumer the CDC Dealer will:
- Create a Kafka Topic (if doesn't exit already)
- Send bulk data (first run) or deltas only



## Current Stack
- Python
- Kakfa (Broker)
- Bash (Pipeline)
- Postgres (Database)