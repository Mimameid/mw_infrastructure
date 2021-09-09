Create restaurants api:

```shell
curl -XPUT "http://localhost:9200/restaurants?pretty" -d
  {
    "settings" : {
        "index" : {
            "number_of_shards" : 4,
            "number_of_replicas" : 2
        }
    }
  }
```

Add restaurant data:

```shell
curl -XPOST "http://localhost:9200/restaurants/_doc/?pretty" -H 'Content-Type: application/json' -d @<filepath>
```

Search restaurants:

```shell
curl -XGET "http://localhost:9200/restaurants/_search/?pretty" -H 'Content-Type: application/json' -d '
    {
        "index": "restaurants",
        "body": {
            "query": {
                "match": {
                    "name": "sultan"
                    },
                },
        }
    }
'
```
