
<!-- README.md is generated from README.Rmd. Please edit that file -->

# MAVISApp

<!-- badges: start -->

[![Generic badge](https://img.shields.io/badge/Version-0.1-green.svg)]()
[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
<!-- badges: end -->

The MAVIS R shiny web application is a tool for……….

## Running the app

You can run MAVISApp from
[GitHub](https://github.com/ZekeMarshall/MAVISApp) by cloning the
repository, calling `renv::restore()`, and then calling
`shiny::runApp("app.R")`.

Future developments may support the release of MAVISApp as an R package.

## Hosting

MAVISApp is configured to be built with
[Docker](https://www.docker.com/).

To build and deploy the app on a linux server with Docker pre-installed
two approaches may be taken:

### Using Docker Manually

1.  Build the app locally with
    `docker build --no-cache -t <container registry url>/mavisapp:<version> .`.
2.  Log in to the container registry with
    `docker login <container registry url>`, using a API key.
3.  Push the image to the container registry with
    `docker push <container registry url>/mavisapp:<version>`. One of:
    4a. Log into a container registry UI through a web browser, and
    navigate to a console button which opens a terminal to the server.
    4b. ssh into the server from a local terminal.
4.  In the server, log in to the container registry with
    `docker login registry.digitalocean.com`, using a API key.
5.  Pull the image from the container registry with
    `docker pull <container registry url>/mavisapp:<version>`.
6.  Check that the image has been successfully retrieved with
    `docker images`.
7.  Check whether there is a container currently running with
    `docker ps -a`.
8.  Stop and remove this instance with `docker rm -f <instance name>`.
9.  Run the Docker container in a new instance with
    `docker run -d -p 8001:8001 --privileged=true --name <instance name> <container registry url>/mavisapp:<version>`.

### Using Docker Compose

1.  Build the app image locally with `docker compose build.`.
2.  Log in to a container registry with
    `docker login <container registry url>`, using a API key.
3.  Push the image to the container registry with `docker compose push`.
    One of: 4a. Log into a container registry UI through a web browser,
    and navigate to a console button which opens a terminal to the
    server. 4b. ssh into the server from a local terminal.
4.  In the server, log in to a container registry with
    `docker login <container registry url>`, using a API key.
5.  Check whether there is a container currently running with the same
    name using `docker ps -a`.
6.  Optionally, stop and remove this instance with
    `docker rm -f <instance name>`.
7.  Run the Docker container in a new, or updated instance with
    `docker compose up --detach`.
