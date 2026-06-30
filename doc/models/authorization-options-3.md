
# Authorization Options 3

*This model accepts additional fields of type array.*

## Structure

`AuthorizationOptions3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `initiator` | [`?Initiator1`](../../doc/models/initiator-1.md) | Optional | - | getInitiator(): ?Initiator1 | setInitiator(?Initiator1 initiator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationOptions3 = AuthorizationOptions3Builder::init()
    ->initiator(
        Initiator1Builder::init()
            ->storedCredentialUsed(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

