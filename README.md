# RestShaper
- [RestShaper](#restshaper)
  - [Summary](#summary)
    - [So what? That's easy.](#so-what-thats-easy)
    - [How does it work?](#how-does-it-work)
  - [API spec](#api-spec)

## Summary

RestShaper is a service that generates data to test REST APIs based on an OpenApi (AKA Swagger) specification, similar to fuzz testing.

### So what? That's easy.

There are a few big problems with traditional methods of generating test data:

1) *Random data is rarely useful for functional testing.* 
   * The domain of, for example, strings you can generate for a string field is so large compared to the number of valid string, you will never get a valid string. This isn't a problem for fuzz testing since that is often just scanning for security issues or weird invalid cases. 
2)  *It's difficult to know if a test has passed or failed.*
    * With normal random testing, if your API returns a 400, is that OK? It's hard to know. If it's invalid data that is correct, but if you get a 400 with valid data that's a big problem.

RestShaper attempts to salve this by saving and reusing the results of the API calls it has made in the past. This alows RestShpaer to generate known valid and invalid data, and pass random data through multiple API calls chained together. Doing this, RestShaper can generate true API workflow tests, instead of spamming a single api with tons of data that is doomed to fail.

Instead of flat tests on each API indepentently, Rest**Shape**r can test all APIs in a specificication together to understand the **shape** of the REST API.

### How does it work?

WIP - 
#1 from above is essentially complete but #2 needs some work. Will update more once complete, but you can see the OpenAPI spec below for information on how to use it.

## API spec
WIP - will be updated with the correct server when hosted.

To view the OpenAPi spec check out https://petstore.swagger.io/. Paste `https://raw.githubusercontent.com/DocksonWedge/RestShaperDocs/main/OpenApi.yml` into the top field and press explore to view the api.