# Disabling-Theme-Changing-for-other-admin



add_action( 'admin_init', 'slt_lock_theme' );
function slt_lock_theme() {
    global $submenu, $userdata;
    get_currentuserinfo();
    if ( $userdata->ID != 1 ) {
        unset( $submenu['themes.php'][5] );
        unset( $submenu['themes.php'][15] );
    }
}
