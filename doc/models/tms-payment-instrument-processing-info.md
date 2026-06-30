
# Tms Payment Instrument Processing Info

*This model accepts additional fields of type array.*

## Structure

`TmsPaymentInstrumentProcessingInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billPaymentProgramEnabled` | `?bool` | Optional | Flag that indicates that this is a payment for a bill or for an existing contractual loan.<br>Possible Values:<br><br>- `true`: Bill payment or loan payment.<br>- `false` (default): Not a bill payment or loan payment.<br><br># For processor-specific details, see the `bill_payment` field description in [Credit Card Services Using the SCMP API.]( | getBillPaymentProgramEnabled(): ?bool | setBillPaymentProgramEnabled(?bool billPaymentProgramEnabled): void |
| `bankTransferOptions` | [`?BankTransferOptions4`](../../doc/models/bank-transfer-options-4.md) | Optional | - | getBankTransferOptions(): ?BankTransferOptions4 | setBankTransferOptions(?BankTransferOptions4 bankTransferOptions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TmsPaymentInstrumentProcessingInfoBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tmsPaymentInstrumentProcessingInfo = TmsPaymentInstrumentProcessingInfoBuilder::init()
    ->billPaymentProgramEnabled(false)
    ->bankTransferOptions(
        BankTransferOptions4Builder::init()
            ->secCode('SECCode6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

