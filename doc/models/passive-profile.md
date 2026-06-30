
# Passive Profile

*This model accepts additional fields of type array.*

## Structure

`PassiveProfile`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The name of the profile. | getName(): ?string | setName(?string name): void |
| `decision` | `?string` | Optional | Decision returned by the profile; this field contains one of these values:<br><br>- ACCEPT<br>- REJECT<br>- REVIEW | getDecision(): ?string | setDecision(?string decision): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PassiveProfileBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$passiveProfile = PassiveProfileBuilder::init()
    ->name('name0')
    ->decision('decision8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

