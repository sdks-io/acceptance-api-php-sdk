
# Merchant Initiated Transaction Object

*This model accepts additional fields of type array.*

## Structure

`MerchantInitiatedTransactionObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Reason for the merchant-initiated transaction or incremental authorization. Possible values:<br><br>- `1`: Resubmission<br>- `2`: Delayed charge<br>- `3`: Reauthorization for split shipment<br>- `4`: No show<br>- `5`: Account top up<br>  This field is required only for the five kinds of transactions in the preceding list.<br>  This field is supported only for merchant-initiated transactions and incremental authorizations.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR0<br>- Position: 160-163<br>- Field: Message Reason Code<br><br>**Constraints**: *Maximum Length*: `1` | getReason(): ?string | setReason(?string reason): void |
| `previousTransactionId` | `?string` | Optional | Network transaction identifier that was returned in the payment response field _processorInformation.transactionID_<br>in the reply message for either the original merchant-initiated payment in the series or the previous<br>merchant-initiated payment in the series.<br><br>If the current payment request includes a token instead of an account number, the following time limits apply for the value of this field:<br><br>- For a **resubmission**, the transaction ID must be less than 14 days old.<br>- For a **delayed charge** or **reauthorization**, the transaction ID must be less than 30 days old.<br><br>**NOTE**: The value for this field does not correspond to any data in the TC 33 capture file5. This field is supported<br>only for Visa transactions on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `15` | getPreviousTransactionId(): ?string | setPreviousTransactionId(?string previousTransactionId): void |
| `originalAuthorizedAmount` | `?string` | Optional | Amount of the original authorization.<br><br>This field is supported only for Apple Pay, Google Pay, and Samsung Pay transactions with Discover on FDC Nashville Global and Chase Paymentech.<br><br>**Constraints**: *Maximum Length*: `61` | getOriginalAuthorizedAmount(): ?string | setOriginalAuthorizedAmount(?string originalAuthorizedAmount): void |
| `agreementId` | `?string` | Optional | This field contains the predetermined agrement id with the merchant | getAgreementId(): ?string | setAgreementId(?string agreementId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransactionObjectBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInitiatedTransactionObject = MerchantInitiatedTransactionObjectBuilder::init()
    ->reason('reason4')
    ->previousTransactionId('previousTransactionId8')
    ->originalAuthorizedAmount('originalAuthorizedAmount2')
    ->agreementId('agreementId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

