
# Account 14

*This model accepts additional fields of type array.*

## Structure

`Account14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | The account number of the sender. | getNumber(): ?string | setNumber(?string number): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account14 = Account14Builder::init()
    ->number('number2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

