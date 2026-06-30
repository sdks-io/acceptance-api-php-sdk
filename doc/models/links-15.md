
# Links 15

*This model accepts additional fields of type array.*

## Structure

`Links15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?MSelf`](../../doc/models/m-self.md) | Optional | - | getSelf(): ?MSelf | setSelf(?MSelf self): void |
| `updateAgreement` | [`?UpdateAgreement`](../../doc/models/update-agreement.md) | Optional | - | getUpdateAgreement(): ?UpdateAgreement | setUpdateAgreement(?UpdateAgreement updateAgreement): void |
| `revokeAgreement` | [`?RevokeAgreement`](../../doc/models/revoke-agreement.md) | Optional | - | getRevokeAgreement(): ?RevokeAgreement | setRevokeAgreement(?RevokeAgreement revokeAgreement): void |
| `status` | [`?Status`](../../doc/models/status.md) | Optional | - | getStatus(): ?Status | setStatus(?Status status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links15Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MSelfBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\UpdateAgreementBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RevokeAgreementBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\StatusBuilder;

$links15 = Links15Builder::init()
    ->self(
        MSelfBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->updateAgreement(
        UpdateAgreementBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->revokeAgreement(
        RevokeAgreementBuilder::init()
            ->href('href8')
            ->method('method0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->status(
        StatusBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

