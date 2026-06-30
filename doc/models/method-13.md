
# Method 13

*This model accepts additional fields of type array.*

## Structure

`Method13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Identifier for the payment type.<br>Possible Values:<br><br>- SENTENIAL<br>- PAYPAL<br><br>#### SEPA/BACS<br><br>Required for mandates services<br><br>#### Paypal<br><br>Required for billing agreements | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Method13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$method13 = Method13Builder::init()
    ->name('name0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

