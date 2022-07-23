# Elasticsearch 8 and the Elastic Stack: In Depth and Hands On

### A Udemy Course

[Course](https://www.udemy.com/course/elasticsearch-7-and-elastic-stack/) |
[ElasticSearch Docs](https://www.elastic.co/webinars/getting-started-elasticsearch?rogue=webinar&baymax=&storm=hero&elektra=home)

## TOC

- [Introduction](#introduction)
- [Elasticsearch Overview](#elasticsearch-overview)

## Introduction

### Basic Commands
 - start elasticsearch on mac (installed with homebrew): `elasticsearch`
 - poll server: `curl -XGET 127.0.0.1:9200`

 ```json
 {
  "name" : "node-1",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "7zDbLjTATs-KncZp6JLORg",
  "version" : {
    "number" : "7.17.4",
    "build_flavor" : "default",
    "build_type" : "tar",
    "build_hash" : "79878662c54c886ae89206c685d9f1051a9d6411",
    "build_date" : "2022-05-18T18:04:20.964345128Z",
    "build_snapshot" : false,
    "lucene_version" : "8.11.1",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}
 ```
 
 - submit to elasticsearch (single document) to index: `curl -H "Content-Type: application/json" -XPUT 127.0.0.1:9200/shakespeare --data-binary @shakes-mapping.json`

 or
 
 - submit to elasticsearch (lots of documents) to index: `curl -H "Content-Type: application/json" -XPUT '127.0.0.1:9200/shakespeare/_bulk' --data-binary @shakespeare_8.0.json`
 - simple search for a phrase: `curl -H "Content-Type:application/json -XGET '127.0.0.1:9200/shakespeare/_search?pretty' -d`
 
 ```bash
 dquote> {
 dquote> "query" : {
 dquote> "match_phrase" : {
 dquote> "text-entry" : "to be or not to be"
 dquote> }
 dquote> }
 dquote> }'
 ```


[back](#toc)

## Elasticsearch Overview

[back](#toc)