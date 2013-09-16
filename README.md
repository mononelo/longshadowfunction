Long Shadow Function
====================

Long Shadow Function is a function in PHP to generate long shadows both for typography and boxes.
You can check all the infomation at <a href="http://longshadowfunction.com" target="_blank">longshadowfunction.com</a>


	<?php
	
	// TEXT SHADOW
	
	function text_shadow( $total, $color ){
		$ts = 'text-shadow:';
		$first = true;
		for( $i = 0; $i < $total; $i++ ){
			if( !$first ){
				$ts .= ', ';
			}else{
				$first = false;
			}
			$ts .= $i.'px '.$i.'px 0 #'.$color;
		}
		echo $ts.';';
	}
	
	
	// BOX SHADOW
	
	function box_shadow( $total, $color ){
		$prefix = array( '', '-webkit-', '-moz-', '-o-' );
		$bs = '';
		for( $j = 0; $j < count($prefix); $j++){
			$ts = $prefix[$j].'box-shadow:';
			$first = true;
			for( $i = 0; $i < $total; $i++ ){
				if( !$first ){
					$ts .= ', ';
				}else{
					$first = false;
				}
				$ts .= $i.'px '.$i.'px 0 #'.$color;
			}
			$bs .= $ts.';';
		}
		echo $bs;
	}
	
	?>


Usage:

	<?php // FUNCTION'S DECLARATION
        
	include 'functions.php';
        
	?>
        
	<div style="<?php text_shadow( $length, $color ); ?>">Lorem Ipsum</div>
		
	<div style="<?php box_shadow( $length, $color ); ?>"></div>
