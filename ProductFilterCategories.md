
## Product Filter - Categories

This section of the tutorial focuses more on styling the [Product Filter - Categories](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/product-filter-categories/). 

We will be exploring how to change the look and feel of the Product Filter - Categories.

> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

> 

Once the widget or shortcode of **Product Filter - Categories** is placed on your site, you should have the following HTML structure:

``` html
<div id="product-search-filter-category-0" class="product-search-filter-terms ">
    <div class="product-search-filter-terms-heading product-search-filter-category-heading" id="product-search-filter-category-heading-0">Category</div>
    <ul>
        <li> <a href=""> </a> </li>
        <li> <a href=""> </a> </li>
        <li> <a href=""> </a> </li>
        ...
    </ul>
</div>
```
Notes:
> The ID ( `product-search-filter-category-0`) is likely to be different on you setup. Hence, please inspect the element using your browser inspector to identify the ID. Tt is also very likely for you to have an ID like `product-search-filter-category-1`.


### Customizing Product Filter - Categories
Here's a list of the top three customization request we have received so far with respect to customizations for Product Filter - Categories
* [ ] Display only child categories
* [ ] Change font color of child categories
* [ ] Make category items look like buttons


### Display only child categories
This is one of our most popular inquiries. If you would love to hide the parent categories and have only the child categories displayed. Please add the CSS snippet below.

_Before_

![Product Filter - categories Example 1](/pfc-before.png)

_After_

![Product Filter - categories Example 1](/pfc-after.png)

*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 .cat-parent{
	    visibility: hidden;
    }
    #product-search-filter-category-0 .cat-parent .children {
        visibility: initial;
    }
    ```

### Change font color of child categories
In this example we'll be changing the color of child categories to red. 

_Preview of final results_

![Product Filter - categories Example 2](/pfc-color.png)


*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 .cat-parent .children a {
	    color: red;
    }
    ```


### Make category items look like buttons
In this example we'll change the list item feel to that of a basic button. The extent to which this can be customized is totally depends on your needs. As you can go further by adding **border-radius**, **color**, **font-size** ... 

_Preview of final results_

![Product Filter - categories Example 2](/pfc-btns.png)


*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 li a {
        border: solid 1px #000;
        padding: 5px 15px;
    }
    #product-search-filter-category-0 li {
        line-height: 2.5;
    }
    ```

### How to apply CSS with WPS inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website.

Inorder to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided