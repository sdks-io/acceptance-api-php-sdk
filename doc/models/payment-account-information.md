
# Payment Account Information

*This model accepts additional fields of type array.*

## Structure

`PaymentAccountInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card1`](../../doc/models/card-1.md) | Optional | - | getCard(): ?Card1 | setCard(?Card1 card): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentAccountInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentAccountInformation = PaymentAccountInformationBuilder::init()
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
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

