
# Reversal Amount Details

*This model accepts additional fields of type array.*

## Structure

`ReversalAmountDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reversedAmount` | `?string` | Optional | Total reversed amount.<br><br>Returned by authorization reversal.<br><br>**Constraints**: *Maximum Length*: `15` | getReversedAmount(): ?string | setReversedAmount(?string reversedAmount): void |
| `originalTransactionAmount` | `?string` | Optional | Amount of the original transaction.<br><br>Returned by authorization reversal and void.<br><br>**Constraints**: *Maximum Length*: `15` | getOriginalTransactionAmount(): ?string | setOriginalTransactionAmount(?string originalTransactionAmount): void |
| `currency` | `?string` | Optional | Currency used for the order. Use the three-character [ISO Standard Currency Codes.](<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>**Authorization Reversal**<br>For an authorization reversal (`reversalInformation`) or a capture (`processingOptions.capture` is set to `true`), you must use the same currency that you used in your payment authorization request.<br><br>#### PIN Debit<br><br>Currency for the amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount. For the possible values, see the [ISO Standard Currency Codes](<br>Returned by PIN debit purchase.<br><br>For PIN debit reversal requests, you must use the same currency that was used for the PIN debit purchase or PIN debit credit that you are reversing.<br>For the possible values, see the [ISO Standard Currency Codes](<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit.<br><br>#### DCC for First Data<br><br>Your local currency.<br><br>#### Tax Calculation<br><br>Required for international tax and value added tax only.<br>Optional for U.S. and Canadian taxes.<br>Your local currency.<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ReversalAmountDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$reversalAmountDetails = ReversalAmountDetailsBuilder::init()
    ->reversedAmount('reversedAmount2')
    ->originalTransactionAmount('originalTransactionAmount2')
    ->currency('currency2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

