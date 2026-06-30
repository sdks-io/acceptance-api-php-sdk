
# Authorization Options 6

*This model accepts additional fields of type array.*

## Structure

`AuthorizationOptions6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authType` | `?string` | Optional | Authorization type. Possible values:<br><br>- `AUTOCAPTURE`: automatic capture.<br>- `STANDARDCAPTURE`: standard capture.<br>- `VERBAL`: forced capture. Include it in the payment request for a forced capture. Include it in the capture request for a verbal payment.<br><br>#### Asia, Middle East, and Africa Gateway; Cielo; Comercio Latino; and Visa Acceptance Latin American Processing<br><br>Set this field to `AUTOCAPTURE` and include it in a bundled request to indicate that you are requesting an automatic capture. If your account is configured to enable automatic captures, set this field to `STANDARDCAPTURE` and include it in a standard authorization or bundled request to indicate that you are overriding an automatic capture.<br><br>#### Forced Capture<br><br>Set this field to `VERBAL` and include it in the authorization request to indicate that you are performing a forced capture; therefore, you receive the authorization code outside the Visa Acceptance system.<br><br>#### Verbal Authorization<br><br>Set this field to `VERBAL` and include it in the capture request to indicate that the request is for a verbal authorization.<br><br>#### for PayPal ptsV2CreateOrderPost400Response<br><br>Set this field to 'AUTHORIZE' or 'CAPTURE' depending on whether you want to invoke delayed capture or sale respectively.<br><br>**Constraints**: *Maximum Length*: `15` | getAuthType(): ?string | setAuthType(?string authType): void |
| `authIndicator` | `?string` | Optional | Flag that specifies the purpose of the authorization.<br><br>Possible values:<br><br>- **0**: Preauthorization<br>- **1**: Final authorization<br><br>To set the default for this field, contact Visa Acceptance Customer Support.<br><br>#### Barclays and Elavon<br><br>The default for Barclays and Elavon is 1 (final authorization). To change the default for this field, contact Visa Acceptance Customer Support.<br><br>#### Visa Acceptance through VisaNet<br><br>When the value for this field is 0, it corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCR0<br>- Position: 164<br>- Field: Additional Authorization Indicators<br>  When the value for this field is 1, it does not correspond to any data in the TC 33 capture file.<br><br>**Constraints**: *Maximum Length*: `1` | getAuthIndicator(): ?string | setAuthIndicator(?string authIndicator): void |
| `extendAuthIndicator` | `?string` | Optional | Indicates Authorization extension transaction. Extension transaction is used to prolong the settlement period by one additional settlement cycle period.<br><br>Possible values:<br><br>- true: Transaction is an Authorization Extension transaction.<br>- false: Transaction is not an Authorization Extension transaction.<br><br>**Constraints**: *Maximum Length*: `5` | getExtendAuthIndicator(): ?string | setExtendAuthIndicator(?string extendAuthIndicator): void |
| `cardVerificationIndicator` | `?bool` | Optional | This API field will indicate whether a card verification check is being performed during the transaction<br><br>Possible values:<br><br>- `true`<br>- `false` (default value) | getCardVerificationIndicator(): ?bool | setCardVerificationIndicator(?bool cardVerificationIndicator): void |
| `initiator` | [`?Initiator26`](../../doc/models/initiator-26.md) | Optional | - | getInitiator(): ?Initiator26 | setInitiator(?Initiator26 initiator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransactionObjectBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationOptions6 = AuthorizationOptions6Builder::init()
    ->authType('authType8')
    ->authIndicator('authIndicator4')
    ->extendAuthIndicator('extendAuthIndicator8')
    ->cardVerificationIndicator(false)
    ->initiator(
        Initiator26Builder::init()
            ->type('type4')
            ->credentialStoredOnFile('credentialStoredOnFile6')
            ->storedCredentialUsed('storedCredentialUsed0')
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
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

