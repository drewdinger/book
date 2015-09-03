# Analysis

{% import './data.html' as data %}

After completing the warmup exercises, your task is to do four more slightly
more challenges analyses.

## How many students like sushi as their favorite food?

{% lodash %}
return _.size(_.filter(data.comments, function(n){
	return _.includes(n.body,"Sushi");
}))
{% endlodash %}

The answer is {{result}}.

## Who are the students liking Python the most?

{% lodash %}
var x = _.filter(data.comments, function(n){
	return _.includes(n.body,"Python");
})
var y = _.pluck(x, "body")
var z = _.map(y, function(name){
	var a = name.split("\r\n") [0]
	return _.last(a.split("Name:"))
});
return z
{% endlodash %}

Their names are {{result}}.

## Are there more Javascript lovers or Java lovers?

{% lodash %}
var x = _.size(_.filter(data.comments, function(n){
	return _.includes(n.body,"Java");
}))
var y = _.size(_.filter(data.comments, function(n){
	return _.includes(n.body,"Javascript");
}))
if (x > y)
	return 'Java'
else
	return 'Javascript'
{% endlodash %}

The answer is {{result}}.

## Who like the same food as `kjblakemore`?

{% lodash %}
var x = _.filter(data.comments, function(n){
	return _.includes(n.body,"Vegan");
})
var y = _.pluck(x, "body")
var z = _.map(y, function(name){
	var a = name.split("\r\n") [0]
	return _.last(a.split("Name:"))
});
return z
{% endlodash %}

Their names are {{result}}.
