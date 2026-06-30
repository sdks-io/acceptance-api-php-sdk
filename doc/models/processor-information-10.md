
# Processor Information 10

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `responseCode` | `?string` | Optional | For most processors, this is the error message sent directly from the bank. Returned only when the processor<br>returns this value.<br><br>**Important** Do not use this field to evaluate the result of the authorization.<br><br>#### PIN debit<br><br>Response value that is returned by the processor or bank.<br>**Important** Do not use this field to evaluate the results of the transaction request.<br><br>Returned by PIN debit credit, PIN debit purchase, and PIN debit reversal.<br><br>#### AIBMS<br><br>If this value is `08`, you can accept the transaction if the customer provides you with identification.<br><br>#### Atos<br><br>This value is the response code sent from Atos and it might also include the response code from the bank.<br>Format: `aa,bb` with the two values separated by a comma and where:<br><br>- `aa` is the two-digit error message from Atos.<br>- `bb` is the optional two-digit error message from the bank.<br><br>#### Comercio Latino<br><br>This value is the status code and the error or response code received from the processor separated by a colon.<br>Format: [status code]:E[error code] or [status code]:R[response code]<br>Example `2:R06`<br><br>#### JCN Gateway<br><br>Processor-defined detail error code. The associated response category code is in the `processorInformation.responseCategoryCode` field.<br>String (3)<br><br>#### paypalgateway<br><br>Processor generated ID for the itemized detail.<br><br>**Constraints**: *Maximum Length*: `10` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `responseDetails` | `?string` | Optional | The reason for when the transaction status is Pending or Reversed.<br>Possible values:<br><br>- `PAYER_SHIPPING_UNCONFIRMED`<br>- `MULTI_CURRENCY`<br>- `RISK_REVIEW`<br>- `REGULATORY_REVIEW`<br>- `VERIFICATION_REQUIRED`<br>- `ORDER`<br>- `OTHER`<br><br>**Constraints**: *Maximum Length*: `60` | getResponseDetails(): ?string | setResponseDetails(?string responseDetails): void |
| `transactionId` | `?string` | Optional | Identifier of the order transaction. | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorInformation10 = ProcessorInformation10Builder::init()
    ->responseCode('responseCode0')
    ->responseDetails('responseDetails0')
    ->transactionId('transactionId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

