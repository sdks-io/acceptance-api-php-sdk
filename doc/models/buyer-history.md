
# Buyer History

*This model accepts additional fields of type array.*

## Structure

`BuyerHistory`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerAccount` | [`?CustomerAccount`](../../doc/models/customer-account.md) | Optional | - | getCustomerAccount(): ?CustomerAccount | setCustomerAccount(?CustomerAccount customerAccount): void |
| `accountHistory` | [`?AccountHistory`](../../doc/models/account-history.md) | Optional | - | getAccountHistory(): ?AccountHistory | setAccountHistory(?AccountHistory accountHistory): void |
| `accountPurchases` | `?int` | Optional | Number of purchases with this cardholder account during the previous six months.<br>Recommended for Discover ProtectBuy. | getAccountPurchases(): ?int | setAccountPurchases(?int accountPurchases): void |
| `addCardAttempts` | `?int` | Optional | Number of add card attempts in the last 24 hours.<br>Recommended for Discover ProtectBuy. | getAddCardAttempts(): ?int | setAddCardAttempts(?int addCardAttempts): void |
| `priorSuspiciousActivity` | `?bool` | Optional | Indicates whether the merchant experienced suspicious activity (including previous fraud) on the account.<br>Recommended for Discover ProtectBuy. | getPriorSuspiciousActivity(): ?bool | setPriorSuspiciousActivity(?bool priorSuspiciousActivity): void |
| `paymentAccountHistory` | `?string` | Optional | This only applies for NEW_ACCOUNT and EXISTING_ACCOUNT in creationHistory. Possible values are:<br><br>- PAYMENT_ACCOUNT_EXISTS<br>- PAYMENT_ACCOUNT_ADDED_NOW | getPaymentAccountHistory(): ?string | setPaymentAccountHistory(?string paymentAccountHistory): void |
| `paymentAccountDate` | `?int` | Optional | Date applicable only for PAYMENT_ACCOUNT_EXISTS in paymentAccountHistory | getPaymentAccountDate(): ?int | setPaymentAccountDate(?int paymentAccountDate): void |
| `transactionCountDay` | `?int` | Optional | Number of transaction (successful or abandoned) for this cardholder account within the last 24 hours.<br>Recommended for Discover ProtectBuy. | getTransactionCountDay(): ?int | setTransactionCountDay(?int transactionCountDay): void |
| `transactionCountYear` | `?int` | Optional | Number of transaction (successful or abandoned) for this cardholder account within the last year.<br>Recommended for Discover ProtectBuy. | getTransactionCountYear(): ?int | setTransactionCountYear(?int transactionCountYear): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerHistoryBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerAccountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountHistoryBuilder;

$buyerHistory = BuyerHistoryBuilder::init()
    ->customerAccount(
        CustomerAccountBuilder::init()
            ->lastChangeDate('lastChangeDate8')
            ->creationHistory('creationHistory6')
            ->modificationHistory('modificationHistory0')
            ->passwordHistory('passwordHistory6')
            ->createDate('createDate2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->accountHistory(
        AccountHistoryBuilder::init()
            ->firstUseOfShippingAddress(false)
            ->shippingAddressUsageDate('shippingAddressUsageDate0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->accountPurchases(26)
    ->addCardAttempts(170)
    ->priorSuspiciousActivity(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

