Description
===========

Server Side Google Analytics (SSGA) is a simple PHP 5 class, which allows to track server-side events and data within Google Analytics.

Drop-in solution for WordPress plugins (uses the WP HTTP API if available).

Usage
-----

Google Analytics Server Side can be used simply in the following manner:


Easy:

	ssga_track( 'UA-YOUR_NUMBER', 'yoursite.com', '/page.php' )

Advanced:
	
	//create new ssga object
	include 'lib/ssga.class.php';
	$ssga = new ssga( 'UA-YOUR_NUMBER', 'yoursite.com' );

	//Set a pageview
	$ssga->set_page( '/page.php' );
	$ssga->set_page_title( 'Page Title' );

	// Send
	$ssga->send();
	$ssga->reset();

Set an event (based on http://code.google.com/apis/analytics/docs/tracking/eventTrackerGuide.html) 
	
	//$ssga as created above
	$ssga->set_event( 'Feed', 'Categories', $var, $var );
	$ssga->send();
