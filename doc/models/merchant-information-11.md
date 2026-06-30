
# Merchant Information 11

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor6`](../../doc/models/merchant-descriptor-6.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor6 | setMerchantDescriptor(?MerchantDescriptor6 merchantDescriptor): void |
| `categoryCode` | `?int` | Optional | The value for this field is a four-digit number that the payment card industry uses to classify<br>merchants into market segments. A payment card company assigned one or more of these values to your business when you started<br>accepting the payment card company’s cards. When you do not include this field in your request, Visa Acceptance uses the value in your<br>Visa Acceptance account.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR4<br>- Position: 150-153<br>- Field: Merchant Category Code<br><br>**Constraints**: `<= 9999` | getCategoryCode(): ?int | setCategoryCode(?int categoryCode): void |
| `administrativeArea` | `?string` | Optional | The state where the merchant is located.<br><br>#### PIN debit<br><br>State code or region code for your business. Use the Use the [State, Province, and Territory Codes for the United States and Canada]( This value might be displayed on the cardholder’s statement.<br><br>When you do not include this value in your PIN debit request, the merchant name from your account is used.<br>**Important** This value must consist of English characters.<br><br>**Note** This field is supported only for businesses located in the U.S. or Canada.<br><br>Optional field for PIN debit credit or PIN debit purchase. | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `transactionLocalDateTime` | `?string` | Optional | Date and time at your physical location.<br><br>Format: `YYYYMMDDhhmmss`, where:<br><br>- `YYYY` = year<br>- `MM` = month<br>- `DD` = day<br>- `hh` = hour<br>- `mm` = minutes<br>- `ss` = seconds<br><br>#### Used by<br><br>**Authorization**<br>Required for these processors:<br><br>- American Express Direct                                                                                                                                                                                                                                                                                                                         - American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br><br>Optional for all other processors.<br><br>**Constraints**: *Maximum Length*: `14` | getTransactionLocalDateTime(): ?string | setTransactionLocalDateTime(?string transactionLocalDateTime): void |
| `cancelUrl` | `?string` | Optional | URL to which the customer is directed if they fail to sign the mandate.<br><br>#### SEPA<br><br>Required for Create Mandate and Update Mandate<br><br>#### BACS<br><br>Required for Create Mandate<br><br>**Constraints**: *Maximum Length*: `255` | getCancelUrl(): ?string | setCancelUrl(?string cancelUrl): void |
| `successUrl` | `?string` | Optional | URL to which the customer is directed if they fail to sign the mandate.<br><br>#### SEPA<br><br>Required for Create Mandate and Update Mandate<br><br>#### BACS<br><br>Required for Create Mandate<br><br>**Constraints**: *Maximum Length*: `255` | getSuccessUrl(): ?string | setSuccessUrl(?string successUrl): void |
| `failureUrl` | `?string` | Optional | URL to which the customer is directed if they fail to sign the mandate.<br><br>#### SEPA<br><br>Required for Create Mandate and Update Mandate<br><br>#### BACS<br><br>Required for Create Mandate<br><br>**Constraints**: *Maximum Length*: `255` | getFailureUrl(): ?string | setFailureUrl(?string failureUrl): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation11 = MerchantInformation11Builder::init()
    ->merchantDescriptor(
        MerchantDescriptor6Builder::init()
            ->postalCode('postalCode4')
            ->contact('contact0')
            ->locality('locality2')
            ->name('name2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->categoryCode(8999)
    ->administrativeArea('administrativeArea8')
    ->transactionLocalDateTime('transactionLocalDateTime6')
    ->cancelUrl('cancelUrl0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

