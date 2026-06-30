
# Profile 1

*This model accepts additional fields of type array.*

## Structure

`Profile1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the active profile chosen by the profile selector. If no profile selector exists,<br>the default active profile is chosen.<br><br>**Note** By default, your default profile is the active profile, or the Profile Selector chooses the active profile. Use this field<br>only if you want to specify the name of a different profile. The passed-in profile will then become the active profile.<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `desinationQueue` | `?string` | Optional | Name of the queue where orders that are not automatically accepted are sent.<br><br>**Constraints**: *Maximum Length*: `255` | getDesinationQueue(): ?string | setDesinationQueue(?string desinationQueue): void |
| `selectorRule` | `?string` | Optional | Name of the profile selector rule that chooses the profile to use for the<br>transaction. If no profile selector exists, the value is Default Active Profile.<br><br>**Constraints**: *Maximum Length*: `255` | getSelectorRule(): ?string | setSelectorRule(?string selectorRule): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Profile1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$profile1 = Profile1Builder::init()
    ->name('name2')
    ->desinationQueue('desinationQueue8')
    ->selectorRule('selectorRule0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

