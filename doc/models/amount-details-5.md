
# Amount Details 5

*This model accepts additional fields of type array.*

## Structure

`AmountDetails5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | Grand total for the order. This value cannot be negative. You can include a decimal point (.), but no other special characters.<br>Visa Acceptance truncates the amount to the correct number of decimal places.<br><br>**Note** For CTV, FDCCompass, Paymentech processors, the maximum length for this field is 12.<br><br>**Important** Some processors have specific requirements and limitations, such as maximum amounts and maximum field lengths.<br><br>If your processor supports zero amount authorizations, you can set this field to 0 for the authorization to check if the card is lost or stolen.<br><br>#### Card Present<br><br>Required to include either this field or `orderInformation.lineItems[].unitPrice` for the order.<br><br>#### Invoicing / Pay By Link<br><br>Required for creating a new invoice or payment link.<br><br>#### PIN Debit<br><br>Amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount.<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit; however, for all other processors, these fields are required.<br><br>#### DCC with a Third-Party Provider<br><br>Set this field to the converted amount that was returned by the DCC provider. You must include either this field or the 1st line item in the order and the specific line-order amount in your request.<br><br>#### DCC for First Data<br><br>Not used.<br><br>**Constraints**: *Maximum Length*: `19` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `currency` | `?string` | Optional | Currency used for the order. Use the three-character [ISO Standard Currency Codes.](<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>**Authorization Reversal**<br>For an authorization reversal (`reversalInformation`) or a capture (`processingOptions.capture` is set to `true`), you must use the same currency that you used in your payment authorization request.<br><br>#### PIN Debit<br><br>Currency for the amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount. For the possible values, see the [ISO Standard Currency Codes](<br>Returned by PIN debit purchase.<br><br>For PIN debit reversal requests, you must use the same currency that was used for the PIN debit purchase or PIN debit credit that you are reversing.<br>For the possible values, see the [ISO Standard Currency Codes](<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit.<br><br>#### DCC for First Data<br><br>Your local currency.<br><br>#### Tax Calculation<br><br>Required for international tax and value added tax only.<br>Optional for U.S. and Canadian taxes.<br>Your local currency.<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails5 = AmountDetails5Builder::init()
    ->totalAmount('totalAmount8')
    ->currency('currency4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

