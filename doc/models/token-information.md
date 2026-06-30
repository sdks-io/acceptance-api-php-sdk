
# Token Information

*This model accepts additional fields of type array.*

## Structure

`TokenInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `jti` | `?string` | Optional | TMS Transient Token, 64 hexadecimal id value representing captured payment credentials (including Sensitive Authentication Data, e.g. CVV).<br><br>**Constraints**: *Maximum Length*: `64` | getJti(): ?string | setJti(?string jti): void |
| `transientTokenJwt` | `?string` | Optional | Flex API Transient Token encoded as JWT (JSON Web Token), e.g. Flex microform or Unified Payment checkout result. | getTransientTokenJwt(): ?string | setTransientTokenJwt(?string transientTokenJwt): void |
| `paymentInstrument` | [`?PaymentInstrument1`](../../doc/models/payment-instrument-1.md) | Optional | - | getPaymentInstrument(): ?PaymentInstrument1 | setPaymentInstrument(?PaymentInstrument1 paymentInstrument): void |
| `shippingAddress` | [`?ShippingAddress1`](../../doc/models/shipping-address-1.md) | Optional | - | getShippingAddress(): ?ShippingAddress1 | setShippingAddress(?ShippingAddress1 shippingAddress): void |
| `networkTokenOption` | `?string` | Optional | Indicates whether a payment network token associated with a TMS token should be used for authorization. This field can contain one of following values:<br><br>- `ignore`: Use a tokenized card number for an authorization, even if the TMS token has an associated payment network token.<br>- `prefer`: (Default) Use an associated payment network token for an authorization if the TMS token has one; otherwise, use the tokenized card number. | getNetworkTokenOption(): ?string | setNetworkTokenOption(?string networkTokenOption): void |
| `tokenProvisioningInformation` | [`?TokenProvisioningInformation`](../../doc/models/token-provisioning-information.md) | Optional | - | getTokenProvisioningInformation(): ?TokenProvisioningInformation | setTokenProvisioningInformation(?TokenProvisioningInformation tokenProvisioningInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstrument1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress1Builder;

$tokenInformation = TokenInformationBuilder::init()
    ->jti('jti6')
    ->transientTokenJwt('transientTokenJwt4')
    ->paymentInstrument(
        PaymentInstrument1Builder::init()
            ->default(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingAddress(
        ShippingAddress1Builder::init()
            ->default(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->networkTokenOption('networkTokenOption0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

