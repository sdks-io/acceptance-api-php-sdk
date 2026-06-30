
# Rule

*This model accepts additional fields of type array.*

## Structure

`Rule`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Description of the rule as it appears in the Profile Editor.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `decision` | `?string` | Optional | Summarizes the result for the rule according to the setting that you chose in the Profile Editor.<br>This field can contain one of the following values:<br><br>- `IGNORE`<br>- `REVIEW`<br>- `REJECT`<br>- `ACCEPT`<br><br>**Constraints**: *Maximum Length*: `255` | getDecision(): ?string | setDecision(?string decision): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RuleBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$rule = RuleBuilder::init()
    ->name('name0')
    ->decision('decision2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

