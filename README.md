# MongoDB

Why MongoDB

## Learning Objectives

- Review nonrelational databases
- Register for a MongoDB Atlas cloud database account
- Distinguish between database server, database, collection, and documents
- Create, drop and interact with MongoDB databases and collections using the
  Atlas cloud interface
- Create, Read, Update and Delete documents in MongoDB collections using MongoDB
  Atlas
- Use Mongo querying syntax to specify querying conditions

## Why Nonrelational?

MongoDB is a non-relational, document-based database. It stores data in
something called BSON, which stands for binary JSON, which as the name implies,
is very close to JSON.

Non-relational, or NoSQL, databases are very different in some ways from the SQL
databases we've worked with.

For starters, we are not always guaranteed the ACID guarantees with NoSQL
databases, though some, like MongoDB, do enforce ACID. We also don't inherently
have consistency in our data structure, which SQL tables provide. NoSQL
databases are generally designed for more flexibility in data, which is useful
in scenarios where there are little or rapidly changing requirements for the
data. Flexibility in its data model makes MongoDB a good choice for content
management.

Because MongoDB is so fast, it's also a well-suited database for handling big,
complex datasets and real-time analytics.

MongoDB Atlas features options for
[both vertical and horizontal scaling](https://www.mongodb.com/basics/scaling),
including auto-sharding, that make it a great choice for cloud environments.

## Getting Started on MongoDB Atlas

MongoDB is a non-relational database management software. Like many DBMS, it can
be run locally on your machine or in the cloud.

Today we're going to get started with MongoDB's Atlas service, which is a
cloud-based offering of MongoDB. You might hear the term Database as a Service
(DBaaS) used to describe applications like MongoDB Atlas, Amazon's DynamoDB,
Google Cloud Firestore, and many others. A DBaaS allows team members to focus on
the differentiating features of their application rather than the infrastructure
or database administrative tasks such as provisioning the server, installing the
database, taking backups, etc.

Let's start by signing in -- I prefer using OAuth to log into MongoDB and most
other sites, so that I don't have to remember (forget) another set of
credentials.

We'll accept the terms of service and continue.

!["Accept MongoDB Privacy Policy and Terms of Service"](assets/tos.png)

After a welcome page, we're greeted with a questionnaire, which MongoDB is using
to collect data on who is signing up for their application.

Let's enter the following (you can choose a different preferred language if you
like):

!["MongoDB questionnaire 1"](assets/questionnaire1.png)

Then click the "Finish" button. This leads us to the screen where we will deploy
our first remote MongoDB database cluster. Let's select the free options, call
our cluster "Learning," then click "Create".

!["Create MongoDB cluster"](assets/deploydb.png)

When we click "Create," MongoDB provisions a corner of a cluster for us on a
server in a data center of whichever cloud provider we choose. We get a piece of
the server (a fancy computer), which we share with other MongoDB customers.

In that corner of the server, which we'll call our cluster, we can create
MongoDB databases! It takes a few minutes to "provision" the cluster, because a
lot is happening in that time. The physical infrastructure is being set up, such
as the hardware and network resources to run the cluster, as well as the
software needed to create it.

This takes us to the Security Quickstart page. For now, let's set up
authentication with a username and password, and tell Atlas that we are
connecting from our local environment. You can give your default user any
username/password combination you like. Here, I'll use admin and use an
auto-generated password, which I'll paste in a text file for temporary
safekeeping.

Be sure to hit "Create User" to actually create that user.

![Create User in MongoDB](assets/security-quickstart1.png)

<!-- zznAwlZm3EPxoCPy -->

Next, we'll tell MongoDB where we're connecting from. Let's use our local
environment (the computer we're currently on) by clicking "Add My Current IP
Address." Note that it'll only accept connections from your current machine.

![Configure connection in MongoDB](assets/security-quickstart2.png)

When finished, click "Finish and Close," then click "Go to Databases." If your
cluster is finished provisioning, we are ready to dive in!

##

## References
