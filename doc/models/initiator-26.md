
# Initiator 26

*This model accepts additional fields of type array.*

## Structure

`Initiator26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | This field indicates whether the transaction is a merchant-initiated transaction or customer-initiated transaction.<br><br>Valid values:<br><br>- **customer**<br>- **merchant** | getType(): ?string | setType(?string type): void |
| `credentialStoredOnFile` | `?string` | Optional | Indicates to the issuing bank two things:<br><br>- The merchant has received consent from the cardholder to store their card details on file<br>- The merchant wants the issuing bank to check out the card details before the merchant initiates their first transaction for this cardholder.<br>  The purpose of the merchant-initiated transaction is to ensure that the cardholder’s credentials are valid (that the card is not stolen or has restrictions) and that the card details are good to be stored on the merchant’s file for future transactions.<br><br>Valid values:<br><br>- `Y` means merchant will use this transaction to store payment credentials for follow-up merchant-initiated transactions.<br>- `N` means merchant will not use this transaction to store payment credentials for follow-up merchant-initiated transactions.<br><br>**NOTE:** The value for this field does not correspond to any data in the TC 33 capture file5.<br><br>This field is supported only for Visa transactions on Visa Acceptance through VisaNet. | getCredentialStoredOnFile(): ?string | setCredentialStoredOnFile(?string credentialStoredOnFile): void |
| `storedCredentialUsed` | `?string` | Optional | Indicates to an issuing bank whether a merchant-initiated transaction came from a card that was already stored on file.<br><br>Possible values:<br><br>- **Y** means the merchant-initiated transaction came from a card that was already stored on file.<br>- **N**  means the merchant-initiated transaction came from a card that was not stored on file. | getStoredCredentialUsed(): ?string | setStoredCredentialUsed(?string storedCredentialUsed): void |
| `merchantInitiatedTransaction` | [`?MerchantInitiatedTransactionObject`](../../doc/models/merchant-initiated-transaction-object.md) | Optional | - | getMerchantInitiatedTransaction(): ?MerchantInitiatedTransactionObject | setMerchantInitiatedTransaction(?MerchantInitiatedTransactionObject merchantInitiatedTransaction): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransactionObjectBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$initiator26 = Initiator26Builder::init()
    ->type('type2')
    ->credentialStoredOnFile('credentialStoredOnFile2')
    ->storedCredentialUsed('storedCredentialUsed6')
    ->merchantInitiatedTransaction(
        MerchantInitiatedTransactionObjectBuilder::init()
            ->reason('reason4')
            ->previousTransactionId('previousTransactionId8')
            ->originalAuthorizedAmount('originalAuthorizedAmount2')
            ->agreementId('agreementId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

