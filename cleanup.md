## Clean Up

Remove the index:

``` curl
curl -XDELETE 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles?pretty'
```

Response:

![remove index](./images/es44.png)

Verify removal of index:

``` curl
curl -HEAD 'https://MyPrivateSecurityInfo.us-east-1.bonsaisearch.net/articles?pretty'
```

Response:

![remove index](./images/es45.png)
