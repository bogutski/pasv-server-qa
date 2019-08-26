pm.test("User name is correct", () => {pm.expect(jsonData.user.name).to.match(/^[A-Z][a-z]{1,15}\s[A-Z][a-z]{1,15}$/);
   });
   
pm.test("Phone number is correct", () => {pm.expect(jsonData.user.phone).to.match(/^\+[0-9]{11,12}$/);
});

pm.test("Email is correct", () => {pm.expect(jsonData.user.email).to.match(/[a-z0-9!#$%&‘*+/=?^_{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?/);
});

pm.test("The length of UserId is 24", () => {pm.expect(jsonData.userId.length).to.equal(24);
});
pm.test("Returns 24 char alphanumeric id", () => {pm.expect(jsonData.userId).to.match(/^[a-f0-9A-F]{24}$/);
    
}); 
pm.test("response should be okay to process", function () {
pm.response.to.not.be.error;
pm.response.to.not.have.jsonBody("error");

});
pm.test("Roles is admin", () => {pm.expect(jsonData.user.roles[0]).to.equal("admin");
});
pm.test("The acl length larger than 1", () => {pm.expect(jsonData.acl).to.have.lengthOf.at.least(2);
});