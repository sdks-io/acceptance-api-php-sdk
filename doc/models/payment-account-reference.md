
# Payment Account Reference

*This model accepts additional fields of type array.*

## Structure

`PaymentAccountReference`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | A Payment Account Reference number (PAR) is a unique reference value associated with a specific card holder PAN. It identifies the card account, not just a card. PAR is a non-payment identifier that can be associated to PANs and tokens, as defined by EMVCo. PAR allows all participants in the payments chain to have a single, non-sensitive value assigned to a consumer. This value can be used in place of sensitive card holder identification fields, and transmitted across the payments ecosystem to facilitate card holder identification.<br><br>**Constraints**: *Maximum Length*: `29` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentAccountReferenceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentAccountReference = PaymentAccountReferenceBuilder::init()
    ->id('id8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

