
# Profile 2

*This model accepts additional fields of type array.*

## Structure

`Profile2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The name of the profile. | getName(): ?string | setName(?string name): void |
| `decision` | `?string` | Optional | Decision returned by the profile; this field contains one of these values:<br><br>- ACCEPT<br>- REJECT<br>- REVIEW | getDecision(): ?string | setDecision(?string decision): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Profile2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$profile2 = Profile2Builder::init()
    ->name('name8')
    ->decision('decision6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

