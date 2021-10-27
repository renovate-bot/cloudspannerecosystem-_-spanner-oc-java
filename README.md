# Spanner - OpenCensus Example

## About Cloud Spanner

[Cloud Spanner](https://cloud.google.com/spanner/) is a fully managed, mission-critical,
relational database service that offers transactional consistency at global scale,
schemas, SQL (ANSI 2011 with extensions), and automatic, synchronous replication
for high availability.

Be sure to activate the Cloud Spanner API on the Developer's Console to
use Cloud Spanner from your project.

See the [Spanner client lib docs](https://googleapis.dev/java/google-cloud-clients/latest/index.html?com/google/cloud/spanner/package-summary.html) to learn how to
interact with Cloud Spanner using this Client Library.

### Prerequisites
Please refer to the [getting
started](https://cloud.google.com/spanner/docs/getting-started/java/) guide.

### Authentication
See the [Authentication](https://github.com/googleapis/google-cloud-java#authentication) section in the base directory's README.

### To build the example
Create a table named 'Players' in your database.
```sql
CREATE TABLE Players (
	id STRING(30) NOT NULL,
	name STRING(30),
	email STRING(30),
) PRIMARY KEY (id);
```
You may also populate it with a sample record.
```sql
INSERT INTO Players (id,name,email)
VALUES ('a','a','a@a.com');
```
Update the instance and database names in PersonController.java to your instance and database.

```bash
$ mvn clean package
```

### To Run the example
```bash
$ mvn exec:java -Dexec.mainClass=com.example.spanner.App
```

Go to http://localhost:8080/spanner/ and, start sending read request.

## OpenCensus agent

The `ocagent` can be run directly from sources, binary, or a Docker image.
To install and build the agent, please follow the instructions from [here](https://opencensus.io/service/components/agent/install/)


### Running it
Edit the config in conf/config.yaml file to select the exporter of your choice.
Run the following command to start the OpenCensus agent.
```bash
./bin/ocagent_darwin --config=/conf/config.yaml
```

