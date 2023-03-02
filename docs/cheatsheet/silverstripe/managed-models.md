# Managed models

## Defining the ModelAdmin models

The `$managed_models` configuration supports additional formats allowing you to customise the URL and tab label used to access a specific model. This can also be used to display the same model more than once with different filtering or display options.

```php
use SilverStripe\Admin\ModelAdmin;

class MyAdmin extends ModelAdmin
{

    private static $managed_models = [
        // This is the most basic format. URL for this Model will use the fully
        // qualified namespace of `Product`. The label for this tab will be determined
        // by the `i18n_plural_name` on the `Product` class.
        Product::class,
    
        // This format can be used to customise the tab title.
        Category::class => [
            'title' => 'All categories'
        ],
    
        // This format can be used to customise the URL segment for this Model. This can
        // be useful if you do not want the fully qualified class name of the Model to
        // appear in the URL. It can also be used to have the same Model appear more than
        // once, allowing you to create custom views. (Only available in SS4.7+)
        'product-category' => [
            'dataClass' => Category::class,
            'title' => 'Product categories'
        ]
    ];

    private static $url_segment = 'products';
    
    private static $menu_title = 'My Product Admin';
    
    public function getList()
    {
        $list =  parent::getList();
        // Only show Categories specific to Products When viewing the product-category tab
        if ($this->modelTab === 'product-category') {
            $list = $list->filter('IsProductCategory', true);
        }
    
        return $list;
    }
}
```
