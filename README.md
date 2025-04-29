# K8s Kind Voting App

This is a Voting Application, we used this app to vote and there is a Result dashboard where you can see the result.

## Architecture

![Architecture Digram](architecture.excalidraw.png)


## output

![Voting App Dashboard]![image](https://github.com/user-attachments/assets/d4c5e290-7975-49a9-84d7-742d362019eb)
![Result Dashboard]![image](https://github.com/user-attachments/assets/7a83c595-0ba5-4095-964c-43834a33ec77)

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



### Keep Learning !
### Keep Growing !

