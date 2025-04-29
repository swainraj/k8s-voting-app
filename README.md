# K8s Kind Voting App

This project enables users to cast votes through a Python and Flask-based web interface. Voting data is then stored and managed within a Redis in-memory data structure. A .NET worker service processes these votes, and the final results are persisted in a PostgreSQL database ("db"). Users can then view the aggregated results through a separate interface.

## Architecture

![Architecture Digram](architecture.excalidraw.png)


## output

- <b>Voting App Dashboard</b>
![image](https://github.com/user-attachments/assets/d4c5e290-7975-49a9-84d7-742d362019eb)

- <b>Result Dashboard</b>
![image](https://github.com/user-attachments/assets/7a83c595-0ba5-4095-964c-43834a33ec77)

## Observability

![Grafana diagram](grafana.png)
![Prometheus diagram](prometheus.png)

* A front-end web app in [Python](/vote) which lets you vote between two options
* A [Redis](https://hub.docker.com/_/redis/) which collects new votes
* A [.NET](/worker/) worker which consumes votes and stores them in…
* A [Postgres](https://hub.docker.com/_/postgres/) database backed by a Docker volume
* A [Node.js](/result) web app which shows the results of the voting in real time



### Project Title: 

Automated Deployment of Scalable Applications on AWS EKS.

### Keep Learning, Keep Growing !!

