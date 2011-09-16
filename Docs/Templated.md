Class: Templated {#Tempalted}
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


### Methods

### enter

* (*function*) Function to execute when the element's designated area is scrolled into.

### Signature

	onEnter(position, enters, event)
	
#### Arguments:

1. position - (*object*) The container's scroll position object.
2. enters - (*integer*) The number of times the scroll area has been entered.
3. event - (*event*) The Event object from the main scroll event.


### leave

* (*function*) Function to execute when the element's designated area is scrolled out of.

### Signature

	onLeave(position, leaves, event)
	
#### Arguments:

1. position - (*object*) The container's scroll position object.
2. leaves - (*integer*) The number of times the scroll area has been left.
3. event - (*event*) The Event object from the main scroll event.

### scroll

* (*function*) Function to execute on each scroll event.

### Signature

	onTick(position, inside, enters, leaves, event)
	
#### Arguments:

1. position - (*object*) The container's scroll position object.
2. inside - (*boolean*) Represents whether or not the scroll is within the designated min and max area.
3. enters - (*integer*) The number of enters.
4. leaves - (*integer*) The number of leaves.
5. event - (*event*) The Event object from the main scroll event.


### tick

* (*function*) Function to execute on each scroll event when the scroll position is between the enter and exit.

### Signature

	onTick(position, inside, enters, leaves, event)
	
#### Arguments:

1. position - (*object*) The container's scroll position object.
2. inside - (*boolean*) Represents whether or not the scroll is within the designated min and max area.
3. enters - (*integer*) The number of enters.
4. leaves - (*integer*) The number of leaves.
5. event - (*event*) The Event object from the main scroll event.