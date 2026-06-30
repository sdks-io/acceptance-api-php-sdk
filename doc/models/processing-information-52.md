
# Processing Information 52

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation52`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `binSource` | `?string` | Optional | Bin Source File Identifier.<br>Possible values:<br><br>- itmx<br>- rupay | getBinSource(): ?string | setBinSource(?string binSource): void |
| `industryDataType` | `?string` | Optional | Indicates that the transaction includes industry-specific data.<br><br>Possible Values:<br><br>- `airline`<br>- `restaurant`<br>- `lodging`<br>- `auto_rental`<br>- `transit`<br>- `healthcare_medical`<br>- `healthcare_transit`<br>- `transit`<br><br>#### Card Present, Airlines and Auto Rental<br><br>You must set this field to `airline` in order for airline data to be sent to the processor. For example, if this<br>field is not set to `airline` or is not included in the request, no airline data is sent to the processor.<br><br>You must set this field to `restaurant` in order for restaurant data to be sent to the processor. When this field<br>is not set to `restaurant` or is not included in the request, no restaurant data is sent to the processor.<br><br>You must set this field to `auto_rental` in order for auto rental data to be sent to the processor. For example, if this<br>field is not set to `auto_rental` or is not included in the request, no auto rental data is sent to the processor.<br><br>Restaurant data is supported only on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `20` | getIndustryDataType(): ?string | setIndustryDataType(?string industryDataType): void |
| `paymentSolution` | `?string` | Optional | Type of digital payment solution for the transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getPaymentSolution(): ?string | setPaymentSolution(?string paymentSolution): void |
| `commerceIndicator` | `?string` | Optional | Type of transaction. Some payment card companies use this information when determining discount rates.<br><br>#### Used by<br><br>**Authorization**<br>Required payer authentication transactions; otherwise, optional.<br>**Credit**<br>Required for standalone credits on Chase Paymentech solutions; otherwise, optional.<br><br>The list of valid values in this field depends on your processor.<br><br>#### Ingenico ePayments<br><br>When you omit this field for Ingenico ePayments, the processor uses the default transaction type they have on file for you instead of the default value<br><br>#### Card Present<br><br>You must set this field to `retail`. This field is required for a card-present transaction. Note that this should ONLY be<br>used when the cardholder and card are present at the time of the transaction.<br>For all keyed transactions originated from a POS terminal where the cardholder and card are not present, commerceIndicator<br>should be submitted as “moto"<br><br>**Constraints**: *Maximum Length*: `20` | getCommerceIndicator(): ?string | setCommerceIndicator(?string commerceIndicator): void |
| `commerceIndicatorLabel` | `?string` | Optional | Type of transaction. Some payment card companies use this information when determining discount rates.<br><br>#### Used by<br><br>**Authorization**<br>Required payer authentication transactions; otherwise, optional.<br>**Credit**<br>Required for standalone credits on Chase Paymentech solutions; otherwise, optional.<br><br>The list of valid values in this field depends on your processor.<br><br>#### Ingenico ePayments<br><br>When you omit this field for Ingenico ePayments, the processor uses the default transaction type they have on file for you<br>instead of the default value<br><br>#### Card Present<br><br>You must set this field to `retail`. This field is required for a card-present transaction. Note that this should ONLY be<br>used when the cardholder and card are present at the time of the transaction.<br>For all keyed transactions originated from a POS terminal where the cardholder and card are not present, commerceIndicator<br>should be submitted as `moto`<br><br>**Constraints**: *Maximum Length*: `20` | getCommerceIndicatorLabel(): ?string | setCommerceIndicatorLabel(?string commerceIndicatorLabel): void |
| `businessApplicationId` | `?string` | Optional | Required for AFT and OCT transactions.<br><br>Given below is a list of all the BAI values available. However, the processors may support only few specific BAI values.<br><br>- AA : Account-to-account<br>- BB : Supplier Payments<br>- BI : Bank-Initiated P2P Money Transfer<br>- BP : Non-Card Bill Pay/Bill Pay<br>- CD : Cash Deposit<br>- CP : Credit card Bill Payment<br>- FD : Funds disbursement<br>- FT : Funds transfer<br>- GD : Government Disbursement<br>- GP : Gambling payout (non-online gambling)<br>- LO : Loyalty credits and rebates<br>- MD : Merchant Settlement<br>- OG : Online Gambling Payout<br>- PD : Payroll and pension disbursement<br>- PP : Person-to-Person or Peer-to-Peer<br>- TU : Top up, prepaid load<br>- WT : Digital wallet | getBusinessApplicationId(): ?string | setBusinessApplicationId(?string businessApplicationId): void |
| `authorizationOptions` | [`?AuthorizationOptions6`](../../doc/models/authorization-options-6.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions6 | setAuthorizationOptions(?AuthorizationOptions6 authorizationOptions): void |
| `bankTransferOptions` | [`?BankTransferOptions21`](../../doc/models/bank-transfer-options-21.md) | Optional | - | getBankTransferOptions(): ?BankTransferOptions21 | setBankTransferOptions(?BankTransferOptions21 bankTransferOptions): void |
| `captureOptions` | [`?CaptureOptions3`](../../doc/models/capture-options-3.md) | Optional | - | getCaptureOptions(): ?CaptureOptions3 | setCaptureOptions(?CaptureOptions3 captureOptions): void |
| `reconciliationId` | `?string` | Optional | Reference number for the transaction.<br>Depending on how your Visa Acceptance account is configured, this value could either be provided in the API request or generated by Visa Acceptance.<br>The actual value used in the request to the processor is provided back to you by Visa Acceptance in the response.<br><br>**Constraints**: *Maximum Length*: `60` | getReconciliationId(): ?string | setReconciliationId(?string reconciliationId): void |
| `japanPaymentOptions` | [`?JapanPaymentOptions2`](../../doc/models/japan-payment-options-2.md) | Optional | - | getJapanPaymentOptions(): ?JapanPaymentOptions2 | setJapanPaymentOptions(?JapanPaymentOptions2 japanPaymentOptions): void |
| `validationLevel` | `?int` | Optional | Enter 1 for routing and account number validation. | getValidationLevel(): ?int | setValidationLevel(?int validationLevel): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation52Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation52 = ProcessingInformation52Builder::init()
    ->binSource('binSource6')
    ->industryDataType('industryDataType0')
    ->paymentSolution('paymentSolution8')
    ->commerceIndicator('commerceIndicator2')
    ->commerceIndicatorLabel('commerceIndicatorLabel0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

