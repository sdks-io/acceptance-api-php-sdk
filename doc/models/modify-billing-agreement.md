
# Modify Billing Agreement

*This model accepts additional fields of type array.*

## Structure

`ModifyBillingAgreement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreementInformation` | [`?AgreementInformation8`](../../doc/models/agreement-information-8.md) | Optional | - | getAgreementInformation(): ?AgreementInformation8 | setAgreementInformation(?AgreementInformation8 agreementInformation): void |
| `clientReferenceInformation` | [`?ClientReferenceInformation28`](../../doc/models/client-reference-information-28.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation28 | setClientReferenceInformation(?ClientReferenceInformation28 clientReferenceInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation5`](../../doc/models/aggregator-information-5.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation5 | setAggregatorInformation(?AggregatorInformation5 aggregatorInformation): void |
| `consumerAuthenticationInformation` | [`?ConsumerAuthenticationInformation2`](../../doc/models/consumer-authentication-information-2.md) | Optional | - | getConsumerAuthenticationInformation(): ?ConsumerAuthenticationInformation2 | setConsumerAuthenticationInformation(?ConsumerAuthenticationInformation2 consumerAuthenticationInformation): void |
| `deviceInformation` | [`?DeviceInformation5`](../../doc/models/device-information-5.md) | Optional | - | getDeviceInformation(): ?DeviceInformation5 | setDeviceInformation(?DeviceInformation5 deviceInformation): void |
| `installmentInformation` | [`?InstallmentInformation4`](../../doc/models/installment-information-4.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation4 | setInstallmentInformation(?InstallmentInformation4 installmentInformation): void |
| `merchantInformation` | [`?MerchantInformation11`](../../doc/models/merchant-information-11.md) | Optional | - | getMerchantInformation(): ?MerchantInformation11 | setMerchantInformation(?MerchantInformation11 merchantInformation): void |
| `orderInformation` | [`?OrderInformation20`](../../doc/models/order-information-20.md) | Optional | - | getOrderInformation(): ?OrderInformation20 | setOrderInformation(?OrderInformation20 orderInformation): void |
| `paymentInformation` | [`?PaymentInformation16`](../../doc/models/payment-information-16.md) | Optional | - | getPaymentInformation(): ?PaymentInformation16 | setPaymentInformation(?PaymentInformation16 paymentInformation): void |
| `processingInformation` | [`?ProcessingInformation20`](../../doc/models/processing-information-20.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation20 | setProcessingInformation(?ProcessingInformation20 processingInformation): void |
| `buyerInformation` | [`?BuyerInformation7`](../../doc/models/buyer-information-7.md) | Optional | - | getBuyerInformation(): ?BuyerInformation7 | setBuyerInformation(?BuyerInformation7 buyerInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ModifyBillingAgreementBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AggregatorInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchantBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ConsumerAuthenticationInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation7Builder;

$modifyBillingAgreement = ModifyBillingAgreementBuilder::init()
    ->agreementInformation(
        AgreementInformation8Builder::init()
            ->id('G8UD2OKG49UW')
            ->eSignIndicator('y')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->clientReferenceInformation(
        ClientReferenceInformation28Builder::init()
            ->code('TC84105-1')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->aggregatorInformation(
        AggregatorInformation5Builder::init()
            ->name('aggregatorname')
            ->subMerchant(
                SubMerchantBuilder::init()
                    ->cardAcceptorId('cardAcceptorId0')
                    ->id('id6')
                    ->name('rupay')
                    ->address1('address16')
                    ->locality('locality4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->consumerAuthenticationInformation(
        ConsumerAuthenticationInformation2Builder::init()
            ->authenticationTransactionContextId('100000000000000000000000025253')
            ->cavv('cavv2')
            ->transactionToken('AxjzbwSTcz9aHyOIL490/949UafAxfvksgAxHXa2/+xcVZ0CtA+AbkvF')
            ->xid('xid4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->deviceInformation(
        DeviceInformation5Builder::init()
            ->httpAcceptBrowserValue('http')
            ->ipAddress('10.10.10.10')
            ->userAgentBrowserValue('safari')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->installmentInformation(
        InstallmentInformation4Builder::init()
            ->identifier('1000000')
            ->paymentType('1')
            ->build()
    )
    ->merchantInformation(
        MerchantInformation11Builder::init()
            ->cancelUrl('https://www.valid.merchant.redirect.url.from.request.html?actioncancel')
            ->successUrl('https://www.valid.merchant.redirect.url.from.request.html?actionsuccess')
            ->failureUrl('https://www.valid.merchant.redirect.url.from.request.html?actionfailure')
            ->build()
    )
    ->orderInformation(
        OrderInformation20Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('100.00')
                    ->currency('INR')
                    ->build()
            )
            ->billTo(
                BillTo7Builder::init()
                    ->address1('808 Metro Blvd')
                    ->address2('Suite A101')
                    ->administrativeArea('CA')
                    ->company('Visa Acceptance Trading Inc.')
                    ->country('US')
                    ->county('San Francisco')
                    ->district('SF')
                    ->email('srbuyeroffice@cybs.com')
                    ->firstName('Comet')
                    ->middleName('Foster')
                    ->lastName('Bowditch')
                    ->locality('San Francisco')
                    ->phoneNumber('16501234567')
                    ->postalCode('944041234')
                    ->title('Senior Buyer')
                    ->build()
            )
            ->build()
    )
    ->paymentInformation(
        PaymentInformation16Builder::init()
            ->card(
                Card7Builder::init()
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->number('5082794233463')
                    ->securityCode('123')
                    ->type('061')
                    ->build()
            )
            ->paymentType(
                PaymentType13Builder::init()
                    ->method(
                        Method13Builder::init()
                            ->name('SENTENIAL')
                            ->build()
                    )
                    ->name('directDebitBacs')
                    ->build()
            )
            ->bank(
                Bank7Builder::init()
                    ->account(
                        Account9Builder::init()
                            ->number('1234567890ABCDEFGHIJ0123456789')
                            ->build()
                    )
                    ->iban('NL51ABNC1122334455')
                    ->swiftCode('ABNCNL2AGMK')
                    ->scheme('bacs')
                    ->build()
            )
            ->build()
    )
    ->processingInformation(
        ProcessingInformation20Builder::init()
            ->commerceIndicator('rpy')
            ->actionList(
                [
                    'UPDATE_AGREEMENT'
                ]
            )
            ->build()
    )
    ->buyerInformation(
        BuyerInformation7Builder::init()
            ->dateOfBirth('19990101')
            ->gender('F')
            ->language('en')
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

