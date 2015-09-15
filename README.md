KnockoutJS external template async loading using jQuery

The code is mainly based on https://github.com/rniemeyer/knockout-amd-helpers/blob/master/src/amdTemplateEngine.js. Main changes here:

1. Using `jQuery`  to load external template files instead of `RequireJS`
2. Can be used with `normal script tag` or `RequireJS`

## Configuration

```javascript
    ko.externalTemplateEngine.defaultPath = "templates";
    ko.externalTemplateEngine.defaultSuffix = ".tmpl.html";
```

## Example
For example, when using a binding like:

```javascript
    <ul data-bind="template: { name: 'itemView', foreach: items }"></ul>
```

If there is no script tag with an id of itemView, it will attempt to load the template. The engine uses a default path of templates and a default suffix of .tmpl.html. So, it would look for the template at templates/itemView.tmpl.html. The default path and suffix can be configured through the attributes of
`ko.externalTemplateEngine`.