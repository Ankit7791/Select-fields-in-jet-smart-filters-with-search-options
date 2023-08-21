# Select-fields-in-jet-smart-filters-with-search-options

To add Select2 search functionality to the select option field within your JetEngine listing grid, follow these steps:

Step 1: Enqueue Select2 JavaScript and CSS

In your WordPress theme's functions.php file or a custom plugin, enqueue the Select2 JavaScript and CSS files. You can use the following code as a starting point:

    function enqueue_select2_scripts() {
        // Enqueue Select2 CSS
        wp_enqueue_style('select2-css', 'https://cdnjs.cloudflare.com/ajax/libs/select2/4.0.13/css/select2.min.css');
    
        // Enqueue Select2 JavaScript
        wp_enqueue_script('select2', 'https://cdnjs.cloudflare.com/ajax/libs/select2/4.0.13/js/select2.min.js', array('jquery'), '', true);
    }
    add_action('wp_enqueue_scripts', 'enqueue_select2_scripts');


Step 2: Initialize Select2

Create a JavaScript file (e.g., select2-init.js) and place it in your theme's JS directory. In this file, initialize Select2 for your select option field. Here's an example:
You can also use custom css and js plugin : https://wordpress.org/plugins/custom-css-js/

    jQuery(document).ready(function($) {
        // Replace 'select.jet-select__control' with the actual selector for your select option field.
        $('select.jet-select__control').select2({
            placeholder: 'Search...',
            width: '100%',
            minimumInputLength: 2, // Customize this value as needed
        });
    });

Replace 'select.jet-select__control' with the actual selector for your select option field.
