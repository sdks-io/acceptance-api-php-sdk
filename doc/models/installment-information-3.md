
# Installment Information 3

*This model accepts additional fields of type array.*

## Structure

`InstallmentInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `planType` | `?string` | Optional | #### American Express Direct, Cielo, and Visa Acceptance Latin American Processing<br><br>Flag that indicates the type of funding for the installment plan associated with the payment.<br><br>Possible values:<br><br>- `1`: Merchant-funded installment plan<br>- `2`: Issuer-funded installment plan<br>  If you do not include this field in the request, Visa Acceptance uses the value in your Visa Acceptance account.<br><br>To change the value in your Visa Acceptance account, contact Visa Acceptance Customer Service.<br><br>#### Visa Acceptance through VisaNet and American Express<br><br>Defined code that indicates the type of installment plan for this transaction.<br><br>Contact American Express for:<br><br>- Information about the kinds of installment plans that American Express provides<br>- Values for this field<br><br>For installment payments with American Express in Brazil, the value for this field corresponds to the following data in the TC 33 capture file*:<br><br>- Record: CP07 TCR3<br>- Position: 5-6<br>- Field: Plan Type<br><br>* The TC 33 Capture file contains information about the purchases and refunds that a merchant submits to Visa Acceptance. Visa Acceptance through VisaNet creates the TC 33 Capture file at the end of the day and sends it to the merchant’s acquirer, who uses this information to facilitate end-of-day clearing processing with payment card companies.<br><br>#### Visa Acceptance through VisaNet with Visa or Mastercard<br><br>Flag indicating the type of funding for the installment plan associated with the payment.<br>Possible values:<br><br>- 1 or 01: Merchant-funded installment plan<br>- 2 or 02: Issuer-funded installment plan<br>- 43: Crediario installment plan—only with Visa in Brazil<br><br>For installment payments with Visa in Brazil, the value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP07 TCR1<br>- Position: 5-6<br>- Field: Installment Type<br><br>For all other kinds of installment payments, the value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR5<br>- Position: 39-40<br>- Field: Installment Plan Type (Issuer or Merchant)<br><br>**Constraints**: *Maximum Length*: `1` | getPlanType(): ?string | setPlanType(?string planType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$installmentInformation3 = InstallmentInformation3Builder::init()
    ->planType('planType4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

