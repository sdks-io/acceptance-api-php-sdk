
# Intimate Billing Agreement

*This model accepts additional fields of type array.*

## Structure

`IntimateBillingAgreement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `installmentInformation` | [`?InstallmentInformation4`](../../doc/models/installment-information-4.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation4 | setInstallmentInformation(?InstallmentInformation4 installmentInformation): void |
| `merchantInformation` | [`?MerchantInformation11`](../../doc/models/merchant-information-11.md) | Optional | - | getMerchantInformation(): ?MerchantInformation11 | setMerchantInformation(?MerchantInformation11 merchantInformation): void |
| `orderInformation` | [`?OrderInformation20`](../../doc/models/order-information-20.md) | Optional | - | getOrderInformation(): ?OrderInformation20 | setOrderInformation(?OrderInformation20 orderInformation): void |
| `paymentInformation` | [`?PaymentInformation16`](../../doc/models/payment-information-16.md) | Optional | - | getPaymentInformation(): ?PaymentInformation16 | setPaymentInformation(?PaymentInformation16 paymentInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IntimateBillingAgreementBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCard5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account9Builder;

$intimateBillingAgreement = IntimateBillingAgreementBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('code4')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->installmentInformation(
        InstallmentInformation4Builder::init()
            ->alertPreference('SMS')
            ->firstInstallmentDate('2111')
            ->identifier('1000000000')
            ->lastInstallmentDate('3110')
            ->maxAmount('1000')
            ->minAmount('100')
            ->paymentType('1')
            ->preferredDay('1')
            ->sequence(2)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation11Builder::init()
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
            ->administrativeArea('administrativeArea0')
            ->transactionLocalDateTime('20211216124549')
            ->cancelUrl('cancelUrl8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation20Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('00')
                    ->currency('INR')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->billTo(
                BillTo7Builder::init()
                    ->address1('address16')
                    ->address2('address20')
                    ->administrativeArea('administrativeArea4')
                    ->buildingNumber('buildingNumber8')
                    ->company('company8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation16Builder::init()
            ->card(
                Card7Builder::init()
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->number('5082302886091')
                    ->securityCode('123')
                    ->type('061')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->tokenizedCard(
                TokenizedCard5Builder::init()
                    ->cryptogram('cryptogram0')
                    ->expirationMonth('expirationMonth0')
                    ->expirationYear('expirationYear4')
                    ->number('number2')
                    ->transactionType('transactionType4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->paymentType(
                PaymentType13Builder::init()
                    ->method(
                        Method13Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->bank(
                Bank7Builder::init()
                    ->account(
                        Account9Builder::init()
                            ->number('number8')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->iban('iban2')
                    ->swiftCode('swiftCode0')
                    ->scheme('scheme8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

