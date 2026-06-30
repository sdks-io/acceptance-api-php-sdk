
# Loan Options

*This model accepts additional fields of type array.*

## Structure

`LoanOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Type of loan based on an agreement between you and the issuer.<br>Examples: AGROCUSTEIO, AGRO-INVEST, BNDES-Type1, CBN, FINAME.<br>This field is supported only for these kinds of payments:<br><br>- BNDES transactions on Visa Acceptance through VisaNet.<br>- Installment payments with Mastercard on Visa Acceptance through VisaNet in Brazil.<br><br>For BNDES transactions, the value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP07 TCR2, Position: 27-46, Field: Loan Type<br><br>For installment payments with Mastercard in Brazil, the value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP07 TCR4, Position: 5-24,Field: Financing Type<br><br>**Constraints**: *Maximum Length*: `20` | getType(): ?string | setType(?string type): void |
| `assetType` | `?string` | Optional | Indicates whether a loan is for a recoverable item or a non-recoverable item.<br>Possible values:<br><br>- `N`: non-recoverable item<br>- `R`: recoverable item<br>  This field is supported only for BNDES transactions on Visa Acceptance through VisaNet.<br>  The value for this field corresponds to the following data in the TC 33 capture file5:<br>  Record: CP07 TCR2, Position: 26, Field: Asset Indicator<br><br>**Constraints**: *Maximum Length*: `1` | getAssetType(): ?string | setAssetType(?string assetType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LoanOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$loanOptions = LoanOptionsBuilder::init()
    ->type('type2')
    ->assetType('assetType4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

