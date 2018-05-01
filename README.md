# n26-api
Unofficial N26 API documentation

It is a collection of observed API calls and methods. No guarantees are provided that they are complete, correct or that they are still functioning as specified.

The OpenAPI specification is provided in the `openapi.yml` file.
For testing the spec, it is also published at https://app.swaggerhub.com/apis/Rots/N26


# Client wrapper generation

The OpenAPI specification allows for generating client wrappers to access the data.

Example:

```
docker run --rm -v ${PWD}:/local korchasa/swagger-codegen-openapi generate -i /local/openapi.yml -l java -o /local/out/java
```

# Security warning!

Do not type in your bank credentials to an untrusted software!
Once you have given full access to a third party, they can indefinitely "keep the bank API session alive" by refreshing their access token and make transactions on your behalf (and change any details on the banking app).
N26 haven't enabled a way to revoke access of third party apps (as far as I know, you can't securely sign in to the bank without giving your password in plain text to the third party).

If you think that your credentials may have been compromised, immidiately change your login password in the official N26 app and notify the bank of any relevant information.

# Other known software for N26

* https://github.com/guitmz/n26 Go API
* https://github.com/PierrickP/n26 JSON API

