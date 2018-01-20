# Drawing Circles (Hollow Circle)
#### Language: PHP

### Code:
```php
$amount = 10; // change to your needs
$radius = 8; // change to your needs

$diff = intval(360 / $amount); // Every n degrees [angle]

// Horizontal ///////////////////////////////////////////////////////////
for($angle = 0; $angle <= 360; $angle += $diff){
	$offsetX = $radius * sin($angle);
	$offsetZ = $radius * cos($angle);

	// your code here... just add current X and Z to offset X and Z
}

// Vertical (Moving in the Y and Z axis) ///////////////////////////////////////
for($angle = 0; $angle <= 360; $angle += $diff){
	$offsetY = $radius * sin($angle);
	$offsetZ = $radius * cos($angle);

	// your code here... just add current Y and Z to offset Y and Z
}

// Vertical (Moving in the Y and X axis) ///////////////////////////////////////
for($angle = 0; $angle <= 360; $angle += $diff){
	$offsetY = $radius * sin($angle);
	$offsetX = $radius * cos($angle);

	// your code here... just add current Y and X to offset Y and X
}
```
