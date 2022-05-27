# sample-kubernetes-wordsmith-project

Wordsmith is the demo project shown at DockerCon EU 2017 and 2018.

The demo app runs across three containers:

db - a Postgres database which stores words

words - a Java REST API which serves words read from the database

web - a Go web application which calls the API and builds words into sentences:
