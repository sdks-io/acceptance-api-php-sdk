
# Processor Information 4

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionId` | `?string` | Optional | Processor transaction ID.<br><br>This value identifies the transaction on a host system. This value is supported only for Moneris. It contains<br>this information:<br><br>- Terminal used to process the transaction<br>- Shift during which the transaction took place<br>- Batch number<br>- Transaction number within the batch<br><br>You must store this value. If you give the customer a receipt, display this value on the receipt.<br><br>Example For the value 66012345001069003:<br><br>- Terminal ID = 66012345<br>- Shift number = 001<br>- Batch number = 069<br>- Transaction number = 003<br><br>**Constraints**: *Maximum Length*: `18` | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `responseCode` | `?string` | Optional | For most processors, this is the error message sent directly from the bank. Returned only when the processor<br>returns this value.<br><br>**Important** Do not use this field to evaluate the result of the authorization.<br><br>#### PIN debit<br><br>Response value that is returned by the processor or bank.<br>**Important** Do not use this field to evaluate the results of the transaction request.<br><br>Returned by PIN debit credit, PIN debit purchase, and PIN debit reversal.<br><br>#### AIBMS<br><br>If this value is `08`, you can accept the transaction if the customer provides you with identification.<br><br>#### Atos<br><br>This value is the response code sent from Atos and it might also include the response code from the bank.<br>Format: `aa,bb` with the two values separated by a comma and where:<br><br>- `aa` is the two-digit error message from Atos.<br>- `bb` is the optional two-digit error message from the bank.<br><br>#### Comercio Latino<br><br>This value is the status code and the error or response code received from the processor separated by a colon.<br>Format: [status code]:E[error code] or [status code]:R[response code]<br>Example `2:R06`<br><br>#### JCN Gateway<br><br>Processor-defined detail error code. The associated response category code is in the `processorInformation.responseCategoryCode` field.<br>String (3)<br><br>#### paypalgateway<br><br>Processor generated ID for the itemized detail.<br><br>**Constraints**: *Maximum Length*: `10` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `networkTransactionId` | `?string` | Optional | Same value as `processorInformation.transactionId` | getNetworkTransactionId(): ?string | setNetworkTransactionId(?string networkTransactionId): void |
| `responseCategoryCode` | `?string` | Optional | Processor-defined response category code. The associated detail error code is in the `processorInformation.responseCode` or `issuerInformation.responseCode`<br>field of the service you requested.<br><br>This field is supported only for:<br><br>- Japanese issuers<br>- Domestic transactions in Japan<br>- Comercio Latino—processor transaction ID required for troubleshooting<br><br>#### Maximum length for processors<br><br>- Comercio Latino: 36<br>- All other processors: 3<br><br>**Constraints**: *Maximum Length*: `36` | getResponseCategoryCode(): ?string | setResponseCategoryCode(?string responseCategoryCode): void |
| `forwardedAcquirerCode` | `?string` | Optional | Name of the Japanese acquirer that processed the transaction. Returned only for JCN Gateway.<br>Please contact the Visa Acceptance Japan Support Group for more information.<br><br>**Constraints**: *Maximum Length*: `32` | getForwardedAcquirerCode(): ?string | setForwardedAcquirerCode(?string forwardedAcquirerCode): void |
| `masterCardServiceCode` | `?string` | Optional | Mastercard service that was used for the transaction. Mastercard provides this value to Visa Acceptance.<br><br>Possible value:<br><br>- 53: Mastercard card-on-file token service<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCR6<br>- Position: 133-134<br>- Field: Mastercard Merchant on-behalf service.<br>  **Note** This field is returned only for Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `2` | getMasterCardServiceCode(): ?string | setMasterCardServiceCode(?string masterCardServiceCode): void |
| `masterCardServiceReplyCode` | `?string` | Optional | Result of the Mastercard card-on-file token service. Mastercard provides this value to Visa Acceptance.<br><br>Possible values:<br><br>- `C`: Service completed successfully.<br>- `F`: One of the following:<br>  - Incorrect Mastercard POS entry mode. The Mastercard POS entry mode should be 81 for an authorization or<br>    authorization reversal.<br>  - Incorrect Mastercard POS entry mode. The Mastercard POS entry mode should be 01 for a tokenized request.<br>  - Token requestor ID is missing or formatted incorrectly.<br>- `I`: One of the following:<br>  - Invalid token requestor ID.<br>  - Suspended or deactivated token.<br>  - Invalid token (not in mapping table).<br>- `T`: Invalid combination of token requestor ID and token.<br>- `U`: Expired token.<br>- `W`: Primary account number (PAN) listed in electronic warning bulletin.<br><br>**Note** This field is returned only for **Visa Acceptance through VisaNet**.<br><br>**Constraints**: *Maximum Length*: `1` | getMasterCardServiceReplyCode(): ?string | setMasterCardServiceReplyCode(?string masterCardServiceReplyCode): void |
| `responseDetails` | `?string` | Optional | This field might contain information about a decline. This field is supported only for **Visa Acceptance through<br>VisaNet**.<br><br>**Constraints**: *Maximum Length*: `255` | getResponseDetails(): ?string | setResponseDetails(?string responseDetails): void |
| `providerResponse` | `?string` | Optional | Processor response to the API request. | getProviderResponse(): ?string | setProviderResponse(?string providerResponse): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorInformation4 = ProcessorInformation4Builder::init()
    ->transactionId('transactionId6')
    ->responseCode('responseCode6')
    ->networkTransactionId('networkTransactionId2')
    ->responseCategoryCode('responseCategoryCode2')
    ->forwardedAcquirerCode('forwardedAcquirerCode4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

