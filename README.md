# Recommend your WordPress ORG profile plugins like WordPress plugin installation method.

Please refer to the screenshots below

![image](https://github.com/user-attachments/assets/477e6af1-7dc0-41fd-91e7-9660932762d9)

The screenshot belongs to "WP News and Scrolling Widgets" whose author is "WP OnlineSupport" (wponlinesupport). I have created a code so you can utilize it in your plugin and recommend users to view your other WordPress Org plugins.

Please follow below steps,
01) Download this repository and add the folder in your plugin.
02) After adding this folder you need to load the files, Kindly add below code at bottom in your plugin main file. Make sure `wpos-recommendation.php` file path is correct.

```
/* Recommended Plugins Starts */
if ( is_admin() ) {

	if( ! defined( 'WPOS_ESPBW_USERNAME' ) ) {
		define( 'WPOS_ESPBW_USERNAME', 'wponlinesupport' ); // Plugin Username
	}

	require_once( WPNW_DIR . '/wp-plugins/wpos-recommendation.php' );

	wpos_espbw_init_module( array(
							'prefix'	=> 'wpnw',
							'menu'		=> 'edit.php?post_type='.WPNW_POST_TYPE,
							'position'	=> 5,
						));
}
/* Recommended Plugins Ends */
```

You can add different menu string the same as WordPress allow on `add_submenu_page`

That's It. Enjoy the recommended plugin section and let the user find out your other plugins.
