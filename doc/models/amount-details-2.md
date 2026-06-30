
# Amount Details 2

*This model accepts additional fields of type array.*

## Structure

`AmountDetails2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | Amount you requested for the payment or capture.<br><br>This value is returned for partial authorizations.<br>This field is also returned on incremental authorizations will contain the aggregated amount from the original authorizations and all the incremental authorizations.<br><br>**Constraints**: *Maximum Length*: `15` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `authorizedAmount` | `?string` | Optional | Amount that was authorized.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Amount of the purchase.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `15` | getAuthorizedAmount(): ?string | setAuthorizedAmount(?string authorizedAmount): void |
| `currency` | `?string` | Optional | Currency used for the order. Use the three-character [ISO Standard Currency Codes.](<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>**Authorization Reversal**<br>For an authorization reversal (`reversalInformation`) or a capture (`processingOptions.capture` is set to `true`), you must use the same currency that you used in your payment authorization request.<br><br>#### PIN Debit<br><br>Currency for the amount you requested for the PIN debit purchase. This value is returned for partial authorizations. The issuing bank can approve a partial amount if the balance on the debit card is less than the requested transaction amount. For the possible values, see the [ISO Standard Currency Codes](<br>Returned by PIN debit purchase.<br><br>For PIN debit reversal requests, you must use the same currency that was used for the PIN debit purchase or PIN debit credit that you are reversing.<br>For the possible values, see the [ISO Standard Currency Codes](<br><br>Required field for PIN Debit purchase and PIN Debit credit requests.<br>Optional field for PIN Debit reversal requests.<br><br>#### GPX<br><br>This field is optional for reversing an authorization or credit.<br><br>#### DCC for First Data<br><br>Your local currency.<br><br>#### Tax Calculation<br><br>Required for international tax and value added tax only.<br>Optional for U.S. and Canadian taxes.<br>Your local currency.<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `settlementAmount` | `?string` | Optional | This is a multicurrency field. It contains the transaction amount (field 4), converted to the Currency used to bill the cardholder’s account.<br>This field is returned for OCT transactions.<br><br>**Constraints**: *Maximum Length*: `12` | getSettlementAmount(): ?string | setSettlementAmount(?string settlementAmount): void |
| `settlementCurrency` | `?string` | Optional | This is a multicurrency-only field. It contains a 3-digit numeric code that identifies the currency used by the issuer to bill the cardholder's account.<br>This field is returned for OCT transactions.<br><br>**Constraints**: *Maximum Length*: `3` | getSettlementCurrency(): ?string | setSettlementCurrency(?string settlementCurrency): void |
| `originalAmount` | `?string` | Optional | Amount in your original local pricing currency.<br><br>This value cannot be negative. You can include a decimal point (.) in this field to denote the currency<br>exponent, but you cannot include any other special characters.<br><br>If needed, Visa Acceptance truncates the amount to the correct number of decimal places.<br><br>**Constraints**: *Maximum Length*: `15` | getOriginalAmount(): ?string | setOriginalAmount(?string originalAmount): void |
| `originalCurrency` | `?string` | Optional | Your local pricing currency code.<br><br>For the possible values, see the [ISO Standard Currency Codes.](<br><br>**Constraints**: *Maximum Length*: `15` | getOriginalCurrency(): ?string | setOriginalCurrency(?string originalCurrency): void |
| `processorTransactionFee` | `?string` | Optional | Amount up to N digit after the decimals separator as defined in ISO 4217 for the appropriate currency code.<br><br>**Constraints**: *Maximum Length*: `15` | getProcessorTransactionFee(): ?string | setProcessorTransactionFee(?string processorTransactionFee): void |
| `exchangeRate` | `?string` | Optional | The rate of conversion of the currency given in the request to CNY. The conversion happens at the time when Alipay’s trade order is created<br><br>**Constraints**: *Maximum Length*: `17` | getExchangeRate(): ?string | setExchangeRate(?string exchangeRate): void |
| `foreignCurrency` | `?string` | Optional | Currency code for the transaction performed in cross border currency.<br><br>**Constraints**: *Maximum Length*: `3` | getForeignCurrency(): ?string | setForeignCurrency(?string foreignCurrency): void |
| `foreignAmount` | `?string` | Optional | The transaction amount in CNY.<br><br>**Constraints**: *Maximum Length*: `11` | getForeignAmount(): ?string | setForeignAmount(?string foreignAmount): void |
| `discountAmount` | `?string` | Optional | If coupons/vouchers are used in the transaction, the discount amount redeemed in the settlement currency will be returned. Otherwise, no return.<br><br>**Constraints**: *Maximum Length*: `11` | getDiscountAmount(): ?string | setDiscountAmount(?string discountAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails2 = AmountDetails2Builder::init()
    ->totalAmount('totalAmount4')
    ->authorizedAmount('authorizedAmount0')
    ->currency('currency0')
    ->settlementAmount('settlementAmount0')
    ->settlementCurrency('settlementCurrency8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

