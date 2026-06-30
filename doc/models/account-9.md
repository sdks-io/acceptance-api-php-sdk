
# Account 9

*This model accepts additional fields of type array.*

## Structure

`Account9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | Customer’s bank account number.<br><br>#### BACS<br><br>Required for Create Mandate, Import Mandate, and Update Mandate<br><br>**Constraints**: *Maximum Length*: `30` | getNumber(): ?string | setNumber(?string number): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account9 = Account9Builder::init()
    ->number('number0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

