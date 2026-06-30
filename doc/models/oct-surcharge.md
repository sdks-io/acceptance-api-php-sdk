
# Oct Surcharge

*This model accepts additional fields of type array.*

## Structure

`OctSurcharge`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?string` | Optional | The surcharge amount is included in the total transaction amount but is passed in a separate field to the issuer and acquirer for tracking.<br>The issuer can provide information about the surcharge amount to the customer.<br><br>If the amount is positive, then it is a debit for the customer.<br><br>If the amount is negative, then it is a credit for the customer.<br><br>**Constraints**: *Maximum Length*: `8` | getAmount(): ?string | setAmount(?string amount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OctSurchargeBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$octSurcharge = OctSurchargeBuilder::init()
    ->amount('amount8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

