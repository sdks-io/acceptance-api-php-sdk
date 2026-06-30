
# Agreement Information 5

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreementId` | `?string` | Optional | The identifier for the billing agreement. | getAgreementId(): ?string | setAgreementId(?string agreementId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation5 = AgreementInformation5Builder::init()
    ->agreementId('agreementId6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

