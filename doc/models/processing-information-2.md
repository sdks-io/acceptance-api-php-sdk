
# Processing Information 2

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorizationOptions` | [`?AuthorizationOptions3`](../../doc/models/authorization-options-3.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions3 | setAuthorizationOptions(?AuthorizationOptions3 authorizationOptions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation2 = ProcessingInformation2Builder::init()
    ->authorizationOptions(
        AuthorizationOptions3Builder::init()
            ->initiator(
                Initiator1Builder::init()
                    ->storedCredentialUsed(false)
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

