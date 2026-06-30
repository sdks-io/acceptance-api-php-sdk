
# Client Reference Information 42

*This model accepts additional fields of type array.*

## Structure

`ClientReferenceInformation42`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Client-generated order reference or tracking number.<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation42Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$clientReferenceInformation42 = ClientReferenceInformation42Builder::init()
    ->code('code6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

