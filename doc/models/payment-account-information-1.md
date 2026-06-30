
# Payment Account Information 1

*This model accepts additional fields of type array.*

## Structure

`PaymentAccountInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card15`](../../doc/models/card-15.md) | Optional | - | getCard(): ?Card15 | setCard(?Card15 card): void |
| `features` | [`?Features`](../../doc/models/features.md) | Optional | - | getFeatures(): ?Features | setFeatures(?Features features): void |
| `network` | [`?Network`](../../doc/models/network.md) | Optional | - | getNetwork(): ?Network | setNetwork(?Network network): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentAccountInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FeaturesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\NetworkBuilder;

$paymentAccountInformation1 = PaymentAccountInformation1Builder::init()
    ->card(
        Card15Builder::init()
            ->type('type4')
            ->brandName('brandName8')
            ->currency('currency6')
            ->maxLength('maxLength4')
            ->credentialType('credentialType4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->features(
        FeaturesBuilder::init()
            ->accountFundingSource('accountFundingSource0')
            ->accountFundingSourceSubType('accountFundingSourceSubType6')
            ->cardProduct('cardProduct8')
            ->messageType('messageType6')
            ->acceptanceLevel('acceptanceLevel8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->network(
        NetworkBuilder::init()
            ->id('id4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

