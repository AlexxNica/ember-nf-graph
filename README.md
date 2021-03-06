[![Build Status](https://travis-ci.org/Netflix/ember-nf-graph.svg?branch=master)](https://travis-ci.org/Netflix/ember-nf-graph)
[![npm version](https://badge.fury.io/js/ember-nf-graph.svg)](http://badge.fury.io/js/ember-nf-graph)

## NOTICE: This add-on was built to support Ember < 1.12 and cannot support Ember 1.13 and higher

Due to this addon being used in large Ember 1.11 and 1.12 apps in production that have enumerable deprecation warnings on the path to Ember 2, and in light of the fact that some public APIs this addon relied on were removed in 1.13, we are unable to update this add-on to a higher version of Ember at this time.

# ember-nf-graph

A Component-based DSL for creating graphs in your Ember app. The goal of the library is to 
create a set of components that allows application or component authors to build graphs in a
compositional way. This includes components for templated axes, graph lines, areas, stacked areas, bar graphs, and much more. Check the [documentation](//netflix.github.io/ember-nf-graph/docs) for more information.

- [Documentation](//netflix.github.io/ember-nf-graph/docs)
- [Examples](//netflix.github.io/ember-nf-graph-examples/dist)



A basic graph example is as follows:

```js
export default Ember.Route.extend({
  model() {
    return {
      myLineData: [
        { x: 0, y: 12 },
        { x: 1, y: 32 },
        { x: 2, y: 42 },
        // ...
      ],
      myAreaData: [
        { x: 0, y: 43 },
        { x: 1, y: 54 },
        { x: 2, y: 13 },
        // ...
      ]
    };
  }
});
```

```hbs
{{#nf-graph width=500 height=300}}
  {{#nf-graph-content}}
    <!-- add a line -->
    {{nf-line data=model.myLineData}}

    <!-- add an area -->
    {{nf-area data=model.myAreaData}}

    <!-- mix in any SVG element you want -->
    <circle cx="40" cy="40" r="10"></circle>
  {{/nf-graph-content}}

	<!-- axis ticks are templateable as well -->
  {{#nf-y-axis as |tick|}}
    <text>{{tick.value}}</text>
  {{/nf-y-axis}}


  {{#nf-x-axis as |tick|}}
    <text>{{tick.value}}</text>
  {{/nf-x-axis}}
{{/nf-graph}}
```


## Installation

This set of Ember components requires [Ember-CLI](http://ember-cli.com) 0.2.0 or higher and
[Ember](http://emberjs.com) 1.10.0 or higher.

To install, simply run `ember install ember-nf-graph`, or `npm install -D ember-nf-graph` 

## Documentation

- Online at: [netflix.github.io/ember-nf-graph/docs](//netflix.github.io/ember-nf-graph/docs) (generated by [YUIDocs](http://yui.github.io/yuidoc/))
- In package: Documentation for these components is included in the package, and can be found under `node_modules/ember-nf-graph/docs/index.html` just open in any browser.

----

## Contributing

* `git clone` this repository
* `npm install`
* `bower install`

### Running

* `ember server`
* Visit your app at http://localhost:4200.

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build`

For more information on using ember-cli, visit [http://www.ember-cli.com/](http://www.ember-cli.com/).

### Generating Documenation

This project uses YUIDoc to generate documentation. Once YUIDoc is installed run:

```sh
yuidoc -c yuidoc.json 
```

The documentation is located in `docs/`.



