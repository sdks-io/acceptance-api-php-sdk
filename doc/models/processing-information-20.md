
# Processing Information 20

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `commerceIndicator` | `?string` | Optional | Type of transaction. Used to determine fees based on channel.<br><br>Possible values:<br><br>- aesk: American Express SafeKey authentication was successful.<br>- aesk_attempted: American Express SafeKey authentication was attempted but did not succeed. • install: Installment payment.<br>- install_internet: Non-U.S. e-commerce (Internet) installment payment. This value is supported only on Visa Platform Connect.<br>- internet (default for authorizations): E-commerce order placed using a web site.<br>- js: JCB J/Secure authentication was successful.<br>- js_attempted: JCB J/Secure authentication was attempted but did not succeed.<br>- moto: Mail order or telephone order.<br>- moto_cc: Mail order or telephone order from a call center. This value is supported only on the Asia, Middle East, and Africa Gateway.<br>- pb: ProtectBuy authentication was successful.<br>- pb_attempted: ProtectBuy authentication was attempted but did not succeed.<br>- recurring: Recurring payment that is a U.S. transaction or non-U.S. mail order / telephone order (MOTO) transaction.<br>- recurring_internet: Recurring payment that is a non-U.S. e-commerce (Internet) transaction.<br>- retail: Card-present transaction.<br>- spa: For Mastercard Identity Check: Authentication was successful or was attempted but did not succeed. The e-commerce indicator for all Mastercard Identity Check transactions, including authentication attempts, must be set to spa.<br>- spa_attempted: Authentication for a co-badged Mastercard and Cartes Bancaires card was attempted but did not succeed.<br>- spa_failure: – For Mastercard Identity Check: Authentication failed. This value is supported only on Elavon, HSBC, and Streamline.<br>- vbv: – For Visa Secure: Authentication was successful.<br>- vbv_attempted: – For Visa Secure: Authentication was attempted but did not succeed.<br>- vbv_failure: – For Visa Secure: Authentication failed. This value is supported only on HSBC and Streamline.<br><br>**Constraints**: *Maximum Length*: `20` | getCommerceIndicator(): ?string | setCommerceIndicator(?string commerceIndicator): void |
| `actionList` | `?(string[])` | Optional | - Use `CONSUMER_AUTHENTICATION` to use Payer Authentication along with Decision Manager. For any other value, only Decision Manager will run.<br>- Use `WATCHLIST_SCREENING`  when you want to call Watchlist Screening service.<br>- Use `BILLING_AGREEMENT_CREATE` when Paypal billing agreements service is requested.<br>- Use `UPDATE_AGREEMENT`<br>- Use `CANCEL_AGREEMENT`<br>- Use `AP_UPDATE_AGREEMENT` when Alternative Payment update mandate service is requested.<br>- Use `AP_CANCEL_AGREEMENT` when Alternative Payment revoke mandate service is requested.<br>- Use `AP_REFRESH_AGREEMENT_STATUS` when Alternative Payment mandate status service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation20Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation20 = ProcessingInformation20Builder::init()
    ->commerceIndicator('commerceIndicator6')
    ->actionList(
        [
            'actionList5',
            'actionList6'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

