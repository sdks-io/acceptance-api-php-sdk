
# Response Insights

*This model accepts additional fields of type array.*

## Structure

`ResponseInsights`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `category` | `?string` | Optional | Categorization of response message from processor<br><br>Possible Values:<br><br>- `ISSUER_WILL_NEVER_APPROVE`<br>- `ISSUER_CANNOT_APPROVE_AT_THIS_TIME`<br>- `ISSUER_CANNOT_APPROVE_WITH_THESE_DETAILS`<br>- `GENERIC_ERROR`<br>- `PAYMENT_INSIGHTS_INTERNAL_ERROR`<br>- `OTHERS`<br>- `PAYMENT_INSIGHTS_RESPONSE_CATEGORY_MATCH_NOT_FOUND`<br><br>**Constraints**: *Maximum Length*: `60` | getCategory(): ?string | setCategory(?string category): void |
| `categoryCode` | `?string` | Optional | Categorization Code of response message from processor<br><br>Possible Values:<br><br>- `01` : ISSUER_WILL_NEVER_APPROVE<br>- `02` : ISSUER_CANNOT_APPROVE_AT_THIS_TIME<br>- `03` : ISSUER_CANNOT_APPROVE_WITH_THESE_DETAILS<br>- `04` : GENERIC_ERROR<br>- `97` : PAYMENT_INSIGHTS_INTERNAL_ERROR<br>- `98` : OTHERS<br>- `99` : PAYMENT_INSIGHTS_RESPONSE_CATEGORY_MATCH_NOT_FOUND<br><br>**Constraints**: *Maximum Length*: `2` | getCategoryCode(): ?string | setCategoryCode(?string categoryCode): void |
| `processorRawName` | `?string` | Optional | Raw name of the processor used for the transaction processing, especially useful during acquirer swing to see<br>which processor transaction settled with<br><br>**Constraints**: *Maximum Length*: `40` | getProcessorRawName(): ?string | setProcessorRawName(?string processorRawName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ResponseInsightsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$responseInsights = ResponseInsightsBuilder::init()
    ->category('category2')
    ->categoryCode('categoryCode4')
    ->processorRawName('processorRawName4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

