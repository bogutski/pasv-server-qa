### Ruslan Ramazanov

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
pm.test("Phone length to be 12 symbols", function(){
    pm.expect(jsonData.user.phone).to.have.lengthOf(12);
});
```

*/ This is test check that ID contains numbers and letters*/
```javascript
pm.test("UserID is per requirements", function(){
    pm.expect(jsonData.userId).to.match(/[a-fA-F0-9]/);
});
```