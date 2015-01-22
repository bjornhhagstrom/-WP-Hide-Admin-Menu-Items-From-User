# -WP-Hide-Admin-Menu-Items-From-User

* Add to theme's functions.php
* Function will hide menu items in the Wordpress admin from users in specific role ('editor' used below)

<pre><code>
// hide menu items from users
add_action( 'admin_init', 'my_remove_menu_pages' );
function my_remove_menu_pages() {
 
    global $user_ID;
 
    if ( current_user_can( 'editor' ) ) {
      remove_menu_page( 'index.php' ); // Dashboard
      //remove_menu_page('edit.php'); // Posts
      remove_menu_page('update-core.php'); // Updates
    	remove_menu_page('upload.php'); // Media
      remove_menu_page('link-manager.php'); // Links
      remove_menu_page('edit-comments.php'); // Comments
      //remove_menu_page('edit.php?post_type=page'); // Pages
      remove_menu_page('edit.php?post_type=products'); // Products
      remove_menu_page( 'wpcf7' ); // Contact
      remove_menu_page('edit.php?post_type=acf'); // Advanced Custom Fields
      remove_menu_page('plugins.php'); // Plugins
      remove_menu_page('themes.php'); // Appearance
      remove_menu_page('users.php'); // Users
      remove_menu_page('tools.php'); // Tools
      remove_menu_page('options-general.php'); // Settings
      
      // remove toolbar
      show_admin_bar(false);
    }
}
</code></pre>
