
# Merchant Information 3

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor`](../../doc/models/merchant-descriptor.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor | setMerchantDescriptor(?MerchantDescriptor merchantDescriptor): void |
| `cardAcceptorReferenceNumber` | `?string` | Optional | Reference number that facilitates card acceptor/corporation communication and record keeping.<br><br>**Constraints**: *Maximum Length*: `25` | getCardAcceptorReferenceNumber(): ?string | setCardAcceptorReferenceNumber(?string cardAcceptorReferenceNumber): void |
| `categoryCode` | `?int` | Optional | The value for this field is a four-digit number that the payment card industry uses to classify<br>merchants into market segments. A payment card company assigned one or more of these values to your business when you started<br>accepting the payment card company’s cards. When you do not include this field in your request, Visa Acceptance uses the value in your<br>Visa Acceptance account.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR4<br>- Position: 150-153<br>- Field: Merchant Category Code<br><br>**Constraints**: `<= 9999` | getCategoryCode(): ?int | setCategoryCode(?int categoryCode): void |
| `vatRegistrationNumber` | `?string` | Optional | Your government-assigned tax identification number.<br><br>#### Tax Calculation<br><br>Required field for value added tax only. Not applicable to U.S. and Canadian taxes.<br><br>#### Visa Acceptance through VisaNet<br><br>For CtV processors, the maximum length is 20.<br><br>**Constraints**: *Maximum Length*: `21` | getVatRegistrationNumber(): ?string | setVatRegistrationNumber(?string vatRegistrationNumber): void |
| `serviceFeeDescriptor` | [`?ServiceFeeDescriptor`](../../doc/models/service-fee-descriptor.md) | Optional | - | getServiceFeeDescriptor(): ?ServiceFeeDescriptor | setServiceFeeDescriptor(?ServiceFeeDescriptor serviceFeeDescriptor): void |
| `taxId` | `?string` | Optional | Your Cadastro Nacional da Pessoa Jurídica (CNPJ) number.<br><br>This field is supported only for BNDES transactions on Visa Acceptance through VisaNet.<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP07 TCR6<br>- Position: 40-59<br>- Field: BNDES Reference Field 1<br><br>**Constraints**: *Maximum Length*: `15` | getTaxId(): ?string | setTaxId(?string taxId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ServiceFeeDescriptorBuilder;

$merchantInformation3 = MerchantInformation3Builder::init()
    ->merchantDescriptor(
        MerchantDescriptorBuilder::init()
            ->name('name2')
            ->alternateName('alternateName0')
            ->contact('contact0')
            ->address1('address10')
            ->locality('locality2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->cardAcceptorReferenceNumber('cardAcceptorReferenceNumber8')
    ->categoryCode(8999)
    ->vatRegistrationNumber('vatRegistrationNumber8')
    ->serviceFeeDescriptor(
        ServiceFeeDescriptorBuilder::init()
            ->name('name6')
            ->contact('contact6')
            ->state('state2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

