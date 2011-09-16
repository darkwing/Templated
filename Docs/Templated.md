Class: Templated {#Templated}
=============================

### Notes:

- *Templated* debuted Monday, September 19, 2011 on the David Walsh Blog:  [http://davidwalsh.name/templated](http://davidwalsh.name/templated)
- *Templated* requires MooTools Core only -- no MooTools More dependencies.
- Visit [http://davidwalsh.name/templated](http://davidwalsh.name/templated) for example usages.
- *Templated* is meant as a Mixin, not a standalone class

### Options:

* template - (*string*, defaults to "<div></div>")  The HTML template for the widget, including attach points and attach events
* templateUrl:  (*string*, defaults to "")  The URL to the widget's template if it's external.  A basic Request will be sent to retrieve the widget if not yet cached.
* element:  (*node*)  The element which the widget's domNode will replace.
* widgetsInTemplate (*boolean*, defaults to true)  If true, parses the widget template to find and create subwidgets.  Inline attach points and attach events are added to the parent widget, not the subwidget.
* propertyMappings (*object*, defaults to null)  An object which contains custom property mappings for the widget.
* defaultPropertyMappings (*object*, defaults to null)  An object with default, fallback property mappings for the widget.  Property mappings included ID, style, and class, which these properties are carried over from the base element to the domNode.

### Progress Stub Methods:

* postMixInProperties: Fires after the options and widget properties have been mixed.
* postCreate: Fires after the widget nodes have been create but before the nodes are placed into the DOM
* startup:  Fires after the widget has been created and is placed into the DOM