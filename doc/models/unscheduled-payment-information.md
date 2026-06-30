
# Unscheduled Payment Information

*This model accepts additional fields of type array.*

## Structure

`UnscheduledPaymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Indicates the type of unscheduled payment. This field is required for unscheduled payments CIT/MIT Possible values:<br>1: First unscheduled transaction.<br>2: Subsequent unscheduled transaction.<br><br>**Constraints**: *Maximum Length*: `1` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\UnscheduledPaymentInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$unscheduledPaymentInformation = UnscheduledPaymentInformationBuilder::init()
    ->type('type2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

