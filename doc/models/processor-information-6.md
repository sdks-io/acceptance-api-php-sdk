
# Processor Information 6

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionId` | `?string` | Optional | Processor transaction ID.<br><br>This value identifies the transaction on a host system. This value is supported only for Moneris. It contains<br>this information:<br><br>- Terminal used to process the transaction<br>- Shift during which the transaction took place<br>- Batch number<br>- Transaction number within the batch<br><br>You must store this value. If you give the customer a receipt, display this value on the receipt.<br><br>Example For the value 66012345001069003:<br><br>- Terminal ID = 66012345<br>- Shift number = 001<br>- Batch number = 069<br>- Transaction number = 003<br><br>**Constraints**: *Maximum Length*: `18` | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `networkTransactionId` | `?string` | Optional | Network Transaction Identifier<br>Applicable for online capture transactions only. | getNetworkTransactionId(): ?string | setNetworkTransactionId(?string networkTransactionId): void |
| `responseDetails` | `?string` | Optional | The processor code that describes why the transaction state is pending or reversed.<br><br>**Constraints**: *Maximum Length*: `60` | getResponseDetails(): ?string | setResponseDetails(?string responseDetails): void |
| `responseCode` | `?string` | Optional | For most processors, this is the error message sent directly from the bank. Returned only when the processor<br>returns this value.<br><br>**Important** Do not use this field to evaluate the result of the authorization.<br><br>#### PIN debit<br><br>Response value that is returned by the processor or bank.<br>**Important** Do not use this field to evaluate the results of the transaction request.<br><br>Returned by PIN debit credit, PIN debit purchase, and PIN debit reversal.<br><br>#### AIBMS<br><br>If this value is `08`, you can accept the transaction if the customer provides you with identification.<br><br>#### Atos<br><br>This value is the response code sent from Atos and it might also include the response code from the bank.<br>Format: `aa,bb` with the two values separated by a comma and where:<br><br>- `aa` is the two-digit error message from Atos.<br>- `bb` is the optional two-digit error message from the bank.<br><br>#### Comercio Latino<br><br>This value is the status code and the error or response code received from the processor separated by a colon.<br>Format: [status code]:E[error code] or [status code]:R[response code]<br>Example `2:R06`<br><br>#### JCN Gateway<br><br>Processor-defined detail error code. The associated response category code is in the `processorInformation.responseCategoryCode` field.<br>String (3)<br><br>#### paypalgateway<br><br>Processor generated ID for the itemized detail.<br><br>**Constraints**: *Maximum Length*: `10` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `providerResponse` | `?string` | Optional | Processor response to the API request. | getProviderResponse(): ?string | setProviderResponse(?string providerResponse): void |
| `updateTimeUtc` | `?string` | Optional | The date and time when the transaction was last updated, in Internet date and time format. | getUpdateTimeUtc(): ?string | setUpdateTimeUtc(?string updateTimeUtc): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorInformation6 = ProcessorInformation6Builder::init()
    ->transactionId('transactionId6')
    ->networkTransactionId('networkTransactionId2')
    ->responseDetails('responseDetails6')
    ->responseCode('responseCode6')
    ->providerResponse('providerResponse4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

