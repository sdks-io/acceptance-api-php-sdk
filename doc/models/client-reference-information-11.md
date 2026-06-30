
# Client Reference Information 11

*This model accepts additional fields of type array.*

## Structure

`ClientReferenceInformation11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Merchant-generated order reference or tracking number. It is recommended that you send a unique value for each<br>transaction so that you can perform meaningful searches for the transaction.<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>#### PIN Debit<br><br>Requests for PIN debit reversals need to use the same merchant reference number that was used in the transaction that is being<br>reversed.<br><br>Required field for all PIN Debit requests (purchase, credit, and reversal).<br><br>#### FDC Nashville Global<br><br>Certain circumstances can cause the processor to truncate this value to 15 or 17 characters for Level II and Level III processing, which can cause a discrepancy between the value you submit and the value included in some processor reports.<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `submitLocalDateTime` | `?string` | Optional | Date and time at your physical location.<br><br>Format: `YYYYMMDDhhmmss`, where YYYY = year, MM = month, DD = day, hh = hour, mm = minutes ss = seconds<br><br>#### PIN Debit<br><br>Optional field for PIN Debit purchase and credit requests.<br><br>**Constraints**: *Maximum Length*: `14` | getSubmitLocalDateTime(): ?string | setSubmitLocalDateTime(?string submitLocalDateTime): void |
| `ownerMerchantId` | `?string` | Optional | Merchant ID that was used to create the subscription or customer profile for which the service was requested.<br><br>If your Visa Acceptance account is enabled for Recurring Billing, this field is returned only if you are using<br>subscription sharing and if your merchant ID is in the same merchant ID pool as the owner merchant ID.<br><br>If your Visa Acceptance account is enabled for Payment Tokenization, this field is returned only if you are using<br>profile sharing and if your merchant ID is in the same merchant ID pool as the owner merchant ID. | getOwnerMerchantId(): ?string | setOwnerMerchantId(?string ownerMerchantId): void |
| `returnReconciliationId` | `?string` | Optional | A new ID which is created for refund | getReturnReconciliationId(): ?string | setReturnReconciliationId(?string returnReconciliationId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$clientReferenceInformation11 = ClientReferenceInformation11Builder::init()
    ->code('code2')
    ->submitLocalDateTime('submitLocalDateTime8')
    ->ownerMerchantId('ownerMerchantId0')
    ->returnReconciliationId('returnReconciliationId6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

