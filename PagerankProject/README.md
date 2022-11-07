# This project will implement ranking of pages in search engine.
## Question
<img width="206" alt="image" src="https://user-images.githubusercontent.com/55336314/200246284-da39cfd3-9fae-4bfe-a665-dd534e93b594.png">

**Formular**

PR(A) = (1-d)/N + d *(PR(C))

PR(B) = (1-d)/N + d *(PR(A)/2)

PR(C) = (1-d)/N + d *(PR(B) + PR(A)/2)

in this case d=0.85, N=1

N is the number of documents

Some formula set N to be 1

d is the damping factor

## Process
### Study PageRank Theory
### PageRank + PySpark + GCP
* Set up PySpark on GCP
* Do this question using PySpark
### PageRank + Scala + GCP
* Set up PySpark on GCP
* Do this question using Scala

More details [slides](https://docs.google.com/presentation/d/17btBlN1gR-NkBgm8s3wEd3bI3PgRXvax15GL5T6fP1w/edit#slide=id.g184994c5208_0_38)
