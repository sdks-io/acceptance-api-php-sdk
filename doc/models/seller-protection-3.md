
# Seller Protection 3

*This model accepts additional fields of type array.*

## Structure

`SellerProtection3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eligibilty` | `?string` | Optional | The level of seller protection in force for the transaction.<br>Possible values:<br><br>- `ELIGIBLE`<br>- `PARTIALLY_ELIGIBLE`<br>- `INELIGIBLE`<br><br>**Constraints**: *Maximum Length*: `60` | getEligibilty(): ?string | setEligibilty(?string eligibilty): void |
| `type` | `?string` | Optional | The kind of seller protection in force for the transaction. This field is returned only when the protection eligibility is set to ELIGIBLE or PARTIALLY_ELIGIBLE.<br>Possible values:<br><br>- `ITEM_NOT_RECEIVED_ELIGIBLE: Sellers are protected against claims for items not received.`<br>- `UNAUTHORIZED_PAYMENT_ELIGIBLE: Sellers are protected against claims for unauthorized payments.One or both values can be returned.`<br><br>**Constraints**: *Maximum Length*: `60` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SellerProtection3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$sellerProtection3 = SellerProtection3Builder::init()
    ->eligibilty('eligibilty2')
    ->type('type0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

