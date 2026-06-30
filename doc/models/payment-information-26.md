
# Payment Information 26

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType19`](../../doc/models/payment-type-19.md) | Optional | - | getPaymentType(): ?PaymentType19 | setPaymentType(?PaymentType19 paymentType): void |
| `tokenizedPaymentMethod` | [`?TokenizedPaymentMethod2`](../../doc/models/tokenized-payment-method-2.md) | Optional | - | getTokenizedPaymentMethod(): ?TokenizedPaymentMethod2 | setTokenizedPaymentMethod(?TokenizedPaymentMethod2 tokenizedPaymentMethod): void |
| `industryType` | `?string` | Optional | Indicates the industry type. Possible Values:<br><br>- “Events”<br>- "Ticketing"<br>- "Fuel"<br>- "GAMING"<br>- "DIGITAL GOODS"<br>- "TELCO"<br>- "Token Service Providers"<br>- "Gambling"<br>- "CFDs"<br>- "car rental"<br>- "hotel"<br>- "transportation"<br>- "travel package"<br>- "Cruise Line"<br>- "P2P"<br>- "Retail"<br>- "Food"<br>- "Groceries"<br>- "Ride Sharing"<br>- "Taxi"<br>- "Remittance"<br>- "Crypto"<br>- "Marketplaces" | getIndustryType(): ?string | setIndustryType(?string industryType): void |
| `eWallet` | [`?EWallet13`](../../doc/models/e-wallet-13.md) | Optional | - | getEWallet(): ?EWallet13 | setEWallet(?EWallet13 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet13Builder;

$paymentInformation26 = PaymentInformation26Builder::init()
    ->paymentType(
        PaymentType19Builder::init()
            ->name('name6')
            ->method(
                Method19Builder::init()
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->tokenizedPaymentMethod(
        TokenizedPaymentMethod2Builder::init()
            ->description('description0')
            ->usagePattern('usagePattern8')
            ->usageType('usageType0')
            ->allowMultipleTokens(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->industryType('industryType8')
    ->eWallet(
        EWallet13Builder::init()
            ->accountId('accountId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

