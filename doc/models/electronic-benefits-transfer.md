
# Electronic Benefits Transfer

*This model accepts additional fields of type array.*

## Structure

`ElectronicBenefitsTransfer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `category` | `?string` | Optional | Flag that specifies the category for the EBT transaction.<br><br>Possible values:<br><br>- `CASH`: Cash benefits, which can be used to purchase any item at a participating retailer, as well as to obtain cash-back or make a cash withdrawal from a participating ATM.<br>- `FOOD`: Food stamp benefits, which can be used only to purchase food items authorized by the USDA SNAP program.<br><br>#### PIN debit<br><br>Required field for EBT transactions that use PIN debit credit or PIN debit purchase; otherwise, not used.<br><br>**Constraints**: *Maximum Length*: `4` | getCategory(): ?string | setCategory(?string category): void |
| `voucherSerialNumber` | `?string` | Optional | The serial number printed on the EBT voucher.<br><br>#### PIN debit<br><br>Required field for EBT voucher transactions that use PIN debit purchase; otherwise, not used.<br><br>**Constraints**: *Maximum Length*: `15` | getVoucherSerialNumber(): ?string | setVoucherSerialNumber(?string voucherSerialNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ElectronicBenefitsTransferBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$electronicBenefitsTransfer = ElectronicBenefitsTransferBuilder::init()
    ->category('category4')
    ->voucherSerialNumber('voucherSerialNumber6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

