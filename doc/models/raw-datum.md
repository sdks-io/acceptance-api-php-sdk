
# Raw Datum

*This model accepts additional fields of type array.*

## Structure

`RawDatum`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `?string` | Optional | Field that contains the device fingerprint data from the specified provider. The value should be Base64 encoded. | getData(): ?string | setData(?string data): void |
| `provider` | `?string` | Optional | Possible values:<br><br>- cardinal<br>- inauth<br>- threatmetrix<br><br>**Constraints**: *Maximum Length*: `32` | getProvider(): ?string | setProvider(?string provider): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RawDatumBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$rawDatum = RawDatumBuilder::init()
    ->data('data4')
    ->provider('provider6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

