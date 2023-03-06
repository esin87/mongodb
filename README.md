![MongoDB Logo](assets/mongodb-logo.png)

# MongoDB

MongoDB is a popular non-relational, document-based database management software
that is used across industries by a variety of companies like Forbes, Toyota,
Verizon, Expedia, and [many more](https://www.mongodb.com/who-uses-mongodb).

Whether you're a data engineer looking to pick up another database format, or
whether you're a fullstack developer interested in learning more about the
database behind the
[MERN/MEAN stacks](https://medium.com/@devathon_/mean-vs-mern-stack-development-5ba3e517bc68),
you're in the right place to learn more about MongoDB.

## Learning Objectives

- Why MongoDB
- Register for a MongoDB Atlas cloud database account
- Distinguish between database server, database, collection, and documents
- Create, drop and interact with MongoDB databases and collections using the
  MongoDB Atlas cloud interface
- Create, Read, Update and Delete documents in MongoDB collections using MongoDB
  Atlas
- Use Mongo querying syntax to specify querying conditions

## Why MongoDB

MongoDB is a non-relational, document-based database. It stores data in a format
called binary JSON, or BSON. Because BSON is so close to JSON in form and
function, MongoDB lends itself very well for the database layer of fully
JavaScript stacks.

Non-relational, or NoSQL, databases are different in many ways from the SQL
databases we've worked with in training. For starters, we are not always
guaranteed the ACID principles with NoSQL databases, though MongoDB
[can be set up to enforce ACID for multi-document transactions](https://www.mongodb.com/basics/acid-transactions).

With MongoDB, there is no inherent consistency in our data structure, which SQL
tables provide. NoSQL databases are designed to accommodate more varied and
unstructured data, which is useful in scenarios where there are few or changing
requirements for the data, such as rapid app development. This flexibility in
its data model actually makes MongoDB a good database choice for
[content management on digital platforms](https://www.mongodb.com/use-cases/content-management),
which is
[how the digital design platform Canva uses MongoDB](https://www.mongodb.com/blog/post/video-canvas-lessons-scaling-mongodb-atlas-billion-documents-across-nodes).

Because MongoDB is so fast, it's also a well-suited database for handling big,
complex datasets and
[real-time analytics](https://www.mongodb.com/use-cases/analytics/real-time-analytics).
In fact, the name "Mongo"
[comes from "humongous."](https://kchodorow.com/2010/08/23/history-of-mongodb/)
The creators of MongoDB built it in part to better handle the scaling challenges
faced by databases at the time.

MongoDB Atlas also features options for
[both vertical and horizontal scaling](https://www.mongodb.com/basics/scaling),
including auto-sharding, which makes it a great choice for cloud environments.

## Getting Started on MongoDB Atlas

MongoDB is a non-relational database management software. Like many DBMS, it can
be run
[locally on your machine](https://www.mongodb.com/docs/manual/installation/) or
in the cloud.

Today we're going to get started with MongoDB's Atlas service, which is a
cloud-based offering of MongoDB. You might hear the term "Database as a Service"
(DBaaS) used to describe applications like MongoDB Atlas. Other DBaaS examples
include AWS's
[many database offerings](https://aws.amazon.com/products/databases/) (like
DynamoDB, Amazon RDS, and more) as well as
[Google](https://cloud.google.com/products/databases) and
[Azure](https://azure.microsoft.com/en-us/products/). A DBaaS allows your team
to focus on the differentiating features of your application rather than the
infrastructure or administration of the database; a DBaaS handles tasks such as
provisioning the server, installing the database, taking backups, etc.

Let's start by [navigating to MongoDB's website](https://www.mongodb.com) and
signing up or signing in.

> I usually prefer using OAuth to log into most sites, so that I don't have to
> remember (and forget) another set of credentials.

Once we've created our account or used our Google or GitHub credentials to log
in, we'll accept the terms of service and continue.

!["Accept MongoDB Privacy Policy and Terms of Service"](assets/tos.png)

After a welcome page, we're greeted with a questionnaire, which MongoDB uses to
collect data on who is signing up for their application.

Let's enter the following (you can choose a different preferred language if you
like -- Python for our data folks, Java for our fullstack folks):

!["MongoDB questionnaire 1"](assets/questionnaire1.png)

Then click the "Finish" button. This leads us to the screen where we will deploy
our first remote MongoDB database cluster. Let's select the free options, call
our cluster "Learning," then click "Create".

!["Create MongoDB cluster"](assets/deploydb.png)

When we click "Create," MongoDB provisions a cluster for us on a server in a
data center of whichever cloud provider we choose (AWS, Google Cloud, or Azure).
We get a corner of the server (which is a fancy computer), which we will share
with other MongoDB customers.

In that corner of the server, which we'll call our cluster, we can create
MongoDB databases! It takes a few minutes to "provision" the cluster, because a
lot is happening in that time. The physical infrastructure is being set up, such
as the hardware and network settings to run the cluster, as well as the software
needed to create it.

This takes us to the Security Quickstart page. For now, let's set up
authentication with a username and password. You can give your default user any
username/password combination you like. Here, I'll use "admin" and use an
auto-generated password, which I'll paste in a text file for temporary
safekeeping.

Be sure to hit "Create User" to actually create that user.

![Create User in MongoDB](assets/security-quickstart1.png)

<!-- zznAwlZm3EPxoCPy -->

<!-- 1x5opKOqfvkj3DbH -->

Next, we'll tell MongoDB where we're connecting from. Let's use our local
environment (the computer we're currently on) by clicking "Add My Current IP
Address." Note that with this setting, your cluster will only accept connections
from your current machine, so if you log into your MongoDB Atlas account from
another computer and want to connect to this cluster, you'll need to add that
computer's IP address as well.

![Configure connection in MongoDB](assets/security-quickstart2.png)

When finished, click "Finish and Close," then click "Go to Databases." If your
cluster is finished provisioning, we are ready to dive in!

## Database servers, databases, collections, and documents, oh my!

Congratulations, you've set up your MongoDB cloud database server! 🎉

Now that we have a server set up, we can create databases on it.

Click "Browse Collections" in order to view the databases on this cluster. We
don't have any currently, so let's create our first database on this cluster.
Let's choose the "Add My Own Data" option.

![Empty cluster](assets/empty-cluster.png)

Let's create a database called "mongodb-school" and create our first collection
in it, "users." Hit the "Create" button.

![New database and collection](assets/create-db.png)

Now that we have our first database with one collection established, let's add
some documents to it. We can insert documents using the "Insert Document" option
in the right corner.

When we do so, you'll notice MongoDB only enforces one field in this document
collection: the `_id`, which is the
[Mongo-generated ObjectId](https://www.mongodb.com/docs/manual/reference/method/ObjectId/),
a UUID for each document. Let's fill the field with some properties that a user
might have.

![Create document](assets/create-document.png)

Click "Insert" to add that document to your users collection. We can also add
multiple users. Click "Insert Document" again, and this time click on the array
brackets for the text field upload. Copy and paste the
[users.json](data/users.json) data into the field. Click the "Insert" button.

**💡 What do you notice about the data?**

**💡 How does the behavior of MongoDB contrast so far to SQL databases?**

It's beyond the scope of today's work, but MongoDB Atlas does offer the ability
to define [schema](https://www.mongodb.com/docs/atlas/app-services/schemas/) for
your data. Additionally, third-party libraries (like
[Mongoose](https://mongoosejs.com/) for Node.js applications) give us a
programmatic way to define schema for our application data.

**💡 What is the relationship between a database server, a database, a
collection, and a document in MongoDB?**

## CRUD with Documents, Collections, and Databases

We have created a database server, a database, a collection, and multiple
documents. So far, we've been able to create documents as well as read all of
our documents.

What if we want to query for particular data? We can use MongoDB's powerful
[query syntax](https://www.mongodb.com/docs/manual/tutorial/query-documents/) in
order to do so.

Let's drop our current users collection and create a new one using the
[users2.json](data/users2.json) file. This data is courtesy of the Dummy JSON
website. This data has many more fields and is also more consistently structured
than the previous data we were working with.

When we are done with a database, we can drop the database as well.
