
# Issuer Information 1

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exemptionDataRaw` | `?string` | Optional | Payer authentication exemption indicator for Carte Bancaire exemptions.<br>This is used with unbundled authentication and authorizations calls, for example: "low fraud merchant program".<br>The value for this field maps to the value returned in the payer authentication API response field -<br>`consumerAuthenticationInformation.exemptionDataRaw`.<br><br>**Constraints**: *Maximum Length*: `4` | getExemptionDataRaw(): ?string | setExemptionDataRaw(?string exemptionDataRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation1 = IssuerInformation1Builder::init()
    ->exemptionDataRaw('exemptionDataRaw0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

