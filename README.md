<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.2/angular.min.js"></script>
<body>

<div ng-app="myApp" ng-controller="customersCtrl"> 

<table>
  <tr ng-repeat="x in names">
    <td>{{ x.userId }}</td>
    <td>{{ x.id }}</td>
    <td>{{ x.title }}</td>
    <td>{{ x.body }}</td>
  </tr>
</table>

</div>

<script>
var app = angular.module('myApp', []);
app.controller('customersCtrl', function($scope, $http) {
    $http.get("http://jsonplaceholder.typicode.com/posts")
    .then(function (response) {$scope.names = response.data.records;});
});
</script>

</body>
</html>
