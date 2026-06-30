
# Client Reference Information 29

*This model accepts additional fields of type array.*

## Structure

`ClientReferenceInformation29`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Merchant-generated order reference or tracking number. It is recommended that you send a unique value for each transaction so that you can perform meaningful searches for the transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation29Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$clientReferenceInformation29 = ClientReferenceInformation29Builder::init()
    ->code('code8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

