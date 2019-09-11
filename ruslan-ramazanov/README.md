### Ruslan Ramazanov
##### Description of Postman test scripts

*/ This is test check that header is present/*
```javascript
pm.test("Server header is present", function () {
    pm.response.to.have.header("Server");
});
```

*/ This is test check that name contains in response body/*
```javascript
pm.test("Response contains name", function () {
    pm.expect(pm.response.text()).to.include("name");
});
```

*/ This is test check that phone number's length*/
```javascript
pm.test("Phone number is correct", () => {
    pm.expect(jsonData.user.phone).to.match(/[0-9]{11,12}$/);
});
```

*/ This is test check that ID contains numbers and letters*/
```javascript
pm.test("UserID is per requirements", function(){
    pm.expect(jsonData.userId).to.match(/[a-fA-F0-9]/);
});
```

*/This is test check that response has JSON type*/
```javascript
pm.test("Content-Type header value is application/json", function () {
       pm.response.to.be.header("Content-Type", "application/json; charset=utf-8");
});
```

```javascript
pm.test("Response id success", () => {
    pm.expect(jsonData.success).to.be.true;
});
```
