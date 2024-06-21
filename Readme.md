# User-Email Micro Services Project

This repository contains two microservices, user_microservice and email_microservice, along with a docker-compose.yml file to run them together using Docker Compose.

## What does it do?
When posting a User with a name and an email, the microservices, connected to the RabbitMQ Broker will produce and consume the message.
A welcoming email is sent to the user's email and this email is saved to the emails database.

## How it works?
 - The user_microservice creates a User, saves it to the database and produces a message with the user data (email and name) to the broker.
 - The email_microservice consumes the message in the broker, sends a welcoming email to the user's email, and saves it to the emails database.

Database used is Supabase

## Prerequisites

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

# How to run it

## Clone the Repository

To clone this repository along with its submodules, run the following command:

sh
git clone --recurse-submodules https://github.com/brenokleine/microservices-central-repo

Go inside the project directory with the following command:
sh
cd microservices-user-email-central-repo
 

If you have already cloned the repository without submodules, initialize and update the submodules with:
sh
git submodule update --init --recursive

## Build and run the services

To build and run the services, use Docker Compose:

sh
docker-compose up --build
