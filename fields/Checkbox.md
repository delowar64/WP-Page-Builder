
# Checkbox
A Multiple Checkbox Input Field

## Parameters
Parameter | Type | Value
--- | --- | ---
type | `required` | Predefined String (checkbox)
title | `optional` | String
desc | `optional` | String
values | `optional` | Array
multiple | `optional` | Boolean ( Default: false )
std | `optional` | String( multiple: false ) or Array (multiple: false)
selector | `optional` | String / Array
tab | `optional` | String(style)
section | `optional` | String

## Return
return single `string` single  
return `array` for the multiple

## Example
**Single**
```php
'addon_checkbox' => array (
    'type' => 'checkbox',
    'title' => __('Checkbox Field','your-textdomain'),
    'values' => array(
		'10px' => 'Small Height',
		'20px' => 'Medium Height',
		'40px' => 'Large height'
	    ),
    'std' => '20px',
    'selector'	=> '{{SELECTOR}} .example-checkbox{ margin-left:{{data.addon_checkbox}}; }'
)
```
Support 'selector' parameters.


**Multiple**
```php
'addon_checkbox' => array (
    'type' => 'checkbox',
    'title' => __('Checkbox Title','your-textdomain'),
    'values' => array(
                    'type1' => 'Type 1',
                    'type2' => 'Type 2',
                    'type3' => 'Type 3'
                ),
    'std' => ['type1','type2'],
    'multiple' => true
)
```

## Controls
### PHP
Inside the `rander()` method-
```php
echo '<div>'.$data['settings']['addon_checkbox'].'</div>';
<div class="example-checkbox">Example Checkbox</div>
```

**Multiple**
```php
echo '<div>';
    foreach($data['settings']['addon_checkbox'] as $value) {
        echo $value;
    }
echo '</div>';
```

### JS Template
Inside the `getTemplate()` method-

**Single**
```js
<div>{{data.addon_checkbox}}</div>
<div class="example-checkbox">Example Checkbox</div>
```

**Multiple**
```js
<div>
<# _.forEach(data.addon_checkbox, function(value, key) { #>
    {{value}}
<# } #>
</div>
```
