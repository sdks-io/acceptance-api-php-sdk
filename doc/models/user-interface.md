
# User Interface

*This model accepts additional fields of type array.*

## Structure

`UserInterface`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `borderRadius` | `?string` | Optional | Border Radius, Allowed Values - Number, Chars, SPACE, Percentage(%), DOT(.),<br>Example '25px 10px 25px 10px'; '2em 1em 0.5em 3em'<br><br>**Constraints**: *Maximum Length*: `19` | getBorderRadius(): ?string | setBorderRadius(?string borderRadius): void |
| `theme` | `?string` | Optional | UI Theme Name/Design Name - Allowed Chars: Alpha Numeric, Dot (.), Hyphen (-), Underscore (_)<br><br>**Constraints**: *Maximum Length*: `19` | getTheme(): ?string | setTheme(?string theme): void |
| `color` | [`?Color`](../../doc/models/color.md) | Optional | - | getColor(): ?Color | setColor(?Color color): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\UserInterfaceBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ColorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$userInterface = UserInterfaceBuilder::init()
    ->borderRadius('borderRadius2')
    ->theme('theme0')
    ->color(
        ColorBuilder::init()
            ->border('border0')
            ->borderSelected('borderSelected2')
            ->button('button8')
            ->buttonText('buttonText8')
            ->checkbox('checkbox6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

