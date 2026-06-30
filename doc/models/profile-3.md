
# Profile 3

*This model accepts additional fields of type array.*

## Structure

`Profile3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the active profile chosen by the profile selector. If no profile selector exists,<br>the default active profile is chosen.<br><br>**Note** By default, your default profile is the active profile, or the Profile Selector chooses the active profile. Use this field<br>only if you want to specify the name of a different profile. The passed-in profile will then become the active profile.<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Profile3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$profile3 = Profile3Builder::init()
    ->name('name4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

