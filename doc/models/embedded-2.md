
# Embedded 2

*This model accepts additional fields of type array.*

## Structure

`Embedded2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `binLookup` | [`?BinLookup`](../../doc/models/bin-lookup.md) | Optional, Read-only | - | getBinLookup(): ?BinLookup | setBinLookup(?BinLookup binLookup): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Embedded2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BinLookupBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentAccountInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FeaturesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\NetworkBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation6Builder;

$embedded2 = Embedded2Builder::init()
    ->binLookup(
        BinLookupBuilder::init()
            ->paymentAccountInformation(
                PaymentAccountInformation1Builder::init()
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
                    ->build()
            )
            ->issuerInformation(
                IssuerInformation6Builder::init()
                    ->name('name8')
                    ->country('country2')
                    ->binLength('binLength8')
                    ->accountPrefix('accountPrefix6')
                    ->phoneNumber('phoneNumber2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

