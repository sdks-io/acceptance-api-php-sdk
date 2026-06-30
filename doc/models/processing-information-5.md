
# Processing Information 5

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentSolution` | `?string` | Optional | Type of digital payment solution for the transaction. Possible Values:<br><br>- `visacheckout`: Visa Checkout. This value is required for Visa Checkout transactions. For details, see `payment_solution` field description in [Visa Checkout Using the REST API.](<br>- `001`: Apple Pay.<br>- `004`: Visa Acceptance In-App Solution.<br>- `005`: Masterpass. This value is required for Masterpass transactions on OmniPay Direct.<br>- `006`: Android Pay.<br>- `007`: Chase Pay.<br>- `008`: Samsung Pay.<br>- `012`: Google Pay.<br>- `013`: Visa Acceptance P2PE Decryption<br>- `014`: Mastercard credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `015`: Visa credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `027`: Click to Pay.<br><br>**Constraints**: *Maximum Length*: `12` | getPaymentSolution(): ?string | setPaymentSolution(?string paymentSolution): void |
| `reconciliationId` | `?string` | Optional | Please check with Visa Acceptance customer support to see if your merchant account is configured correctly so you<br>can include this field in your request.<br><br>* For Payouts: max length for FDCCompass is String (22).<br><br>**Constraints**: *Maximum Length*: `60` | getReconciliationId(): ?string | setReconciliationId(?string reconciliationId): void |
| `linkId` | `?string` | Optional | Value that links the current authorization request to the original authorization request. Set this value<br>to the ID that was returned in the reply message from the original authorization request.<br><br>This value is used for:<br><br>- Partial authorizations<br>- Split shipments<br><br>**Constraints**: *Maximum Length*: `26` | getLinkId(): ?string | setLinkId(?string linkId): void |
| `reportGroup` | `?string` | Optional | Attribute that lets you define custom grouping for your processor reports. This field is supported only for **Worldpay VAP**.<br><br>**Constraints**: *Maximum Length*: `25` | getReportGroup(): ?string | setReportGroup(?string reportGroup): void |
| `visaCheckoutId` | `?string` | Optional | Identifier for the **Visa Checkout** order. Visa Checkout provides a unique order ID for every transaction in<br>the Visa Checkout **callID** field.<br><br>**Constraints**: *Maximum Length*: `48` | getVisaCheckoutId(): ?string | setVisaCheckoutId(?string visaCheckoutId): void |
| `purchaseLevel` | `?string` | Optional | Set this field to 3 to indicate that the request includes Level III data.<br><br>**Constraints**: *Maximum Length*: `1` | getPurchaseLevel(): ?string | setPurchaseLevel(?string purchaseLevel): void |
| `industryDataType` | `?string` | Optional | Indicates that the transaction includes industry-specific data.<br><br>Possible Values:<br><br>- `airline`<br>- `restaurant`<br>- `lodging`<br>- `auto_rental`<br>- `transit`<br>- `healthcare_medical`<br>- `healthcare_transit`<br>- `transit`<br><br>#### Card Present, Airlines and Auto Rental<br><br>You must set this field to `airline` in order for airline data to be sent to the processor. For example, if this<br>field is not set to `airline` or is not included in the request, no airline data is sent to the processor.<br><br>You must set this field to `restaurant` in order for restaurant data to be sent to the processor. When this field<br>is not set to `restaurant` or is not included in the request, no restaurant data is sent to the processor.<br><br>You must set this field to `auto_rental` in order for auto rental data to be sent to the processor. For example, if this<br>field is not set to `auto_rental` or is not included in the request, no auto rental data is sent to the processor.<br><br>Restaurant data is supported only on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `20` | getIndustryDataType(): ?string | setIndustryDataType(?string industryDataType): void |
| `issuer` | [`?Issuer`](../../doc/models/issuer.md) | Optional | - | getIssuer(): ?Issuer | setIssuer(?Issuer issuer): void |
| `authorizationOptions` | [`?AuthorizationOptions4`](../../doc/models/authorization-options-4.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions4 | setAuthorizationOptions(?AuthorizationOptions4 authorizationOptions): void |
| `captureOptions` | [`?CaptureOptions2`](../../doc/models/capture-options-2.md) | Optional | - | getCaptureOptions(): ?CaptureOptions2 | setCaptureOptions(?CaptureOptions2 captureOptions): void |
| `loanOptions` | [`?LoanOptions`](../../doc/models/loan-options.md) | Optional | - | getLoanOptions(): ?LoanOptions | setLoanOptions(?LoanOptions loanOptions): void |
| `payByPointsIndicator` | `?bool` | Optional | Flag that indicates if the transaction is pay by points transaction<br>true: Transaction uses loyalty points<br>false: Transaction does not use loyalty points<br>Default: false | getPayByPointsIndicator(): ?bool | setPayByPointsIndicator(?bool payByPointsIndicator): void |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the capture to invoke bundled services along with capture.<br><br>Possible values :<br><br>- `AP_CAPTURE`: Use this when Alternative Payment Capture service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation5 = ProcessingInformation5Builder::init()
    ->paymentSolution('paymentSolution2')
    ->reconciliationId('reconciliationId2')
    ->linkId('linkId2')
    ->reportGroup('reportGroup0')
    ->visaCheckoutId('visaCheckoutId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

