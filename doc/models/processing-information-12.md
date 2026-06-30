
# Processing Information 12

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankTransferOptions` | [`?BankTransferOptions3`](../../doc/models/bank-transfer-options-3.md) | Optional | - | getBankTransferOptions(): ?BankTransferOptions3 | setBankTransferOptions(?BankTransferOptions3 bankTransferOptions): void |
| `enhancedDataEnabled` | `?bool` | Optional | The possible values for the reply field are:<br><br>- `true` : the airline data was included in the request to the processor.<br>- `false` : the airline data was not included in the request to the processor.<br><br>Returned by authorization, capture, or credit services. | getEnhancedDataEnabled(): ?bool | setEnhancedDataEnabled(?bool enhancedDataEnabled): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation12 = ProcessingInformation12Builder::init()
    ->bankTransferOptions(
        BankTransferOptions3Builder::init()
            ->settlementMethod('settlementMethod4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->enhancedDataEnabled(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

