## WooCommerce Product Search CSS Customizations

### Introduction

This section of the documentation is aimed at helping you customize your WooCommerce Product Search by adding custom styles. It gives you an overview of how to modify the layout, colors, and so much more. 

This tutorial is based of the [Storefront WooCommerce theme](https://woocommerce.com/storefront/). 

The browser used in the tutorials is Mozilla Firefox. However, it is worth nothing that the instructions here would also apply on your stores with different themes and browsers. We would also be using the [Inline Styles CSS editor](https://docs.woocommerce.com/document/Ioocommerce-product-search/settings/css/) in order to apply the custom styles.

#### Documentation sections
* [Product Search Field](/WPS_StyleCustomizations.md)
* [Product Filter - Search ](/ProductSearchFilter.md)

#### Relevant links:
* [Product Search Widgets documentation](https://docs.woocommerce.com/document/woocommerce-product-search/widgets/)
* [Product Search shortcodes documentation](https://docs.woocommerce.com/document/woocommerce-product-search/shortcodes)
* [Product Search API function's documentation](https://docs.woocommerce.com/document/woocommerce-product-search/api/functions/)

### How to inspect and locate IDs and classes
This is very important as most of the tutorial relies heavily on this. We would be using the **developer console** for this. 

In order to access the developer console:
* **Right click** on the webpage and select **Inspect Element** OR press the ```Ctrl``` ```Shift``` ```K``` (```Command``` ```Option``` ```K``` on macOS) keyboard shortcut. [for Mozilla Firefox]
* **Right click** on the webpage and select **Inspect** OR press the ```Ctrl``` ```Shift``` ```C``` (```Command``` ```Option``` ```C``` on macOS) keyboard shortcut. [for Google Chrome]

Let's move on to identifying the IDs and classes that are made available by the WooCommerce Product Search. These IDs and classes would be used to help target the HTML elements you intend to style.

**See screenshots:**
1. Before
   ![How to Inspect a Product Search Field](/find_id.png)

2. After Inspecting
   ![How to Inspect a Product Search Field](/console.png)

> 
> Though we assume you know your way around with CSS rules. Here's a good resource to help refresh your mind on CSS rules and how to target HTML elements with CSS.
> * [CSS rules reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
> * [How to target HTML with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

> 

After inspecting the Product Search Field, you should be able to see the following HTML in your console.

``` html
<div class="widget woocommerce widget_product_search">
    <div id="product-search-0" class="product-search floating">
        <div class="product-search-form">
            <form id="product-search-form-0" class="product-search-form show-submit-button" action="http://wpdev-com.stackstaging.com/" method="get">
                ::before
                <input id="product-search-field-0" name="s" type="text" class="product-search-field" placeholder="Search products …" autocomplete="off">
                <input type="hidden" name="post_type" value="product">
                <input type="hidden" name="title" value="1">
                <input type="hidden" name="excerpt" value="1">
                <input type="hidden" name="content" value="1">
                <input type="hidden" name="categories" value="1">
                <input type="hidden" name="attributes" value="1">
                <input type="hidden" name="tags" value="1">
                <input type="hidden" name="sku" value="1">
                <input type="hidden" name="orderby" value="date-DESC">
                <input type="hidden" name="ixwps" value="1">
                <span title="Clear" class="product-search-field-clear" style="display:none"></span> 
                <button type="submit">Search</button>
            </form>
        </div>
        <div id="product-search-results-0" class="product-search-results">
            <div id="product-search-results-content-0" class="product-search-results-content" style="display: none;"></div>
        </div>
    </div>
</div>
```
It is worth noting that the following IDs might differ depending on your install. 
* ```product-search-0```, ```product-search-form-0```, ```product-search-field-0```, ```product-search-results-0```
Hence, please if you have something like this instead: ```product-search-1```, ```product-search-form-1```, ```product-search-field-1```, ```product-search-results-1``` OR an ID with any other suffix that is still very okay. 
> If you would love to copy and apply a CSS rule from this tutorial, please verify that the integer suffix on the IDs or classes match. If not please modify them accordingly.

### Examples covered
* [ ] Add a teal border of size 2px to Product Search Field
* [ ] Changing the search icon within the search field to a red color
* [ ] Styling Product Search Field result section
    * [ ] Add a blue border to the search result container
    * [ ] Make Add to Cart button red with white text
    * [ ] Make the cancel search icon bigger and red

### 1. Adding a border to Product Search Field
This example focuses on adding a border to the Product Search Field. For example let's **add a teal border of size 2px to Product Search Field**.

_Preview of final result_
![Product Search Field teal border](/2pxborder.png)

**HTML elements** of interest:
``` html
    <div id="product-search-0" class="product-search floating"> OR 
    <input id="product-search-field-0" name="s" type="text" class="product-search-field" placeholder="Search products …" autocomplete="off">
```
*   **IDs** we are interested in:
```css
    #product-search-0 OR
    #product-search-field-0
```
**CSS used**:
``` css
#product-search-0 {
    border: solid 2px teal;
}

OR

#product-search-field-0 {
    border: solid 2px teal;
}

```

### 2. Styling the Product Search Field

This example focuses on modifying the Product Search Field icon color. For instance if you wanted to change the search icon to a red color, here's what you'll do.

_Preview of final result_

![Product Search field: Red Icon](/redicon.png)

**HTML elements** of interest:
``` html
    ::before pseudo-element found within the form.
```
*   **IDs** we are interested in:
```css
    #product-search-form-0  and  
    ::before psuedo element. 
```
**CSS used**:
``` css

#product-search-form-0::before {
    color: red
}
```
<hr>

In the next example, we focus on completely changing the default search icon for the Product Search Field. WooCommerce Product Search uses [FontAwesome](https://fontawesome.com/) icons. 

For example, assume we wanted to change the default search icon to a **teal 18px [search-plus icon](https://fontawesome.com/icons/search-plus?style=solid)**, we would have to get the Unicode for this icon( _\f00e_ ). 

> Notice the use of the **backward slash** before Unicode value itself. This is because it is required in order to render on the browser.

Here's a link to all [FontAwesome icons Unicodes](https://fontawesome.com/cheatsheet).

_Preview of final result_

![Product Search field: Red Icon](/search-plus.png)
**HTML elements** of interest:
``` html
    ::before pseudo-element found within the form.
```
*   **IDs** we are interested in:
```css
    #product-search-form-0  and  
    ::before psuedo element. 
```
**CSS used**:
``` css
#product-search-form-0::before {
	content: "\f00e";
	font-size: 18px;
	color: teal;
	margin: -4px -7px;
}
```
> The line of CSS to change the icon only is done with **```content: "\f00e";```**. The other CSS properties, simply improve aesthetics. 

### 3. Styling the Product Search Field Results
In this section we consider you intend to style the results displayed after a search has occurred. And the search dropdown is visible. An example of the HTML produced after a search result is obtained can be seen below alongside a breakdown of each section.

![Product Search field results HTML](/search-results.png)

### 3.1 Add border to the search result container
In this example we will be adding a 2px blue border to the search results container.

_Preview of final result_

![Product Search Results border-blue](/blue-bd.png)

*   **HTML elements** of interest:
    ``` html
        <div id="product-search-0" class="product-search floating"> OR 
        <input id="product-search-field-0" name="s" type="text" class="product-search-field" placeholder="Search products …" autocomplete="off">
    ```
*   **ID** we are interested in:
    ```css
        #product-search-results-content-0
    ```
    **CSS used**:
    ``` css
        #product-search-results-content-0 {
            border: solid 2px blue;
        }

    ```

### 3.2 Style ADD TO CART button
In this example we explore styling the add to cart button by giving it **red background color** and a **white text**.

_Preview of final result_

![Product Search - Filter Example 1](/red-btn.png)

*   **HTML elements** of interest:
    ``` html
        <div id="product-search-0" class="product-search floating"> 
        <a href="..." data-quantity="..." class="button product_type_simple add_to_cart_button ajax_add_to_cart" data-product_id="..." >Add to cart</a>
    ```
*   **ID and classes** we are interested in:
    ```css
        #product-search-0 , for ID 
        .wps_add_to_cart and  .add_to_cart_button for classes
    ```
    **CSS used**:
    ``` css
        #product-search-0 .wps_add_to_cart .add_to_cart_button {
            background-color: red;
            color: white;
        }

    ```

### 3.3 Styling the clear icon
In this example we explore one of the most sought-after customizations; **"how do I make the cancel search icon bigger and red?"**.

_Preview of final result_

![Product Search - Filter Example 1](/red-cancel.png)

*   **HTML elements** of interest:
    ``` html
        <div id="product-search-0" class="product-search floating"> 
        <span title="Clear" class="product-search-field-clear" style=""></span>
    ```
*   **ID and class** we are interested in:
    ```css
        #product-search-0 , for ID 
        .product-search-field-clear for class
    ```
    **CSS used**:
    ``` css
        #product-search-0 .product-search-field-clear {
            font-size: 30px;
            color: red;
        }

    ```

### How to apply CSS with WooCommerce Product Search inline stylesheet.
The Animated GIF below demonstrates how you would apply your custom styles to your website. In the example below we demonstrate how you would go about applying a 2px red border and a red icon search icon to your search field. 

In order to access the inline stylesheet, from your admin dashboard you would;
* Navigate to: **WooCommerce -> Settings -> Search -> CSS**
* Make sure the **Use inline styles** option is enabled
* Paste your CSS rules in the **Inline styles** stylesheet provided

![Product Search - Filter Example 1](/styles.gif)

