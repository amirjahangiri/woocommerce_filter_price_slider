# woocommerce_filter_price_slider
fixed slider price filter to woocommerce


Rename these files:
wp-content/plugins/woocommerce/assets/js/jquery-cookie/jquery.cookie.js
wp-content/plugins/woocommerce/assets/js/jquery-cookie/jquery.cookie.min.js

to:

wp-content/plugins/woocommerce/assets/js/jquery-cookie/jquery_cookie.js
wp-content/plugins/woocommerce/assets/js/jquery-cookie/jquery_cookie.min.js

--------------------------------------------------
And add the following to your theme’s functions.php file:

add_action( 'wp_enqueue_scripts', 'custom_frontend_scripts' );function custom_frontend_scripts() {global $post, $woocommerce;

$suffix = defined( 'SCRIPT_DEBUG' ) && SCRIPT_DEBUG ? : '.min';
wp_deregister_script( 'jquery-cookie' );
wp_register_script( 'jquery-cookie', $woocommerce->plugin_url() . '/assets/js/jquery-cookie/jquery_cookie' . $suffix . '.js', array( 'jquery' ), '1.3.1', true );
}
