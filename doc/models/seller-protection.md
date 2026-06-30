
# Seller Protection

*This model accepts additional fields of type array.*

## Structure

`SellerProtection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | The kind of seller protection in force for the transaction. This field is<br>returned only when the protection eligibility value is set to<br>ELIGIBLE or PARTIALLY_ELIGIBLE.<br>Possible values<br><br>- ITEM_NOT_RECEIVED_ELIGIBLE: Sellers are protected<br>  against claims for items not received.<br>- UNAUTHORIZED_PAYMENT_ELIGIBLE: Sellers are<br>  protected against claims for unauthorized payments.<br>  One or both values can be returned. | getType(): ?string | setType(?string type): void |
| `eligibility` | `?string` | Optional | Indicates whether the transaction is eligible for seller protection. The values returned are described below.<br>Possible values:<br><br>- `ELIGIBLE`<br>- `PARTIALLY_ELIGIBLE`<br>- `INELIGIBLE`<br>- `NOT_ELIGIBLE`<br><br>**Constraints**: *Maximum Length*: `36` | getEligibility(): ?string | setEligibility(?string eligibility): void |
| `disputeCategories` | `?(string[])` | Optional | An array of conditions that are covered for the transaction. | getDisputeCategories(): ?array | setDisputeCategories(?array disputeCategories): void |
| `eligibilityType` | `?string` | Optional | The kind of seller protection in force for the transaction. This field is returned only when the protection_eligibility property is set to ELIGIBLE or PARTIALLY_ELIGIBLE.<br>Possible values:<br><br>- `ITEM_NOT_RECEIVED_ELIGIBLE: Sellers are protected against claims for items not received.`<br>- `UNAUTHORIZED_PAYMENT_ELIGIBLE: Sellers are protected against claims for unauthorized payments.`<br>  One or both values can be returned.<br><br>**Constraints**: *Maximum Length*: `60` | getEligibilityType(): ?string | setEligibilityType(?string eligibilityType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SellerProtectionBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$sellerProtection = SellerProtectionBuilder::init()
    ->type('type0')
    ->eligibility('eligibility6')
    ->disputeCategories(
        [
            'disputeCategories3'
        ]
    )
    ->eligibilityType('eligibilityType8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

