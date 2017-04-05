+++
date = "2017-04-05T06:25:21-07:00"
description = "A list of work projects"
draft = true
tags = [
  "web",
  "tech",
]
title = "what ive done"
topics = [
  "work",
  "computer"
]

+++

Here is a list of what I have put together or worked on for some significant
amount over the last couple of years on the job.

* [Monitoring](/monitoring-work) will get its own post eventually.
* We migrated from a single service which ran on a single instance in Classic
EC2 to a half dozen services running in separate VPCs, each with autoscaling
instances behind an elastic load balancer to provide high availability. Getting
all the plumbing on this right was a major effort.
* Wrote an automation script which packaged service config files into a
Debian package which would simply be pulled into a new instance like any other
versioned package.
* Worked on a couple iterations of an ELK stack accept logs and structured data
* Prototyped a stack which used Amazon IoT, Kinesis Firehose, DynamoDB, and S3
to accept mobile data streams and store them for business intelligence. The
components were held together with Simple Notification Service and Lambda
functions in a serverless fashion.
* Hacked out numerous one-off scripts in bash and Ruby to automate the recurring maintenance
chores in our environments. For instance we needed something to clean up user
logins which were not needed any more, scripts to take reference snapshots of
volumes for safekeeping, and so on.
* Worked on some scripts to transfer information from our services to a data
warehouse running on Amazon Redshift (so-called ETL scripts) so we would have
an analytics service for our own use.
* Migrated some administrative tools off of dedicated virtual machines onto
containers which would run under Rancher. The idea was that we could pack
a bunch of light-duty tasks together on a cluster of instances which would run the
same workloads with much higher density, reducing costs and maintenance.
* Wrote a simple Sinatra app which would gather information from our environments (addresses,
instance IDs, running state, and so on) and display them in a tabular format. This
saved me a lot of time switching between different dashboards and running things through
the command line interface just to keep things oriented.
*
