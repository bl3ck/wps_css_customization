
## Product Filter - Categories

This section of the tutorial focuses more on styling the [Product Filter - Categories](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/product-filter-categories/). 

We will be exploring how to change the look and feel of the Product Filter - Categories.

> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)



### Customizing Product Filter - Categories with style option set to List

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


Here's a list of the top three customization request we have received so far with respect to customizations for Product Filter - Categories
* [ ] Display only child categories
* [ ] Change font color of child categories
* [ ] Make category items look like buttons


#### Display only child categories
This is one of our most popular inquiries. If you would love to hide the parent categories and have only the child categories displayed. Please add the CSS snippet below.

_Preview of results_

![Product Filter - categories Example 1](/pfc-inline-1.jpg)

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
        margin: 0;
    }
    ```

#### Change font color of child categories
In this example we'll be changing the color of child categories to red. 

_Preview of results_

![Product Filter - categories Example 2](/pfc-color.jpg)


*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 .cat-parent .children a {
	    color: red;
    }
    ```


#### Make category items look like buttons
In this example we'll change the list item feel to that of a basic button. The extent to which this can be customized is totally depends on your needs. As you can go further by adding **border-radius**, **color**, **font-size**, **background-color** ... 

_Preview of results_

![Product Filter - categories Example 2](/pfc-btns.jpg)


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


### Customizing Product Filter - Categories with style option set to Select
> 

Once the widget or shortcode of **Product Filter - Categories** is placed on your site and the style option set to **Select**, you should have the following HTML structure:

``` html
<div id="product-search-filter-category-0" class="product-search-filter-terms ">
    <div class="product-search-filter-terms-heading product-search-filter-category-heading" id="product-search-filter-category-heading-0">Category</div>
    <select name="product-search-filter-product_cat">
        <option value=""> </option>
        <option value=""> </option>
        <option value=""> </option>
        ...
    </select>
</div>
```
Notes:
> The ID ( `product-search-filter-category-0`) is likely to be different on you setup. Hence, please inspect the element using your browser inspector to identify the ID. Tt is also very likely for you to have an ID like `product-search-filter-category-1`.

Examples covered:
* [ ] Add spacing between categories
* [ ] Increase height of select box


#### Add spacing between categories
In this example we'll focus on increasing the spacing between category items. This example makes uses a padding of 20px around each category item, however these values can be changed to meet your needs.

_Preview of results_

![Product Filter - categories Example 2](/pfc-select-1.jpg)

*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 option {
        padding: 12px;
    }
    ```

#### Increase the height of the select box
In this example we'll increase the height of the select box to 200px.

_Preview of results_

![Product Filter - categories Example 2](/pfc-h.jpg)

*   **ID** we are interested in:
    ```css
        #product-search-filter-select-product_cat-0
    ```

    ``` css
    #product-search-filter-select-product_cat-0 {
        height: 200px;
    }
    ```




### Customizing Product Filter - Categories with style option set to Dropdown
> 

Once the widget or shortcode of **Product Filter - Categories** is placed on your site and the style option set to **Dropdown**, you should have the following HTML structure:

``` html
<div id="product-search-filter-category-0">
    <div class="product-search-filter-select-product_cat-selectize">
        <div class="selectize-input items"></div>
        <div class="selectize-dropdown multi product-categories">
            <div class="selectize-dropdown-content">
                <div class="option">....</div>
                <div class="option">....</div>
                ...
            </div>
        </div>
    </div>
</div>
```
Notes:
> The ID ( `product-search-filter-category-0`) is likely to be different on you setup. Hence, please inspect the element using your browser inspector to identify the ID. Tt is also very likely for you to have an ID like `product-search-filter-category-1`.

Examples covered:
* [ ] Change the background color of selected items
* [ ] Add hover background color to dropdown options


#### Change the background color of selected items
In this example we'll focus on changing the background color of selected items(categories) to teal and its color to white.

_Preview of results_

![Product Filter - categories Example 2](/pfc-os.jpg)

*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0 .has-options .item {
        background-color: #0b7b86;
        color: white;
    }
    ```

#### Add hover background color to dropdown options
This example demonstrates how you could go about adding a hover background color to the dropdown options.

_Preview of results_

![Product Filter - categories Example 2](/pfc-hover.jpg)

*   **ID** we are interested in:
    ```css
        #product-search-filter-category-0
    ```

    ``` css
    #product-search-filter-category-0  .selectize-dropdown .option:hover {
        background-color: #0b7b86;
        color: #fff;
    }
    ```



### How to apply CSS with WPS inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website.

Inorder to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided