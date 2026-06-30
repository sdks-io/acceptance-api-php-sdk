
# Color

*This model accepts additional fields of type array.*

## Structure

`Color`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `border` | `?string` | Optional | Border Color<br><br>**Constraints**: *Maximum Length*: `10` | getBorder(): ?string | setBorder(?string border): void |
| `borderSelected` | `?string` | Optional | Selected Border Color<br><br>**Constraints**: *Maximum Length*: `10` | getBorderSelected(): ?string | setBorderSelected(?string borderSelected): void |
| `button` | `?string` | Optional | Button Color<br><br>**Constraints**: *Maximum Length*: `10` | getButton(): ?string | setButton(?string button): void |
| `buttonText` | `?string` | Optional | Button Text Color<br><br>**Constraints**: *Maximum Length*: `10` | getButtonText(): ?string | setButtonText(?string buttonText): void |
| `checkbox` | `?string` | Optional | Checkbox Color<br><br>**Constraints**: *Maximum Length*: `10` | getCheckbox(): ?string | setCheckbox(?string checkbox): void |
| `checkboxCheckMark` | `?string` | Optional | Checkbox Checkmark Color<br><br>**Constraints**: *Maximum Length*: `10` | getCheckboxCheckMark(): ?string | setCheckboxCheckMark(?string checkboxCheckMark): void |
| `header` | `?string` | Optional | Header Color<br><br>**Constraints**: *Maximum Length*: `10` | getHeader(): ?string | setHeader(?string header): void |
| `link` | `?string` | Optional | Link Color<br><br>**Constraints**: *Maximum Length*: `10` | getLink(): ?string | setLink(?string link): void |
| `text` | `?string` | Optional | Text Color<br><br>**Constraints**: *Maximum Length*: `10` | getText(): ?string | setText(?string text): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ColorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$color = ColorBuilder::init()
    ->border('border0')
    ->borderSelected('borderSelected2')
    ->button('button8')
    ->buttonText('buttonText8')
    ->checkbox('checkbox6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

