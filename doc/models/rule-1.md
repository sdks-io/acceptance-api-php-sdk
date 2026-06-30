
# Rule 1

Names of one or more rules that were processed, and the decisions made by the rules.

*This model accepts additional fields of type array.*

## Structure

`Rule1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Description of the rule as it appears in the Profile Editor.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `decision` | `?string` | Optional | Summarizes the result for the rule according to the setting that you chose in the Profile Editor.<br>This field can contain one of the following values:<br><br>- `IGNORE`<br>- `REVIEW`<br>- `REJECT`<br>- `ACCEPT`<br><br>**Constraints**: *Maximum Length*: `255` | getDecision(): ?string | setDecision(?string decision): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Rule1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$rule1 = Rule1Builder::init()
    ->name('name2')
    ->decision('decision0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

