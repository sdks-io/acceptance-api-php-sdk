
# Client Reference Information 3

*This model accepts additional fields of type array.*

## Structure

`ClientReferenceInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Merchant-generated order reference or tracking number. It is recommended that you send a unique value for each<br>transaction so that you can perform meaningful searches for the transaction.<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>#### PIN Debit<br><br>Requests for PIN debit reversals need to use the same merchant reference number that was used in the transaction that is being<br>reversed.<br><br>Required field for all PIN Debit requests (purchase, credit, and reversal).<br><br>#### FDC Nashville Global<br><br>Certain circumstances can cause the processor to truncate this value to 15 or 17 characters for Level II and Level III processing, which can cause a discrepancy between the value you submit and the value included in some processor reports.<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$clientReferenceInformation3 = ClientReferenceInformation3Builder::init()
    ->code('code6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

