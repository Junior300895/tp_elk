# Requête sur kibana

GET hol_devoxxfr_11/_search
{
  "query": {
    "match": {
      "app_name.keyword": "Photo Editor"
    }
  }
}

DELETE hol_devoxxfr_12

## GET information index
GET hol_devoxxfr_11/_doc/4

GET hol_devoxxfr_11

# INDEX BANQUE
## get all data
GET bank/_search

GET bank/_search
{
  "query": {
    "match": {
      "firstname": "AMber"
    }
  }
}

## QUERY get data where address contains place or lane
GET bank/_search
{
  "query": {
    "match": {
      "address": "place lane"
    }
  }
}

## QUERY get all data 
GET bank/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "address": "place lane"
          }
        }
      ], 
      "filter": [
        {
          "term": {
            "address": "place"
          }
        }
      ]
    }
  }
}

## MULTIPLE QUERY CRITERIA
GET bank/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "age": "39"
          }
        }
      ],
      "must_not": [
        {
          "match": {
            "gender": "F"
          }
        }
      ]
    }
  }
}

# DATABASE ES_DB
GET /es_db