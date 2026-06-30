
# Processing Information 3

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentSolution` | `?string` | Optional | Type of digital payment solution for the transaction. Possible Values:<br><br>- `visacheckout`: Visa Checkout. This value is required for Visa Checkout transactions. For details, see `payment_solution` field description in [Visa Checkout Using the REST API.](<br>- `001`: Apple Pay.<br>- `004`: Visa Acceptance In-App Solution.<br>- `005`: Masterpass. This value is required for Masterpass transactions on OmniPay Direct.<br>- `006`: Android Pay.<br>- `007`: Chase Pay.<br>- `008`: Samsung Pay.<br>- `012`: Google Pay.<br>- `013`: Visa Acceptance P2PE Decryption<br>- `014`: Mastercard credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `015`: Visa credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `027`: Click to Pay.<br><br>**Constraints**: *Maximum Length*: `12` | getPaymentSolution(): ?string | setPaymentSolution(?string paymentSolution): void |
| `reconciliationId` | `?string` | Optional | Please check with Visa Acceptance customer support to see if your merchant account is configured correctly so you<br>can include this field in your request.<br><br>* For Payouts: max length for FDCCompass is String (22).<br><br>**Constraints**: *Maximum Length*: `60` | getReconciliationId(): ?string | setReconciliationId(?string reconciliationId): void |
| `linkId` | `?string` | Optional | Value that links the current authorization request to the original authorization request. Set this value<br>to the ID that was returned in the reply message from the original authorization request.<br><br>This value is used for:<br><br>- Partial authorizations<br>- Split shipments<br><br>**Constraints**: *Maximum Length*: `26` | getLinkId(): ?string | setLinkId(?string linkId): void |
| `reportGroup` | `?string` | Optional | Attribute that lets you define custom grouping for your processor reports. This field is supported only for **Worldpay VAP**.<br><br>**Constraints**: *Maximum Length*: `25` | getReportGroup(): ?string | setReportGroup(?string reportGroup): void |
| `visaCheckoutId` | `?string` | Optional | Identifier for the **Visa Checkout** order. Visa Checkout provides a unique order ID for every transaction in<br>the Visa Checkout **callID** field.<br><br>**Constraints**: *Maximum Length*: `48` | getVisaCheckoutId(): ?string | setVisaCheckoutId(?string visaCheckoutId): void |
| `issuer` | [`?Issuer`](../../doc/models/issuer.md) | Optional | - | getIssuer(): ?Issuer | setIssuer(?Issuer issuer): void |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the reversal<br>Possible value:<br><br>- `AP_AUTH_REVERSAL`: Use this when you want to reverse an Alternative Payment Authorization. | getActionList(): ?array | setActionList(?array actionList): void |
| `transactionTypeIndicator` | `?string` | Optional | This field is used identify the type of payment transaction taking place. This field is applicable for MasterCard transactions only.<br>Possible values:<br><br>- 201- Mastercard Rebate<br>- 202- rePower Load Value<br>- 203- Gaming Re-pay<br>- 204- General Person-to-Person<br>- 205- General Transfer to Own Account<br>- 206- Agent Cash Out<br>- 207- Payment of Own Credit Card Bill<br>- 208- Business Disbursement<br>- 209- Government/Non-Profit Disbursement<br>- 210- Rapid Merchant Settlement<br>- 211- Cash in at ATM (Usage limited to specific countries)<br>- 212- Cash in at Point of Sale (Usage limited to specific countries)<br>- 213- General Business to Business Transfer<br>- 214- Mastercard Merchant Presented QR<br>- 215- Mastercard Merchant Presented QR Refund Payment<br>- 216- Utility Payments (for Brazil domestic use only)<br>- 217- Government Services (for Brazil domestic use only)<br>- 218- Mobile phone top-ups (for Brazil domestic use only)<br>- 219- Coupon booklet payments (for Brazil domestic use only)<br>- 220- General Person-to-Person Transfer<br>- 221- Person-to-Person Transfer to Card Account<br>- 222- General Transfer to Own Account<br>- 223- Agent Cash Out<br>- 224- Payment of Own Credit Card Bill<br>- 225- Business Disbursement<br>- 226- Transfer to Own Staged Digital Wallet Account<br>- 227- Transfer to Own Debit or Prepaid Account<br>- 228- General Business-to-Business Transfer<br>- 229- Installment-based repayment<br>- 230- Mastercard ATM Cash Pick-Up Transaction<br>- 231- Cryptocurrency<br>- 232- High-risk Securities<br><br>**Constraints**: *Maximum Length*: `3` | getTransactionTypeIndicator(): ?string | setTransactionTypeIndicator(?string transactionTypeIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation3 = ProcessingInformation3Builder::init()
    ->paymentSolution('paymentSolution6')
    ->reconciliationId('reconciliationId6')
    ->linkId('linkId8')
    ->reportGroup('reportGroup4')
    ->visaCheckoutId('visaCheckoutId4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

