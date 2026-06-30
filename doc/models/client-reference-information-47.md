
# Client Reference Information 47

*This model accepts additional fields of type array.*

## Structure

`ClientReferenceInformation47`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Merchant-generated order reference or tracking number. It is recommended that you send a unique value for each<br>transaction so that you can perform meaningful searches for the transaction.<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>#### PIN Debit<br><br>Requests for PIN debit reversals need to use the same merchant reference number that was used in the transaction that is being<br>reversed.<br><br>Required field for all PIN Debit requests (purchase, credit, and reversal).<br><br>#### FDC Nashville Global<br><br>Certain circumstances can cause the processor to truncate this value to 15 or 17 characters for Level II and Level III processing, which can cause a discrepancy between the value you submit and the value included in some processor reports.<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `applicationVersion` | `?string` | Optional | Version of the Visa Acceptance application or integration used for a transaction. | getApplicationVersion(): ?string | setApplicationVersion(?string applicationVersion): void |
| `applicationName` | `?string` | Optional | The name of the Connection Method client (such as Virtual Terminal or SOAP Toolkit API) that the merchant uses to send a transaction request to Visa Acceptance. | getApplicationName(): ?string | setApplicationName(?string applicationName): void |
| `applicationUser` | `?string` | Optional | The entity that is responsible for running the transaction and submitting the processing request to Visa Acceptance. This could be a person, a system, or a connection method. | getApplicationUser(): ?string | setApplicationUser(?string applicationUser): void |
| `partner` | [`?Partner16`](../../doc/models/partner-16.md) | Optional | - | getPartner(): ?Partner16 | setPartner(?Partner16 partner): void |
| `comments` | `?string` | Optional | Brief description of the order or any comment you wish to add to the order.<br><br>**Constraints**: *Maximum Length*: `255` | getComments(): ?string | setComments(?string comments): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation47Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Partner16Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$clientReferenceInformation47 = ClientReferenceInformation47Builder::init()
    ->code('code6')
    ->applicationVersion('applicationVersion8')
    ->applicationName('applicationName0')
    ->applicationUser('applicationUser0')
    ->partner(
        Partner16Builder::init()
            ->solutionId('solutionId2')
            ->thirdPartyCertificationNumber('thirdPartyCertificationNumber6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

