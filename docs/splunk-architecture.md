# Splunk Architecture

Splunk processes and analyzes machine data using a distributed architecture composed of several core components. 

## Splunk Data Flow Architecture

```
        +--------------------+
        |   Log Sources      |
        | (Servers / Apps)   |
        +---------+----------+
                  |
                  v
        +--------------------+
        | Universal Forwarder|
        |  (Collects Logs)   |
        +---------+----------+
                  |
                  v
        +--------------------+
        |      Indexer       |
        | (Parses & Stores)  |
        +---------+----------+
                  |
                  v
        +--------------------+
        |    Search Head     |
        | (Runs SPL Queries) |
        +---------+----------+
                  |
                  v
        +--------------------+
        | Dashboards / Alerts|
        |  Visualization     |
        +--------------------+
```

## Splunk Instance

A Splunk instance is a running installation of Splunk software on a machine.
After configuration, the instance performs different roles in the Splunk environment.

## Core Processing Components

### Forwarder

Forwarders collect log data from source machines and send it to Splunk for processing.

Two types of forwarders exist:

**Universal Forwarder**

* Lightweight agent
* Collects and forwards data only
* Installed on source hosts

**Heavy Forwarder**

* Full Splunk Enterprise instance
* Can parse and filter data before forwarding

### Indexer

Indexers receive data from forwarders and process it into searchable events.

Responsibilities of an indexer include:

* Breaking raw data into events
* Extracting metadata fields
* Assigning timestamps
* Storing indexed data on disk

### Search Head

The search head is the interface where users perform searches, create dashboards, and analyze data.

Search heads send search queries to indexers and combine the results for display.

## Data Storage (Buckets)

Splunk stores indexed data in buckets that represent different stages of the data lifecycle.

Hot Bucket
Data actively being written.

Warm Bucket
Recently indexed data.

Cold Bucket
Older searchable data stored in long-term storage.

Frozen Bucket
Data archived or deleted.

Thawed Bucket
Frozen data restored for searching.



## Summary

The main components of Splunk architecture are:

* Forwarders (data collection)
* Indexers (data processing and storage)
* Search Heads (data searching and visualization)

