# Hadoop 
IBM Hadoop 101 course

## Architecture
cluster -> rack -> node

## HDFS
* Not POSIX compliant
* File blocks: default 64MB, recommend 128MB

### HDFS Command
`hdfs dfs -ls`

#### POSIX-like commands
cat, chgrp, chmod, chown, cp, du, ls, mkdir, mv, rm, stat, tail

#### HDFS - specific commands
* copyFromLocal / put, copyToLocal / get 
* getMerge: gets all files and merges and sorts them to only one file on local filesystem
* setRep: sets the replication factor of a file (files)

## MapReduce
* only one namenode per cluster
* only one JobTracker per cluster

## Hadoop 2.2 Architecture (YARN)
