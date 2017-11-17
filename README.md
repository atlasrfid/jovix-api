Already an expert, or just ready to jump into the details? This link's for you...

<a href="public/index.html" target="_blank"><img src="public/assets/jovix-rest-api-reference-button.png" alt="Jovix REST API Reference"></a>

---

## Getting started using the Jovix REST API

The Jovix REST API is available on any paid instance of Jovix, starting with version 2017.9, and makes it possible to access and modify data within that instance. 

The fastest way to get started with the API is to try it out with our sample Postman Collection:

<a href="https://app.getpostman.com/run-collection/2eec01d5777eda9bccfd" target="_blank"><img src="https://run.pstmn.io/button.svg" alt="Run in Postman"></a>

---

#### Example calls using cURL

Make a request to get a JSON Web Token (JWT) using basic authentication...

```
curl -X GET \
  https://<server_address>/api/v1/token \
  -H 'authorization: Basic Z3JvZGdlcnM6Z3JvZGdlcnM='
```

* Use the Authorization header with 'Basic' and Base64 encoded credentials in the format username:password
* JSON response includes accessToken and refreshToken

Make a request to get materials using the accessToken JWT received from the first call...

```
curl -X GET \
  'https://<server_address>/api/v1/materials?filter=name=^PIPE-17' \
  -H 'authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ'
```

* Use the Authorization header with 'Bearer' and the accessToken returned from the authentication call
