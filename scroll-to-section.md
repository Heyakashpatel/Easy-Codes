```js
jQuery(document).ready(function($) {
    // Get all anchor links
    $("a[href^='#']").on('click', function(e) {     
e.preventDefault();  
        var targetId = $(this).attr('href').substring(1);
        var targetElement = $('#' + targetId);			
        if (targetElement.length) {	
			const targetPosition = targetElement.offset().top; //- 250;
            $('html, body').animate({
                scrollTop: targetPosition
            }, 500);
        }
		
    });
