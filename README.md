# opencart-custom-field-tooltips
This extension modifies OpenCart so that a Customer Custom Field can have a tooltip associated with it to explain to the user what its purpose is.

## Requirements
OpenCart, written for v2.1.0.1
vQmod, written for v2.5.1

## Installation
Place the XML file in vqmod/xml and run the below query on your database.
```
CREATE TABLE IF NOT EXISTS `oc_custom_field_tooltip` (
  `custom_field_id` int(11) NOT NULL,
  `language_id` int(11) NOT NULL,
  `tooltip` text NOT NULL,
  PRIMARY KEY (`custom_field_id`,`language_id`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8;
```

## Usage
Once installed, you will see a new field in the Custom Field edit screen: immediately below the Custom Field Name will be a Tooltip Description field. What is entered here will appear as a tooltip for the field on the customer registration form. It should support multiple languages, though this is untested.

The vQmod script modifies the default theme but you will need to make a similar modification to any custom theme you might be using; search for "theme/default" in the script to see what was done to the default theme files.

This is my first OpenCart vQmod extension so I'm open to criticism!
