# docker-mysqldump-to-s3
Docker container that dumps a single mysql db to an s3 bucket

### Requirements

1. Needs to be running with AWS credentials with write access to the s3 bucket (either mount the .aws dir to /root/.aws or seed them via ENV or use an IAM Role in ECS Task setup)

2. Needs to have the DB details and S3 bucket location seeded via ENV vars

   `DBHOST=<DB_SERVER_HOSTNAME>`

   `DBUSER=<DB_SERVER_USERNAME>`

   `DBPASS=<DB_SERVER_PASSWORD>`

   `DBNAME=<DATABASE_NAME>`

   `S3_BUCKET=<S3_BUCKET_NAME>` (Destination bucket for the sql dump file)

   `S3_PREFIX=<S3_PREFIX>` (Folder path in the S3 bucket)

3. Needs to have a docker storage volume that is mounted to **/dumps**
