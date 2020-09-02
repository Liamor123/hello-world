# hello-world

My first repository

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

const response =pm.response.json();

pm.test("Board should be created", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.name).to.eql("TODO Liam My new board4");
    pm.expect(jsonData.closed).to.eql(false);
    pm.expect(jsonData.idOrganization).to.eql(null);
});

pm.test("Board should be private", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.prefs.permissionLevel).to.eql("private");

});
