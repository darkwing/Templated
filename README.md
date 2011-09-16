Templated
=========

Templated is a MooTools mixin class which creates elements for classes using a string-based HTML template which may included embedded attach points and events.  Using Templated allows developers to provide the UI component structure to the class, taking the presentation structure out of the Class creator's class and placing it into the end developer's.


How to Use
=========

Templated should be provided in the Implements array for the given class:

	#JS
	var UIWidget = new Class({
		
		Implements: [Options, Templated]
		
		// more....
		
	});
	
With Templated implemented, provide the HTML string template for the widget, including attach points, attach events, and props:

	#JS
	var UIWidget = new Class({
		
		Implements: [Options, Templated]
		
		// The UI template with attachpoints and attachevents
		options: {
			template: "<div class='UIWidget'>" + 
						"<p>{message}</p>" +
						"<input type='text' data-widget-attach-point='inputNode' data-widget-attach-event='keyup:onKeyUp,focus:onFocus' />" + 
						"<div type='submit' data-widget-type='UIWidgetButton' data-widget-attach-point='buttonWidget,submitWidget' data-widget-attach-event='click:onSubmit' data-widget-props='label:\"My Prop Label\",somethingElse:true'></div>" + 
					  "</div>",
			uiwidgetOption: "here!"
		},
		
		// more...
		
	});
	
Attach points add element references to the class instance.  Attach events provide shorthand methods to map events to methods on the class instance.  Subwidgets may be embedded via the data-widget-type attribute.  If subwidgets are included, properties for the widget may be attached to the data-widget-props attribute.

When the template should be parsed (usually after options have been merged via setOptions), call the this.parse() method:

	#JS
	var UIWidget = new Class({
	
		Implements: [Options, Templated]
	
		// The UI template with attachpoints and attachevents
		options: {
			template: "<div class='UIWidget'>" + 
						"<p>{message}</p>" +
						"<input type='text' data-widget-attach-point='inputNode' data-widget-attach-event='keyup:onKeyUp,focus:onFocus' />" + 
						"<div type='submit' data-widget-type='UIWidgetButton' data-widget-attach-point='buttonWidget,submitWidget' data-widget-attach-event='click:onSubmit' data-widget-props='label:\"My Prop Label\",somethingElse:true'></div>" + 
					  "</div>",
			uiwidgetOption: "here!"
		},
	
		// Constructor
		initialize: function(options) {
			this.setOptions(options);
		
			// Parse the template, create nodes, find attach points and events
			this.parse();
		}
	
	});

Once the template is parsed, attach points are available on the instance's object!


Helpful Methods
=========

Templated provides stub methods along the way so code can be executed at different points within the creation of the widget:

* postMixInProperties: Fires after the options and widget properties have been mixed.
* postCreate: Fires after the widget nodes have been create but before the nodes are placed into the DOM
* startup:  Fires after the widget has been created and is placed into the DOM

These methods have proven to be useful within the Dojo Toolkit.