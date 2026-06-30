
# Processor Information

Processor Information

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `preApprovalToken` | `?string` | Optional | Token received in original session service.<br><br>**Constraints**: *Maximum Length*: `60` | getPreApprovalToken(): ?string | setPreApprovalToken(?string preApprovalToken): void |
| `authorizationOptions` | [`?AuthorizationOptions1`](../../doc/models/authorization-options-1.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions1 | setAuthorizationOptions(?AuthorizationOptions1 authorizationOptions): void |
| `reversal` | [`?Reversal`](../../doc/models/reversal.md) | Optional | - | getReversal(): ?Reversal | setReversal(?Reversal reversal): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ReversalBuilder;

$processorInformation = ProcessorInformationBuilder::init()
    ->preApprovalToken('preApprovalToken6')
    ->authorizationOptions(
        AuthorizationOptions1Builder::init()
            ->panReturnIndicator('panReturnIndicator8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->reversal(
        ReversalBuilder::init()
            ->preApprovalToken('preApprovalToken0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

