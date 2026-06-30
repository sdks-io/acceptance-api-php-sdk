
# Processing Information 1

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankTransferOptions` | [`?BankTransferOptions1`](../../doc/models/bank-transfer-options-1.md) | Optional | - | getBankTransferOptions(): ?BankTransferOptions1 | setBankTransferOptions(?BankTransferOptions1 bankTransferOptions): void |
| `paymentSolution` | `?string` | Optional | Type of digital payment solution for the transaction. Possible Values:<br><br>- `visacheckout`: Visa Checkout. This value is required for Visa Checkout transactions. For details, see `payment_solution` field description in [Visa Checkout Using the REST API.](<br>- `001`: Apple Pay.<br>- `004`: Visa Acceptance In-App Solution.<br>- `005`: Masterpass. This value is required for Masterpass transactions on OmniPay Direct.<br>- `006`: Android Pay.<br>- `007`: Chase Pay.<br>- `008`: Samsung Pay.<br>- `012`: Google Pay.<br>- `013`: Visa Acceptance P2PE Decryption<br>- `014`: Mastercard credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `015`: Visa credential on file (COF) payment network token. Returned in authorizations that use a payment network token associated with a TMS token.<br>- `027`: Click to Pay.<br><br>**Constraints**: *Maximum Length*: `12` | getPaymentSolution(): ?string | setPaymentSolution(?string paymentSolution): void |
| `enhancedDataEnabled` | `?bool` | Optional | The possible values for the reply field are:<br><br>- `true` : the airline data was included in the request to the processor.<br>- `false` : the airline data was not included in the request to the processor.<br><br>Returned by authorization, capture, or credit services. | getEnhancedDataEnabled(): ?bool | setEnhancedDataEnabled(?bool enhancedDataEnabled): void |
| `captureOptions` | [`?CaptureOptions1`](../../doc/models/capture-options-1.md) | Optional | - | getCaptureOptions(): ?CaptureOptions1 | setCaptureOptions(?CaptureOptions1 captureOptions): void |
| `authorizationOptions` | [`?AuthorizationOptions2`](../../doc/models/authorization-options-2.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions2 | setAuthorizationOptions(?AuthorizationOptions2 authorizationOptions): void |
| `purchaseOptions` | [`?PurchaseOptions1`](../../doc/models/purchase-options-1.md) | Optional | - | getPurchaseOptions(): ?PurchaseOptions1 | setPurchaseOptions(?PurchaseOptions1 purchaseOptions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureOptions1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions2Builder;

$processingInformation1 = ProcessingInformation1Builder::init()
    ->bankTransferOptions(
        BankTransferOptions1Builder::init()
            ->settlementMethod('settlementMethod4')
            ->fraudScreeningLevel('fraudScreeningLevel0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentSolution('paymentSolution2')
    ->enhancedDataEnabled(false)
    ->captureOptions(
        CaptureOptions1Builder::init()
            ->finalCapture('finalCapture8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->authorizationOptions(
        AuthorizationOptions2Builder::init()
            ->serviceType('serviceType8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

