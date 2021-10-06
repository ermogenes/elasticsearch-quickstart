# elasticsearch-quickstart

Compose file to quickstart Elasticsearch and Kibana.

⚠ _For development purposes only. DO NOT USE IN PRODUCTION._

## Starting

```bash
docker compose up
```

## Using

Credentials:

- Username: `elastic`
- Password: `abc123`

URLs:

- REST API: http://localhost:9200/
- Kibana: http://localhost:5601/

On Kibana, use the [Management > Dev Tools > Console](http://localhost:5601/app/dev_tools#/console) option.

## Examples

```
POST /teste/_doc
{
  "campo": "valor xyz",
  "campo 2": 2,
  "campo 3": {
    "campo3.1": true,
    "campo3.2": [1, 2, 3]
  }
}

POST /teste/_doc
{
  "campo": "abc xyz",
  "campo 2": 99,
  "campo 3": {
    "campo3.1": false,
    "campo3.2": [99, 99, 99]
  }
}

POST /teste/_doc
{
  "campo": "valor abc",
  "campo 2": 99,
  "campo 3": {
    "campo3.1": true,
    "campo3.2": [99, 2, 99]
  }
}

GET /teste/_search

GET /teste/_search
{
  "query": {
    "match_phrase": {
      "campo": "valor xyz"
    }
  }
}

GET /teste/_search
{
  "query": {
    "match": {
      "campo": "valor"
    }
  },
  "highlight": {
    "fields": {
      "campo": {}
    }
  }
}

DELETE /teste
```