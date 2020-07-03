## WPS Style Customizations

### Product Filter - Search 

Once the widget Product Filter - Search is place on a side bar, you would have the following default html in place.

``` html
<div id="product-filter-search-0" class="product-search product-filter product-search-filter-search" style="">
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
> the elements with ID's ( `product-filter-search-form-0` and `product-filter-search-0` ) are likely to be different on you setup. So please inspect the element using your browser inspector to identify the ID. Hence it is very likely for you to have these ID's `product-filter-search-form-1` and `product-filter-search-1` as well.


**Based on the HTML above let's customize the search filter**

#### Mini design project to master customizing your WPS.
* [x] Style the Product Filter - Search Widget _See section 1_
* [x] Change blinker for input field _See section 1.1
* [x] list syntax required (any unordered or ordered list supported)
* [x] this is a complete item
* [ ] this is an incomplete item

1. #### [SECTION 1] Let's archieve the following design with CSS
    _Preview of final result_
    ![Product Search - Filter Example 1](/p_s_f_input.png)
    *   **HTML Elements** of insterest:
        ``` html
            <form id="product-filter-search-form-0" class="product-search-form " action="..." method="...">
            <input id="product-filter-field-0" name="ixwpss" type="text" class="product-filter-field" placeholder="..." autocomplete="off" value="">
        ```
    *   **ID's** we are insterected in:
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

    ```` css
    #product-filter-search-form-0::before {
        -moz-osx-font-smoothing: grayscale;
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

2.  ##### [SECTION 1. 1] Change blinker for input field
    Changing the loading image is as simple as changing the background image of this input field when it has the `.blinker` class
        
    _Preview of \final result_
    [Gif used](https://ya-webdesign.com/image/loading-gif-png/654656.html)
    ![Product Search - Filter Example 1](/blinker_final.png)

    _Preview of \form before styling result_
    ![Product Search - Filter Example 1](/blinker_before.png)

    *   **HTML Elements** of insterest:
        ``` html
            <input id="product-filter-field-0" name="ixwpss" type="text" class="product-filter-field blinker" placeholder="..." autocomplete="off" value="">
        ```
    *   **ID(s) and class(es)** we are insterected in:
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
        
        
