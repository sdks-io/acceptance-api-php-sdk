
# Token Provisioning Information

*This model accepts additional fields of type array.*

## Structure

`TokenProvisioningInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `consumerConsentObtained` | `?bool` | Optional | Flag that indicates whether the user consented to the tokenization of their credentials. Required for card network tokenization in certain markets, such as India.<br>Possible Values:<br><br>- `true`: Consumer has consented to tokenization of their credentials.<br>- `false`: Consumer has not consented to tokenization of their credentials. | getConsumerConsentObtained(): ?bool | setConsumerConsentObtained(?bool consumerConsentObtained): void |
| `multiFactorAuthenticated` | `?bool` | Optional | Flag that indicates whether AFA (Additional Factor of Authentication) for the PAN was completed. Required for card network tokenization in certain markets, such as India.<br>Possible Values:<br><br>- `true`: Consumer has been authenticated by the issuer.<br>- `false`: Consumer has not been authenticated by the issuer. | getMultiFactorAuthenticated(): ?bool | setMultiFactorAuthenticated(?bool multiFactorAuthenticated): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenProvisioningInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenProvisioningInformation = TokenProvisioningInformationBuilder::init()
    ->consumerConsentObtained(false)
    ->multiFactorAuthenticated(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

