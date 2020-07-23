
## Product Filter-Search 

This section of the tutorial focuses more on styling the [WooCommerce Product Filter-Search](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/product-filter-search/). 

We will be exploring how to change the look and feel of the Product Filter-Search.

> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

> 

Once the widget **Product Filter-Search widget** is place on a side bar, you would have the following default HTML in place.

``` html
<div id="product-filter-search-1" class="product-search product-filter product-search-filter-search" style="">
    <div class="product-search-form">
        <form id="product-filter-search-form-0" class="product-search-form " action="..." method="...">
            <input id="product-filter-field-0" name="ixwpss" type="text" class="product-filter-field" placeholder="..." autocomplete="off" value="">
            <input type="hidden" name="title" value="1">
            <input type="hidden" name="excerpt" value="1">
            <input type="hidden" name="content" value="1">
            <input type="hidden" name="categories" value="1">
            <input type="hidden" name="attributes" value="1">
            <input type="hidden" name="tags" value="1">
            <input type="hidden" name="sku" value="1">
            <button type="submit">Search</button>
        </form>
    </div>
    <div id="product-filter-results-0" class="product-filter-results"></div>
</div>
```
Notes:
> These IDs ( `product-filter-search-form-0` and `product-filter-search-0` ) are likely to be different on you setup. Hence, please inspect the element using your browser inspector to identify the ID. Tt is also very likely for you to have these IDs `product-filter-search-form-1` and `product-filter-search-1`.


### Customizing Product Search-Filter
We have prepared a mini design customization project aimed at helping you master the style customizations for Product Search - Filter.
* [ ] Style the Product Filter-Search Widget
* [ ] Change blinker for the Product Search - Filter input field

### Styling the Product Search-Filter input field 
In this mini-project we would be adding a teal search icon and teal border to the Product Search - Filter input field.

_Preview of final result_

![Product Search - Filter Example 1](/p_s_f_input.png)

*   **HTML elements** of interest:
    ``` html
        <form id="product-filter-search-form-0" class="product-search-form " action="..." method="...">
        <input id="product-filter-field-0" name="ixwpss" type="text" class="product-filter-field" placeholder="..." autocomplete="off" value="">
    ```
*   **IDs** we are interested in:
    ```css
        #product-filter-search-form-0
        #product-filter-field-0
    ```
    ``` css
    #product-filter-field-0 {
        border: solid 2px teal;
        background-color: #fff;
        color: teal;
        font-size: 16px;
        padding: 10px 36px;
        outline: none;
    }
    ```
    _Adding search ICON to the Product Search - Filter Widget_

    ``` css
    #product-filter-search-form-0::before {
        display: inline-block;
        font-style: normal;
        font-variant: normal;
        font-weight: normal;
        line-height: 1;
        font-family: 'Font Awesome 5 Free';
        font-weight: 900;
        vertical-align: baseline;
        content: "\f002";
        position: absolute;
        top: 1.3em;
        left: 1em;
        color: teal
    }
    ```

### Changing the search filter loader icon
Mini project two focuses on changing the rectangular blinker for the Product Search-Filter input field to a radial loading gif. 

> We achieve this by changing the background image of this Product Search-Filter input field when it has the `.blinker` class
    
_Preview of final result_
[GIF used](https://ya-webdesign.com/image/loading-gif-png/654656.html)
![Product Search - Filter Example 1](/blinker_final.png)

_Preview of \form before styling result_
![Product Search - Filter Example 1](/blinker_before.png)

*   **HTML elements** of interest:
    ``` html
        <input id="product-filter-field-0" name="ixwpss" type="text" class="product-filter-field blinker" placeholder="..." autocomplete="off" value="">
    ```
*   **ID and classes** we are interested in:
    ```css
        #product-filter-search-form-0 or .product-search-form
        .blinker
    ```

    _Adding search ICON to the Product Search - Filter Widget_
    ``` css
    .product-search-form input.blinker {
        background-image: url('/wp-content/uploads/2020/07/loading-gif-png.gif');
        background-position: right 8px center;
        background-repeat: no-repeat;
        background-size: 10%;
    }
    ```
        

### How to apply CSS with WPS inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website.

Inorder to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided