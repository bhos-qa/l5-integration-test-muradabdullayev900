## Learning Outputs
Integration Testing is defined as a type of testing where software modules are integrated logically and tested as a group. A typical software project consists of multiple software modules, coded by different programmers. The purpose of this level of testing is to expose defects in the interaction between these software modules when they are integrated

## Implementation
Code snippet below shows output which is requested with http get request module is compared with expected output
```
    TestRestTemplate restTemplate = new TestRestTemplate();
    HttpHeaders headers = new HttpHeaders();

    public void integrationTest(String url, String expected) throws JSONException {
        HttpEntity<String> entity = new HttpEntity<>(null, headers);
        ResponseEntity<String> response = restTemplate.exchange(url, HttpMethod.GET, entity, String.class);
        JSONAssert.assertEquals(expected, response.getBody(), false);
    }
```

## SETUP
First you need to give execute permission to gradlew
```
chmod +x gradlew
```
Then you should build the project
```
./gradlew build
```
Finally you can run the test
```
./gradlew test
```