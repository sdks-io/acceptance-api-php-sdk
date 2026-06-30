
# Payment Information 16

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation16`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card7`](../../doc/models/card-7.md) | Optional | - | getCard(): ?Card7 | setCard(?Card7 card): void |
| `tokenizedCard` | [`?TokenizedCard5`](../../doc/models/tokenized-card-5.md) | Optional | - | getTokenizedCard(): ?TokenizedCard5 | setTokenizedCard(?TokenizedCard5 tokenizedCard): void |
| `paymentType` | [`?PaymentType13`](../../doc/models/payment-type-13.md) | Optional | - | getPaymentType(): ?PaymentType13 | setPaymentType(?PaymentType13 paymentType): void |
| `bank` | [`?Bank7`](../../doc/models/bank-7.md) | Optional | - | getBank(): ?Bank7 | setBank(?Bank7 bank): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCard5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account9Builder;

$paymentInformation16 = PaymentInformation16Builder::init()
    ->card(
        Card7Builder::init()
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->number('number6')
            ->securityCode('securityCode2')
            ->type('type4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->tokenizedCard(
        TokenizedCard5Builder::init()
            ->cryptogram('cryptogram0')
            ->expirationMonth('expirationMonth0')
            ->expirationYear('expirationYear4')
            ->number('number2')
            ->transactionType('transactionType4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentType(
        PaymentType13Builder::init()
            ->method(
                Method13Builder::init()
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank7Builder::init()
            ->account(
                Account9Builder::init()
                    ->number('number8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->iban('iban2')
            ->swiftCode('swiftCode0')
            ->scheme('scheme8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

