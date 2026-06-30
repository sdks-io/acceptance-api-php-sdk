
# Create Session Req

*This model accepts additional fields of type array.*

## Structure

`CreateSessionReq`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation26`](../../doc/models/client-reference-information-26.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation26 | setClientReferenceInformation(?ClientReferenceInformation26 clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation23`](../../doc/models/processing-information-23.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation23 | setProcessingInformation(?ProcessingInformation23 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation22`](../../doc/models/payment-information-22.md) | Optional | - | getPaymentInformation(): ?PaymentInformation22 | setPaymentInformation(?PaymentInformation22 paymentInformation): void |
| `orderInformation` | [`?OrderInformation26`](../../doc/models/order-information-26.md) | Optional | - | getOrderInformation(): ?OrderInformation26 | setOrderInformation(?OrderInformation26 orderInformation): void |
| `buyerInformation` | [`?BuyerInformation9`](../../doc/models/buyer-information-9.md) | Optional | - | getBuyerInformation(): ?BuyerInformation9 | setBuyerInformation(?BuyerInformation9 buyerInformation): void |
| `deviceInformation` | [`?DeviceInformation7`](../../doc/models/device-information-7.md) | Optional | - | getDeviceInformation(): ?DeviceInformation7 | setDeviceInformation(?DeviceInformation7 deviceInformation): void |
| `merchantInformation` | [`?MerchantInformation14`](../../doc/models/merchant-information-14.md) | Optional | - | getMerchantInformation(): ?MerchantInformation14 | setMerchantInformation(?MerchantInformation14 merchantInformation): void |
| `userInterface` | [`?UserInterface`](../../doc/models/user-interface.md) | Optional | - | getUserInterface(): ?UserInterface | setUserInterface(?UserInterface userInterface): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation[])`](../../doc/models/merchant-defined-information.md) | Optional | The object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `agreementInformation` | [`?AgreementInformation10`](../../doc/models/agreement-information-10.md) | Optional | - | getAgreementInformation(): ?AgreementInformation10 | setAgreementInformation(?AgreementInformation10 agreementInformation): void |
| `travelInformation` | [`?TravelInformation6`](../../doc/models/travel-information-6.md) | Optional | - | getTravelInformation(): ?TravelInformation6 | setTravelInformation(?TravelInformation6 travelInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CreateSessionReqBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation22Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card10Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Options1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentTypeBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MethodBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentification2Builder;

$createSessionReq = CreateSessionReqBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation26Builder::init()
            ->code('code4')
            ->reconciliationId('reconciliationId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation23Builder::init()
            ->sessionType('sessionType2')
            ->paymentFlowMode('paymentFlowMode6')
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation22Builder::init()
            ->card(
                Card10Builder::init()
                    ->number('number6')
                    ->expirationMonth('expirationMonth4')
                    ->expirationYear('expirationYear0')
                    ->type('type4')
                    ->securityCode('securityCode2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->bank(
                Bank11Builder::init()
                    ->swiftCode('swiftCode0')
                    ->account(
                        Account12Builder::init()
                            ->number('number8')
                            ->iban('iban4')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->eWallet(
                EWallet9Builder::init()
                    ->fundingSource('fundingSource2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->options(
                Options1Builder::init()
                    ->id('id2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->paymentType(
                PaymentTypeBuilder::init()
                    ->name('name6')
                    ->subTypeName('subTypeName0')
                    ->method(
                        MethodBuilder::init()
                            ->name('name6')
                            ->type('type4')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation26Builder::init()
            ->billTo(
                BillTo12Builder::init()
                    ->name('name8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->shipTo(
                ShipTo9Builder::init()
                    ->email('email2')
                    ->title('title0')
                    ->firstName('firstName0')
                    ->middleName('middleName2')
                    ->lastName('lastName8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->amountDetails(
                AmountDetails28Builder::init()
                    ->totalAmount('totalAmount4')
                    ->currency('currency0')
                    ->discountAmount('discountAmount2')
                    ->taxAmount('taxAmount8')
                    ->dutyAmount('dutyAmount2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->lineItems(
                [
                    LineItem7Builder::init()
                        ->productSku('productSku8')
                        ->productName('productName8')
                        ->quantity(132)
                        ->unitPrice('unitPrice8')
                        ->discountAmount('discountAmount4')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->invoiceDetails(
                InvoiceDetails12Builder::init()
                    ->costCenter('costCenter6')
                    ->productDescription('productDescription6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->buyerInformation(
        BuyerInformation9Builder::init()
            ->dateOfBirth('dateOfBirth2')
            ->gender('gender6')
            ->language('language2')
            ->noteToSeller('noteToSeller4')
            ->personalIdentification(
                [
                    PersonalIdentification2Builder::init()
                        ->id('id8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    PersonalIdentification2Builder::init()
                        ->id('id8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    PersonalIdentification2Builder::init()
                        ->id('id8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

