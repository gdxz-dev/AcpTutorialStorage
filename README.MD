# Setup

## Service in docker

+ docker must be installed and running
+ install PostgreSQL
+ install Localstack

## PostgreSQL

+ docker run --env=POSTGRES_DB=postgres --env=POSTGRES_PASSWORD=postgres --env=POSTGRES_USER=postgres --env=PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/postgresql/17/bin --env=GOSU_VERSION=1.17 --env=LANG=en_US.utf8 --env=PG_MAJOR=17 --env=PG_VERSION=17.0-1.pgdg120+1 --env=PGDATA=/var/lib/postgresql/data --volume=/var/lib/postgresql/data --network=database_default -p 5432:5432 --restart=no --label='com.docker.compose.config-hash=6f262fd9f05043fb4fc99ded841baee96c18fee0211110fe857e6214ab70a854' --label='com.docker.compose.container-number=1' --label='com.docker.compose.depends_on=' --label='com.docker.compose.image=sha256:8d3be35b184e70d81e54cbcbd3df3c0b47f37d06482c0dd1c140db5dbcc6a808' --label='com.docker.compose.oneoff=False' --label='com.docker.compose.project=database' --label='com.docker.compose.project.config_files=/Users/michael/IlpRestServer/setup/docker-compose.yml' --label='com.docker.compose.project.working_dir=/Users/michael/IlpRestServer/setup' --label='com.docker.compose.service=db' --label='com.docker.compose.version=2.38.2' --runtime=runc -d --name postgres-acp postgres
  or
+ docker-compose up

## Localstack

+ docker run --rm -it -d --name localstack-main -p 127.0.0.1:4566:4566 -p 127.0.0.1:4510-4559:4510-4559 -v /var/run/docker.sock:/var/run/docker.sock -e SERVICES=dynamodb,s3 localstack/localstack
or
+ docker-compose up


AWS SDK
https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/setup-project-maven.html

AWS Examples
https://github.com/awsdocs/aws-doc-sdk-examples/blob/0b1785e42949ebf959eaa0f0da4dc2a48f92ea25/javav2/example_code/dynamodb/src/main/java/com/example/dynamodb/PutItem.java

AWS SDK BOM
https://central.sonatype.com/artifact/software.amazon.awssdk/bom

Localstack Endpoint addressing
https://docs.localstack.cloud/aws/capabilities/networking/accessing-endpoint-url/

Localstack SDK
https://docs.localstack.cloud/aws/integrations/aws-sdks/java/
