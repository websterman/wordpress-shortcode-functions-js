# wordpress-shortcode-functions-js
Searches a string for Wordpress shortcodes and calls a mapped function with the attributes as parameters. Return values replace the shortcode in the string.


Usage: WPShortcodes( string, functionMap );

Returns an object with the following structure:

{
    markup: The returned markup
    shortcodes : [ 
        {   
            code: The shortcode name,
            raw: The entire shortcode,
            attributes: [
                {
                    name: The name of the attribute.
                    value: The value of the attribute.
                }
            ]   
        }
    ]
}

The functionMap object should be sorted as such: 

{
    'exampleShortcode': exampleShortcodeFunction
}

Where the value is a valid function. The shortcode attributes will be passed to the function as an object with the following structure:

{
    name: Attribute name,
    value: Attribute value
}