
# Purchase Options 2

*This model accepts additional fields of type array.*

## Structure

`PurchaseOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `isElectronicBenefitsTransfer` | `?bool` | Optional | Flag that indicates whether this transaction is an EBT transaction. Possible values:<br><br>- `true`<br>- `false`<br><br>#### PIN debit<br><br>Required field for EBT and EBT voucher transactions that use PIN debit credit or PIN debit purchase; otherwise, not used. | getIsElectronicBenefitsTransfer(): ?bool | setIsElectronicBenefitsTransfer(?bool isElectronicBenefitsTransfer): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PurchaseOptions2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$purchaseOptions2 = PurchaseOptions2Builder::init()
    ->isElectronicBenefitsTransfer(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

