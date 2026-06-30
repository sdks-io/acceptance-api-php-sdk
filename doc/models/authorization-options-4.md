
# Authorization Options 4

*This model accepts additional fields of type array.*

## Structure

`AuthorizationOptions4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authType` | `?string` | Optional | Authorization type. Possible values:<br><br>- `AUTOCAPTURE`: automatic capture.<br>- `STANDARDCAPTURE`: standard capture.<br>- `VERBAL`: forced capture. Include it in the payment request for a forced capture. Include it in the capture request for a verbal payment.<br><br>#### Asia, Middle East, and Africa Gateway; Cielo; Comercio Latino; and Visa Acceptance Latin American Processing<br><br>Set this field to `AUTOCAPTURE` and include it in a bundled request to indicate that you are requesting an automatic capture. If your account is configured to enable automatic captures, set this field to `STANDARDCAPTURE` and include it in a standard authorization or bundled request to indicate that you are overriding an automatic capture.<br><br>#### Forced Capture<br><br>Set this field to `VERBAL` and include it in the authorization request to indicate that you are performing a forced capture; therefore, you receive the authorization code outside the Visa Acceptance system.<br><br>#### Verbal Authorization<br><br>Set this field to `VERBAL` and include it in the capture request to indicate that the request is for a verbal authorization.<br><br>#### for PayPal ptsV2CreateOrderPost400Response<br><br>Set this field to 'AUTHORIZE' or 'CAPTURE' depending on whether you want to invoke delayed capture or sale respectively.<br><br>**Constraints**: *Maximum Length*: `15` | getAuthType(): ?string | setAuthType(?string authType): void |
| `verbalAuthCode` | `?string` | Optional | Authorization code.<br><br>#### Forced Capture<br><br>Use this field to send the authorization code you received from a payment that you authorized<br>outside the Visa Acceptance system.<br><br>#### PIN debit<br><br>Authorization code that is returned by the processor.<br><br>Returned by PIN debit purchase.<br><br>#### Verbal Authorization<br><br>Use this field in CAPTURE API to send the verbally received authorization code.<br><br>**Constraints**: *Maximum Length*: `7` | getVerbalAuthCode(): ?string | setVerbalAuthCode(?string verbalAuthCode): void |
| `verbalAuthTransactionId` | `?string` | Optional | Transaction ID (TID).<br><br>#### FDMS South<br><br>This field is required for verbal authorizations and forced captures with the American Express card type to comply<br>with the CAPN requirements:<br><br>- Forced capture: Obtain the value for this field from the authorization response.<br>- Verbal authorization: You cannot obtain a value for this field so Visa Acceptance uses the default value of `000000000000000` (15<br>  zeros).<br><br>**Constraints**: *Maximum Length*: `15` | getVerbalAuthTransactionId(): ?string | setVerbalAuthTransactionId(?string verbalAuthTransactionId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationOptions4 = AuthorizationOptions4Builder::init()
    ->authType('authType8')
    ->verbalAuthCode('verbalAuthCode8')
    ->verbalAuthTransactionId('verbalAuthTransactionId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

