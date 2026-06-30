
# Payment Information 1

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card1`](../../doc/models/card-1.md) | Optional | - | getCard(): ?Card1 | setCard(?Card1 card): void |
| `tokenizedCard` | [`?TokenizedCard1`](../../doc/models/tokenized-card-1.md) | Optional | - | getTokenizedCard(): ?TokenizedCard1 | setTokenizedCard(?TokenizedCard1 tokenizedCard): void |
| `tokenizedPaymentMethod` | [`?TokenizedPaymentMethod1`](../../doc/models/tokenized-payment-method-1.md) | Optional | - | getTokenizedPaymentMethod(): ?TokenizedPaymentMethod1 | setTokenizedPaymentMethod(?TokenizedPaymentMethod1 tokenizedPaymentMethod): void |
| `accountFeatures` | [`?AccountFeatures`](../../doc/models/account-features.md) | Optional | - | getAccountFeatures(): ?AccountFeatures | setAccountFeatures(?AccountFeatures accountFeatures): void |
| `bank` | [`?Bank1`](../../doc/models/bank-1.md) | Optional | - | getBank(): ?Bank1 | setBank(?Bank1 bank): void |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | - | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `paymentInstrument` | [`?PaymentInstrument`](../../doc/models/payment-instrument.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument | setPaymentInstrument(?PaymentInstrument paymentInstrument): void |
| `instrumentIdentifier` | [`?InstrumentIdentifier2`](../../doc/models/instrument-identifier-2.md) | Optional | - | getInstrumentIdentifier(): ?InstrumentIdentifier2 | setInstrumentIdentifier(?InstrumentIdentifier2 instrumentIdentifier): void |
| `shippingAddress` | [`?ShippingAddress`](../../doc/models/shipping-address.md) | Optional | - | getShippingAddress(): ?ShippingAddress | setShippingAddress(?ShippingAddress shippingAddress): void |
| `scheme` | `?string` | Optional | Subtype of card account. This field can contain one of the following values:<br><br>- Maestro International<br>- Maestro UK Domestic<br>- MasterCard Credit<br>- MasterCard Debit<br>- Visa Credit<br>- Visa Debit<br>- Visa Electron<br><br>**Note** Additional values may be present.<br><br>**Constraints**: *Maximum Length*: `255` | getScheme(): ?string | setScheme(?string scheme): void |
| `bin` | `?string` | Optional | Credit card BIN (the first six digits of the credit card).Derived either from the `cc_bin` request field<br>or from the first six characters of the `customer_cc_num` field.<br><br>**Constraints**: *Maximum Length*: `255` | getBin(): ?string | setBin(?string bin): void |
| `accountType` | `?string` | Optional | Type of payment card account. This field can refer to a credit card, debit card, or prepaid card<br>account type.<br><br>**Constraints**: *Maximum Length*: `255` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `issuer` | `?string` | Optional | Name of the bank or entity that issued the card account.<br><br>**Constraints**: *Maximum Length*: `255` | getIssuer(): ?string | setIssuer(?string issuer): void |
| `binCountry` | `?string` | Optional | Country (two-digit country code) associated with the BIN of the customer’s card used for the payment.<br>Returned if the information is available. Use this field for additional information when reviewing orders.<br>This information is also displayed in the details page of the Visa Acceptance Business Center.<br><br>**Constraints**: *Maximum Length*: `255` | getBinCountry(): ?string | setBinCountry(?string binCountry): void |
| `eWallet` | [`?EWallet1`](../../doc/models/e-wallet-1.md) | Optional | - | getEWallet(): ?EWallet1 | setEWallet(?EWallet1 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCard1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountFeaturesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BalanceBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account2Builder;

$paymentInformation1 = PaymentInformation1Builder::init()
    ->card(
        Card1Builder::init()
            ->suffix('suffix4')
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->type('type4')
            ->prefix('prefix4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->tokenizedCard(
        TokenizedCard1Builder::init()
            ->prefix('prefix8')
            ->suffix('suffix0')
            ->type('type0')
            ->assuranceLevel('assuranceLevel6')
            ->expirationMonth('expirationMonth0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->tokenizedPaymentMethod(
        TokenizedPaymentMethod1Builder::init()
            ->id('id0')
            ->status('status2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->accountFeatures(
        AccountFeaturesBuilder::init()
            ->accountType('accountType8')
            ->accountStatus('accountStatus6')
            ->balances(
                [
                    BalanceBuilder::init()
                        ->accountType('accountType0')
                        ->amount('amount2')
                        ->amountType('amountType2')
                        ->currency('currency0')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    BalanceBuilder::init()
                        ->accountType('accountType0')
                        ->amount('amount2')
                        ->amountType('amountType2')
                        ->currency('currency0')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    BalanceBuilder::init()
                        ->accountType('accountType0')
                        ->amount('amount2')
                        ->amountType('amountType2')
                        ->currency('currency0')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->balanceAmount('balanceAmount0')
            ->balanceAmountType('balanceAmountType8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank1Builder::init()
            ->account(
                Account2Builder::init()
                    ->correctedAccountNumber('correctedAccountNumber4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->correctedRoutingNumber('correctedRoutingNumber0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

