# Click the Variables button, above, to create your own variables.
GET ${exampleVariable1} // _search
{
  "query": {
    "${exampleVariable2}": {} // match_all
  }
}

GET hol_devoxxfr_11/_search
{
  "query": {
    "match": {
      "app_name.keyword": "Photo Editor"
    }
  }
}

DELETE hol_devoxxfr_12

# GET information index
GET hol_devoxxfr_11/_doc/4

GET hol_devoxxfr_11

# INDEX BANQUE
# get all data
GET bank/_search

# WITH MATCH WE CAN GET DATA THAT ADDRESS CONTAINS "282" OR "Kings" OR "Place"
GET bank/_search
{
  "query": {
    "match": {
      "address": "282 Kings Place"
    }
  }
}

# QUERY get data THAT address exactly contains "282 Kings Place"
GET bank/_search
{
  "query": {
    "match_phrase": {
      "address": "282 Kings Plac"
    }
  }
}

# QUERY get all data 
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

# MULTIPLE QUERY CRITERIA
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

# GET QUERY MULTI MATCH => GET DATA THAT FIRSTNAME OR LASTNAME CONTAINS DUKE
GET bank/_search
{
  "query": {
    "multi_match": {
      "query": "Duke",
      "fields": ["firstname", "lastname"]
    }
  }
}

# DATABASE ES_DB
GET /es_db





