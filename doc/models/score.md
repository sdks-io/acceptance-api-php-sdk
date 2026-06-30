
# Score

*This model accepts additional fields of type array.*

## Structure

`Score`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `factorCodes` | `?(string[])` | Optional | - | getFactorCodes(): ?array | setFactorCodes(?array factorCodes): void |
| `modelUsed` | `?string` | Optional | Name of the score model used for the transaction. If you did not include a custom model in your request,<br>this field contains the name of Visa Acceptance’s default model.<br><br>For all possible values, see the `score_model_used` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getModelUsed(): ?string | setModelUsed(?string modelUsed): void |
| `result` | `?string` | Optional | Total score calculated for this order. The value cannot be negative.<br><br>For all possible values, see the `score_score_result` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getResult(): ?string | setResult(?string result): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ScoreBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$score = ScoreBuilder::init()
    ->factorCodes(
        [
            'factorCodes4',
            'factorCodes5',
            'factorCodes6'
        ]
    )
    ->modelUsed('modelUsed0')
    ->result('result6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

