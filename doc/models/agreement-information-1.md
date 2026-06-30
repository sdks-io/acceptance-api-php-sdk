
# Agreement Information 1

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreementId` | `?string` | Optional | Value of the returned in the billing agreement service response.<br><br>**Constraints**: *Maximum Length*: `50` | getAgreementId(): ?string | setAgreementId(?string agreementId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation1 = AgreementInformation1Builder::init()
    ->agreementId('agreementId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

