
# Tms Bin Lookup

Bin Information of the PAN provided by BinLookUp Service. This is only retrieved when retrieveBinDetails=true is passed as a query parameter.

*This model accepts additional fields of type array.*

## Structure

`TmsBinLookup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentAccountInformation` | [`?PaymentAccountInformation1`](../../doc/models/payment-account-information-1.md) | Optional | - | getPaymentAccountInformation(): ?PaymentAccountInformation1 | setPaymentAccountInformation(?PaymentAccountInformation1 paymentAccountInformation): void |
| `issuerInformation` | [`?IssuerInformation6`](../../doc/models/issuer-information-6.md) | Optional | - | getIssuerInformation(): ?IssuerInformation6 | setIssuerInformation(?IssuerInformation6 issuerInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TmsBinLookupBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentAccountInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FeaturesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\NetworkBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation6Builder;

$tmsBinLookup = TmsBinLookupBuilder::init()
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
    ->build();
```

