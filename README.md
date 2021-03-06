#WordPress Ajax Load More

Ajax Load More is a simple yet powerful solution for lazy loading/infinite scrolling WordPress posts and pages with Ajax.

Build complex WordPress queries using our easy to use shortcode builder then add the shortcode to your pages via the content editor or directly into your template files.

Get more information and view live examples at http://connekthq.com/plugins/ajax-load-more/



##Moved to WordPress.org
Ajax Load More has been updated to v2.0.0 and is now available as an installed plugin on [wordpress.org](https://wordpress.org/plugins/ajax-load-more/). 
Please download the latest stable version from your WordPress plugins dashboard by searching for Ajax Load More or visiting https://wordpress.org/plugins/ajax-load-more/.

*   This repository is now used as a development branch. 
*   Access v1.0 at https://github.com/dcooney/wordpress-ajax-load-more/tree/v1



##Shortcode Parameters

Ajax Load More accepts a number of parameters that are passed to the WordPress query. These parameters are transferred via shortcode - don't worry, creating your shortcode is simple with our intuitive Shortcode Builder.
 
*   **repeater** - Choose a repeater template (Add-on available). Default = ‘default‘
*   **post_type** - Comma separated list of post types. Default = ‘post’
*   **post_format** - Query by post format. Default = null
*   **category** - Query by category slug. Default = null
*   **tag** - Query by tag name. Default = null
*   **taxonomy** - Query by custom taxonomy name. Default = null
*   **taxonomy_terms** - Comma separated list of custom taxonomy terms(slug). Default = null
*   **taxonomy_operator** - Operator to compare Taxonomy Terms against (IN/NOT IN). Default = ‘IN’
*   **meta_key** - Custom field key(name). Default = null
*   **meta_value** - Custom field value. Default = null
*   **meta_compare** - Operator to compare meta_key and meta_value against (=/!=/>/>=/</<= etc.). Default = ‘=’
*   **author** - Query by author id. Default = null
*   **search** - Query search term (‘s’). Default = null
*   **order** - Display posts in ASC(ascending) or DESC(descending) order. Default = ‘DESC’
*   **orderby** - Order posts by date, title, name, menu order, random, author, post ID or comment count.  Default = ‘date’
*   **exclude** - Comma separated list of post ID’s to exclude from query. Default = null 
*   **offset** - Offset the initial query (number). Default = ’0′
*   **posts_per_page** - Number of posts to load with each Ajax request. Default = ’5′
*   **scroll** - Load more posts as the user scrolls the page (true/false). Default = ‘true’
*   **max_pages** - Maximum number of pages to load while user is scrolling (activated on when scroll = true). Default = '5' 
*   **pause** - Do not load posts until user clicks the Load More button (true/false). Default = 'false'
*   **transition** - Choose a posts reveal transition (slide/fade). Default = 'slide' 
*   **button_label** - The label text for Load More button. Default = 'Older Posts'
*   **seo** - Enable address bar URL rewrites as users page through content - <a href="seo/">add-on only</a> (true/false). Default = ‘false’


## Example Shortcode

    [ajax_load_more post_type="post, portfolio" repeater="default" posts_per_page="5" transition="fade" button_label="Older Posts"]
    
## Demos

* **[Default](http://connekthq.com/plugins/ajax-load-more/)** - Out of the box functionality and styling
* **[Fade Transition](http://connekthq.com/plugins/ajax-load-more/examples/fade-transition/)** - Elements fade in as posts are loaded
* **[Mansory](http://connekthq.com/plugins/ajax-load-more/examples/masonry/)** - Creating a flexible grid layout with Masonry JS
* **[Multiple Instances](http://connekthq.com/plugins/ajax-load-more/examples/multiple-instances/)** - Include multiple Ajax Load More' on a single page
* **[Pause Loading](http://connekthq.com/plugins/ajax-load-more/examples/pause-loading/)** - Posts will not load until initiated by the user
* **[Search Results](http://connekthq.com/plugins/ajax-load-more/examples/search-results/)** - Returning results based on search terms
* **[SEO Paging](http://connekthq.com/plugins/ajax-load-more/examples/seo-paging/)** - Generate unique paging URLs with each Ajax Load More query

*The [Custom Repeater Add-On](http://connekthq.com/plugins/ajax-load-more/custom-repeaters/) has been installed for use on each of our product demos*


##Callback Functions
The following functions are avaialble to be dispatched by Ajax Load More. 


####Ajax Complete

The almComplete() function is triggered after every *successful* ajax call made by Ajax Load More.
To utilize the almComplete() function simply place the following code inside your sites javascript file.

    $.fn.almComplete = function(alm){
    	// Your on complete code goes here
    }



##Add-ons

The following Add-ons are available to increase the functionality of Ajax Load More.


####Custom Repeaters

The **[Custom Repeaters](http://connekthq.com/plugins/ajax-load-more/custom-repeaters)** add-on will allow for **unlimited repeater templates** and provide the ability to create unique templates for different content types throughout your theme.
[Get More Information](http://connekthq.com/plugins/ajax-load-more/custom-repeaters)

####Search Engine Optimization

The **[SEO](http://connekthq.com/plugins/ajax-load-more/seo/)** add-on will optimize your ajax loaded content for search engines and site visitors by generating standard WordPress paging URLs with each Ajax Load More query.
[Get More Information](http://connekthq.com/plugins/ajax-load-more/seo/)



##Changelog

= 2.3.1 =
* Urgent fix for array_push error


= 2.3.0 =
* Adding required functionality for ALM SEO add-on (http://connekthq.com/plugins/ajax-load-more/seo/)
* Adding variables for counting items within the ALM query - $alm_page & $alm_item are now accessible within repeater templates.
* Remove plugin activation notification due to error fetching column names.
* Fixed issue with orderby = "rand", ALM now excludes all previously queried post ids.
* fixed JS error on ALM setting pages.
* Fixed issue with hiding TinyMCE button that was affecting other plugins.
* General plugin improvements and enhancements.

= 2.2.8 =
* Adding required functionality for the NEW Ajax Load More Custom Repeaters v2 add-on - http://connekthq.com/plugins/ajax-load-more/custom-repeaters/
* Improved debug messaging for Ajax Load More and Add-Ons.
* Adding fix for ordering by meta value.
* Admin stying updates.
* Updated FAQs
* Fix meta_query query and orderby meta value 

= 2.2.7 =
* Fix for query by Standard post format.
* Fix for Shortcode Builder where Custom Taxonomies were not building correctly.

= 2.2.6 =
* Bug fix for meta_query parameters.
* Further improvements to WordPress query arguments from 2.2.4.
* Update plugin .pot file.

= 2.2.5 =
* Urgent fix for category queries.

= 2.2.4 =
* Improving WordPress query arguments.
* Removing empty query parameters which were conflicting with various hooks and filters reported by ALM users.
* Updated admin notifications.
* Added plugin action links to plugin listing.

= 2.2.3 =
* Adding query by Custom Field value(Meta Query). 
* Improved error handling for easier debugging.
* Fixed issue with pause = "true" and scroll = "true". Pause should always take precendence over scroll. 
* Code clean up, improving overall quality for easier merges and updates.

= 2.2.2 =
* Adding callback function that is dispatched once a successful ajax call is made. $.fn.almComplete(alm). 
* Adding WPML support for ICL_LANGUAGE_CODE - A 'lang' atributed is added dynamically if WPML is installed.
* Making JS variables and functions publically accessible.

= 2.2.1 =
* Fixed php notice/warning that would trigger if WP_DEBUG was enabled. 
* Adding minified core JS.
* Adding global option to disable shortcode button in the content editor.
* Adding touchmove js event for faster scroll detection on mobile devices.
* Code clean up, removing unused functions.

= 2.2.0 =
* Adding Post Format query.
* Adding syntax highlighting for Repeater Templates with CodeMirror (http://codemirror.net/).
* Adding custom alias integration for Repeater Templates (Only for the custom repeater add-on).
* Adding button preview on settings page.
* Adding 'White' button style
* Updated .pot language file

= 2.1.3 =
* Fixed issue causing the Ajax Load More menu to not show on some admin screen do to location conflict with another plugin.
* Adding column 'alias' to wp_alm table to allow for repeater alias (Only for the custom repeater add-on). 
* Remove legacy column 'test' from wp_alm table.  
* Updating styles in admin.css. 

= 2.1.2 =
* Adding ability to have multiple instances of script on a single page
* Adding global class name('.ajax-load-more-wrap') to Ajax Load More container. I plan to remove the #ajax-load-more naming convention in upcoming releases, but need time for users to update their code.
* Small styling enhancements to admin panel.
* Updated .pot language file.

= 2.1.1 =
* Adding Order and Orderby query parameters, you can now set these values within the Shortcode Builder
* Updating core javascript code
* Fixed bug with taxonomy query selectors

= 2.1.0 =
* Adding custom taxonomy query - select from a list of custom taxonomies then select terms and operator
* Fixed path to repeater file in admin functions

= 2.0.15 =
* Fixed issue with loading of admin javascript and css on pages other than Ajax Load More

= 2.0.14 =
* Fixed issue with author query

= 2.0.13 =
* Fixed issue where loading button was not turning off when posts remaining were zero 

= 2.0.12 =
* Adding add_filter('widget_text', 'do_shortcode'); 

= 2.0.11 =
* Removed 2 filters for widget_text which were casuing issues in sidebars

= 2.0.10 =
* Updating default repeater template to include the_permalink()

= 2.0.9 =
* Fixing issue with duplicate column names in database.

= 2.0.8 =
* removed upgrader_process_complete as it was unreliable. Replaced with admin_init to check whether plugin has been updated.

= 2.0.7 =
* Fixed jQuery conflict javascript error

= 2.0.6 =
* Fixing issue with scrolling of posts

= 2.0.5 =
* Updating db table structure
* Adding upgrader_process_complete checker

= 2.0.4 =
* Adding plugin version to wpdb table.
* Removed legacy repeater code.

= 2.0.3 =
* Fixed issue with WP auto updates overriding the default repeater. Please deactivate and then activate your plugin.

= 2.0.2 =
* Fixed issue with tinymce conflict

= 2.0.1 =
* Ajax Load More
