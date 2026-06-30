
# Agreement Information 10

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `indicator` | `?string` | Optional | Indicates whether the transaction is a billing<br>agreement. Possible values<br><br>- true<br>- false (default) | getIndicator(): ?string | setIndicator(?string indicator): void |
| `description` | `?string` | Optional | Description of the billing agreement | getDescription(): ?string | setDescription(?string description): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation10 = AgreementInformation10Builder::init()
    ->indicator('indicator2')
    ->description('description2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

