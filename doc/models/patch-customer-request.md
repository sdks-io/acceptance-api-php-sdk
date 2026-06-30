
# Patch Customer Request

*This model accepts additional fields of type array.*

## Structure

`PatchCustomerRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links19`](../../doc/models/links-19.md) | Optional, Read-only | - | getLinks(): ?Links19 | setLinks(?Links19 links): void |
| `id` | `?string` | Optional | The Id of the Customer Token.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `objectInformation` | [`?ObjectInformation`](../../doc/models/object-information.md) | Optional | - | getObjectInformation(): ?ObjectInformation | setObjectInformation(?ObjectInformation objectInformation): void |
| `buyerInformation` | [`?BuyerInformation12`](../../doc/models/buyer-information-12.md) | Optional | - | getBuyerInformation(): ?BuyerInformation12 | setBuyerInformation(?BuyerInformation12 buyerInformation): void |
| `clientReferenceInformation` | [`?ClientReferenceInformation42`](../../doc/models/client-reference-information-42.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation42 | setClientReferenceInformation(?ClientReferenceInformation42 clientReferenceInformation): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation7[])`](../../doc/models/merchant-defined-information-7.md) | Optional | Object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `defaultPaymentInstrument` | [`?DefaultPaymentInstrument`](../../doc/models/default-payment-instrument.md) | Optional | - | getDefaultPaymentInstrument(): ?DefaultPaymentInstrument | setDefaultPaymentInstrument(?DefaultPaymentInstrument defaultPaymentInstrument): void |
| `defaultShippingAddress` | [`?DefaultShippingAddress`](../../doc/models/default-shipping-address.md) | Optional | - | getDefaultShippingAddress(): ?DefaultShippingAddress | setDefaultShippingAddress(?DefaultShippingAddress defaultShippingAddress): void |
| `metadata` | [`?Metadata`](../../doc/models/metadata.md) | Optional, Read-only | - | getMetadata(): ?Metadata | setMetadata(?Metadata metadata): void |
| `embedded` | [`?Embedded4`](../../doc/models/embedded-4.md) | Optional, Read-only | - | getEmbedded(): ?Embedded4 | setEmbedded(?Embedded4 embedded): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PatchCustomerRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrumentsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ObjectInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation42Builder;

$patchCustomerRequest = PatchCustomerRequestBuilder::init()
    ->links(
        Links19Builder::init()
            ->self(
                Self18Builder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->paymentInstruments(
                PaymentInstrumentsBuilder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->shippingAddress(
                ShippingAddress11Builder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->id('id8')
    ->objectInformation(
        ObjectInformationBuilder::init()
            ->title('title0')
            ->comment('comment8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->buyerInformation(
        BuyerInformation12Builder::init()
            ->merchantCustomerId('merchantCustomerID6')
            ->email('email6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->clientReferenceInformation(
        ClientReferenceInformation42Builder::init()
            ->code('code4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

