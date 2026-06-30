
# Pts V2 Update Order Patch 201 Response

*This model accepts additional fields of type array.*

## Structure

`PtsV2UpdateOrderPatch201Response`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the submitted transaction.<br>Possible values:<br><br>- CREATED<br>- SAVED<br>- APPROVED<br>- VOIDED<br>- COMPLETED<br>- PAYER_ACTION_REQUIRED | getStatus(): ?string | setStatus(?string status): void |
| `processorInformation` | [`?ProcessorInformation22`](../../doc/models/processor-information-22.md) | Optional | - | getProcessorInformation(): ?ProcessorInformation22 | setProcessorInformation(?ProcessorInformation22 processorInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PtsV2UpdateOrderPatch201ResponseBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$ptsV2UpdateOrderPatch201Response = PtsV2UpdateOrderPatch201ResponseBuilder::init()
    ->status('COMPLETED')
    ->processorInformation(
        ProcessorInformation22Builder::init()
            ->transactionId('1234qwerty1234')
            ->networkTransactionId('123qwerty123')
            ->paymentUrl('paymentUrl0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

