
# Bill to 12

*This model accepts additional fields of type array.*

## Structure

`BillTo12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Company Name.<br><br>**Constraints**: *Maximum Length*: `87` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo12 = BillTo12Builder::init()
    ->name('name8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

