# responsiveTruncator

Simple jQuery plugin to truncate content (more/less toggle links) in a responsive way.

## Initializing the plugin

```javascript
$(document).ready(function(){
  $("[data-truncate]").responsiveTruncate();
});
```

## Notes

This will take the html of the elements in the provided selector and wrap it with a div that allows us to truncate the content by height.
When removing the truncation the div and the more/less toggle links are removed from the DOM as well.

The plugin updates on page resize so that the toggle element and links will be removed if the element no longer requires truncation (or added if it now does).  This can cause a lot of DOM manipulation since we are not using timeouts to only take action when the page finishes resizing.  This can be added later, but it seems performant as is in some cursory tests.

## Options

This plugin will take the following options:

* lines (the number of lines to show before truncation [Default: 3])
* more (the text for the more link [Default: more])
* less (the text for the less link [Default: less])

```javascript
$(document).ready(function(){
  $("[data-truncate]").responsiveTruncate({lines: 5, more: 'más', less: 'menos'});
});
```