
# Agency

*This model accepts additional fields of type array.*

## Structure

`Agency`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | International Air Transport Association (IATA) code of travel agency that made the vehicle rental reservation.<br><br>**Constraints**: *Maximum Length*: `8` | getCode(): ?string | setCode(?string code): void |
| `name` | `?string` | Optional | Name of travel agency that made the reservation.<br><br>**Constraints**: *Maximum Length*: `25` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgencyBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agency = AgencyBuilder::init()
    ->code('code4')
    ->name('name6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

