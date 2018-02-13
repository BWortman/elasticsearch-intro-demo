## Initialization

Check for index `articles`:

``` curl
curl -XGET 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles?pretty'
```

Response:

![check for index](./images/es1.png)

Create index `articles`, with single type mapping (per version 6.0):

``` curl
curl -XPUT 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles?pretty' -H 'Content-Type: application/json' -d'
{
    "mappings" : {
        "article" : {
            "properties" : {
                "pagepath" : { "type" : "text" },
                "pagetext" : { "type" : "text" }
            }
        }
    }
}
'
```

Response:

![create index](./images/es2.png)

Use a different verb to check for index `articles`, this time verifying that it does exist:

``` curl
curl -HEAD 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles?pretty'
```

Response:

![check for index](./images/es3.png)

We can even verify that the `article` type, which was mapped to the `articles` index, exists:

``` curl
curl -HEAD 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles/_mapping/article?pretty'
```

Response:

![check for type](./images/es4.png)

Next, let's add, update, and fetch some data...
