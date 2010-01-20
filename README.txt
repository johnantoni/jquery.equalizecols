Michael Futreal has written a very similar plugin called vjustify (btw, vjustify is a much cooler name than equalizeCols). He has identified an issue where columns containing images without specified dimensions can cause the height calculations to be incorrect if the plugin is invoked before the images have loaded. Refer to his page for additional information.

Example:

var $els = $("#col1, #col2, #col3").equalizeCols();
	
// requires jquery.onfontresize.js
$(document).bind("fontresize", function () {
	$els.equalizeCols();
});

If any of the columns contain dynamically updated content, you'll want to call $(elems).equalizeCols() anytime that you show/hide/update content in one of the columns.

UPDATE: the example code above demonstrates using my jquery.onfontresize.js plugin to re-equalize the element heights when the user resizes her browser font.

$(document).ready(function() {
    $.jqem.init();
    $.jqem.bind( function() {
        $(elems).equalizeCols();
    });

});
