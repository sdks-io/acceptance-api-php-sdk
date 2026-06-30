
# Mandate

*This model accepts additional fields of type array.*

## Structure

`Mandate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clearingDate` | `?string` | Optional | This is the date on which the SEPA DD should be executed. Debit date: the day on which the payer's account is debited.<br><br>**Constraints**: *Maximum Length*: `8` | getClearingDate(): ?string | setClearingDate(?string clearingDate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MandateBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$mandate = MandateBuilder::init()
    ->clearingDate('clearingDate6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

