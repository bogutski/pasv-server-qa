# PASV server QA

## `Sergei Latyshev` TESTS

### Pre-request tests in "Register:

```javascript
pm.environment.set("userEmail", "latyshev_" + new Date().getTime() + "@test.ok");
pm.environment.set("userPassword", "12345");
pm.environment.set("userPhone", "+" + Math.floor(Math.random() * 100000000000));
```

### Univesal tests:

```javascript
pm.test("Status code is correct", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is less than 5000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(5000);
});

pm.test("Message is Success", () => {
    pm.expect(pm.response.json().message.type).to.equal("success");
});
```

### Create vaeiables (login request):

```javascript
pm.environment.set("token", pm.response.json().token);
pm.environment.set("userId", pm.response.json().user._id);
```

### Create vaeiables (get hash):

```javascript
pm.environment.set("hash", pm.response.json().hash);
```

### Test in "Get hash":

```javascript
pm.test("Hash is presetned", function () {
    pm.expect(pm.response.text()).to.include("hash");
});
```

### 
