
# Amount Details 28

*This model accepts additional fields of type array.*

## Structure

`AmountDetails28`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | Grand total for the order. This value cannot be negative. You can include a decimal point (.), but no other special characters.<br>Visa Acceptance truncates the amount to the correct number of decimal places.<br><br>**Note** For CTV, FDCCompass, Paymentech processors, the maximum length for this field is 12.<br><br>**Important** Some processors have specific requirements and limitations, such as maximum amounts and maximum field lengths.<br><br>If your processor supports zero amount authorizations, you can set this field to 0 for the authorization to check if the card is lost or stolen.<br><br>#### Card Present<br><br>Required to include either this field or `orderInformation.lineItems[].unitPrice` for the order.<br><br>#### Invoicing / Pay By Link<br><br>Required for creating a new invoice or payment link.<br><br>#### PIN Debit<br><br>Amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount.<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit; however, for all other processors, these fields are required.<br><br>#### DCC with a Third-Party Provider<br><br>Set this field to the converted amount that was returned by the DCC provider. You must include either this field or the 1st line item in the order and the specific line-order amount in your request.<br><br>#### DCC for First Data<br><br>Not used.<br><br>**Constraints**: *Maximum Length*: `19` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `currency` | `?string` | Optional | Currency used for the order. Use the three-character [ISO Standard Currency Codes.](<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>**Authorization Reversal**<br>For an authorization reversal (`reversalInformation`) or a capture (`processingOptions.capture` is set to `true`), you must use the same currency that you used in your payment authorization request.<br><br>#### PIN Debit<br><br>Currency for the amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount. For the possible values, see the [ISO Standard Currency Codes](<br>Returned by PIN debit purchase.<br><br>For PIN debit reversal requests, you must use the same currency that was used for the PIN debit purchase or PIN debit credit that you are reversing.<br>For the possible values, see the [ISO Standard Currency Codes](<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit.<br><br>#### DCC for First Data<br><br>Your local currency.<br><br>#### Tax Calculation<br><br>Required for international tax and value added tax only.<br>Optional for U.S. and Canadian taxes.<br>Your local currency.<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `discountAmount` | `?string` | Optional | Total discount amount applied to the order.<br><br>**Constraints**: *Maximum Length*: `15` | getDiscountAmount(): ?string | setDiscountAmount(?string discountAmount): void |
| `taxAmount` | `?string` | Optional | Total tax amount for all the items in the order.<br><br>**Constraints**: *Maximum Length*: `12` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `dutyAmount` | `?string` | Optional | Total charges for any import or export duties included in the order.<br><br>**Constraints**: *Maximum Length*: `15` | getDutyAmount(): ?string | setDutyAmount(?string dutyAmount): void |
| `exchangeRate` | `?string` | Optional | Exchange rate returned by the DCC service. Includes a decimal point and a maximum of 4 decimal places.<br><br>**Constraints**: *Maximum Length*: `13` | getExchangeRate(): ?string | setExchangeRate(?string exchangeRate): void |
| `exchangeRateTimeStamp` | `?string` | Optional | Time stamp for the exchange rate. This value is returned by the DCC service.<br><br>Format: `YYYYMMDD~HH:MM`  where ~ denotes a space.<br><br>**Constraints**: *Maximum Length*: `14` | getExchangeRateTimeStamp(): ?string | setExchangeRateTimeStamp(?string exchangeRateTimeStamp): void |
| `settlementCurrency` | `?string` | Optional | This is a multicurrency-only field. It contains a 3-digit numeric code that identifies the currency used by the issuer to bill the cardholder's account.<br>This field is returned for OCT transactions.<br><br>**Constraints**: *Maximum Length*: `3` | getSettlementCurrency(): ?string | setSettlementCurrency(?string settlementCurrency): void |
| `invoiceAmount` | `?string` | Optional | Invoice amount.<br><br>The invoice amount issued by the Merchant to the Cardholder, which includes VAT (excluding items such as TIPS or CASHBACK).<br>For transactions that do not have applicable Benefit Laws, the field may be entered as zeros.<br><br>This field is only applicable for Uruguay market.<br><br>Example: 100.00<br><br>Uruguay<br><br>The value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCR9<br>- Position: 7-18<br>- Field: Invoice Amount<br><br>**Constraints**: *Maximum Length*: `12` | getInvoiceAmount(): ?string | setInvoiceAmount(?string invoiceAmount): void |
| `giftwrapAmount` | `?string` | Optional | giftwrap amount (RFU).<br><br>**Constraints**: *Maximum Length*: `19` | getGiftwrapAmount(): ?string | setGiftwrapAmount(?string giftwrapAmount): void |
| `handlingAmount` | `?string` | Optional | handling amount (RFU)<br><br>**Constraints**: *Maximum Length*: `19` | getHandlingAmount(): ?string | setHandlingAmount(?string handlingAmount): void |
| `shippingAmount` | `?string` | Optional | shipping amount (RFU)<br><br>**Constraints**: *Maximum Length*: `19` | getShippingAmount(): ?string | setShippingAmount(?string shippingAmount): void |
| `shippingDiscountAmount` | `?string` | Optional | shipping discount amount (RFU)<br><br>**Constraints**: *Maximum Length*: `19` | getShippingDiscountAmount(): ?string | setShippingDiscountAmount(?string shippingDiscountAmount): void |
| `insuranceAmount` | `?string` | Optional | insurance amount (RFU)<br><br>**Constraints**: *Maximum Length*: `19` | getInsuranceAmount(): ?string | setInsuranceAmount(?string insuranceAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails28Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails28 = AmountDetails28Builder::init()
    ->totalAmount('totalAmount4')
    ->currency('currency0')
    ->discountAmount('discountAmount2')
    ->taxAmount('taxAmount8')
    ->dutyAmount('dutyAmount2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

