
# Installment Information 4

*This model accepts additional fields of type array.*

## Structure

`InstallmentInformation4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `alertPreference` | `?string` | Optional | Applicable only for SI. Required in case the authentication is initiated for SI registration.<br>Valid Values:<br><br>- `SMS`<br>- `EMAIL`<br>- `BOTH`<br><br>**Constraints**: *Maximum Length*: `5` | getAlertPreference(): ?string | setAlertPreference(?string alertPreference): void |
| `firstInstallmentDate` | `?string` | Optional | Date of the first installment payment. Format: YYMMDD. When you do not include this field, Visa Acceptance sends a string of six zeros (000000) to the processor.<br><br>This field is supported only for Crediario installment payments in Brazil on Visa Acceptance through VisaNet.<br><br>The value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCR9<br>- Position: 42-47<br>- Field: Date of First Installment<br><br>**Constraints**: *Maximum Length*: `6` | getFirstInstallmentDate(): ?string | setFirstInstallmentDate(?string firstInstallmentDate): void |
| `identifier` | `?string` | Optional | Standing Instruction/Installment identifier. | getIdentifier(): ?string | setIdentifier(?string identifier): void |
| `lastInstallmentDate` | `?string` | Optional | End date of the SI transactions.<br>Cannot be later than card expiry date. Ideally this can be set to expiry date.<br>Required in case the authentication is initiated for SI registration.<br><br>**Constraints**: *Maximum Length*: `8` | getLastInstallmentDate(): ?string | setLastInstallmentDate(?string lastInstallmentDate): void |
| `maxAmount` | `?string` | Optional | Maximum Amount for which SI can be initiated.<br>Required in case the authentication is initiated for SI registration.<br><br>**Constraints**: *Maximum Length*: `12` | getMaxAmount(): ?string | setMaxAmount(?string maxAmount): void |
| `minAmount` | `?string` | Optional | Minimum Amount for which SI can be initiated.<br>Required in case the authentication is initiated for SI registration.<br><br>**Constraints**: *Maximum Length*: `12` | getMinAmount(): ?string | setMinAmount(?string minAmount): void |
| `paymentType` | `?string` | Optional | Payment plan for the installments.<br>This field is supported only for installment payments on Visa Platform Connect, RuPay and SPG-KSA seamless flow.<br><br>Possible values for a standing-instruction (SI) merchant-initiated transaction (MIT) with Diners Club or Mastercard in India or with an India-issued card:<br><br>- 1: SI with a fixed amount.<br>- 2: SI with a maximum amount.<br>- 3: Other kind of SI.<br><br>Possible values for a type of Installment transaction for on-soil transaction in Kingdom of Saudi Arabia<br><br>- 1: Registration or first transaction.<br>- 2: Subsequent transaction.<br><br>Possible values for other kinds of installment payments:<br><br>- 0 (default): Regular installment. This value is not allowed for airline transactions.<br>- 1: Installment payment with down payment.<br>- 2: Installment payment without down payment. This value is supported only for airline transactions.<br>- 3: Installment payment; down payment and boarding fee will follow. This value is supported only for airline transactions.<br>- 4: Down payment only; regular installment payment will follow.<br>- 5: Boarding fee only. This value is supported only for airline transactions.<br>- 6: SI de-registration on RuPay for the payer authentication seamless flow.<br><br>**Constraints**: *Maximum Length*: `1` | getPaymentType(): ?string | setPaymentType(?string paymentType): void |
| `preferredDay` | `?string` | Optional | Preferred date for initiating the SI transaction every month.<br>This field need not be sent in case the SI has to be initiated as and when required, e.g., topping up the wallet, etc.<br><br>**Constraints**: *Maximum Length*: `2` | getPreferredDay(): ?string | setPreferredDay(?string preferredDay): void |
| `sequence` | `?int` | Optional | Installment number when making payments in installments. Used along with `totalCount` to track which payment is being processed.<br><br>For example, the second of 5 payments would be passed to Visa Acceptance as `sequence` = 2 and `totalCount` = 5.<br><br>#### Chase Paymentech Solutions and FDC Compass<br><br>This field is optional because this value is required in the merchant descriptors.<br><br>#### Visa Acceptance through VisaNet<br><br>When you do not include this field in a request for a Crediario installment payment, Visa Acceptance sends a value of 0 to the processor.<br><br>For Crediario installment payments, the value for this field corresponds to the following data in the TC 33 capture file*:<br><br>- Record: CP01 TCR9<br>- Position: 38-40<br>- Field: Installment Payment Number<br><br>* The TC 33 Capture file contains information about the purchases and refunds that a merchant submits to Visa Acceptance. Visa Acceptance through VisaNet creates the TC 33 Capture file at the end of the day and sends it to the merchant’s acquirer, who uses this information to facilitate end-of-day clearing processing with payment card companies.<br><br>**Constraints**: `<= 999` | getSequence(): ?int | setSequence(?int sequence): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$installmentInformation4 = InstallmentInformation4Builder::init()
    ->alertPreference('alertPreference4')
    ->firstInstallmentDate('firstInstallmentDate8')
    ->identifier('identifier4')
    ->lastInstallmentDate('lastInstallmentDate4')
    ->maxAmount('maxAmount6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

