
# Update Order Request

*This model accepts additional fields of type array.*

## Structure

`UpdateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation39`](../../doc/models/client-reference-information-39.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation39 | setClientReferenceInformation(?ClientReferenceInformation39 clientReferenceInformation): void |
| `orderInformation` | [`?OrderInformation31`](../../doc/models/order-information-31.md) | Optional | - | getOrderInformation(): ?OrderInformation31 | setOrderInformation(?OrderInformation31 orderInformation): void |
| `merchantInformation` | [`?MerchantInformation17`](../../doc/models/merchant-information-17.md) | Optional | - | getMerchantInformation(): ?MerchantInformation17 | setMerchantInformation(?MerchantInformation17 merchantInformation): void |
| `paymentInformation` | [`?PaymentInformation28`](../../doc/models/payment-information-28.md) | Optional | - | getPaymentInformation(): ?PaymentInformation28 | setPaymentInformation(?PaymentInformation28 paymentInformation): void |
| `processingInformation` | [`?ProcessingInformation26`](../../doc/models/processing-information-26.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation26 | setProcessingInformation(?ProcessingInformation26 processingInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\UpdateOrderRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation39Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation31Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails32Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation17Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation26Builder;

$updateOrderRequest = UpdateOrderRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation39Builder::init()
            ->reconciliationId('reconciliationId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation31Builder::init()
            ->amountDetails(
                AmountDetails32Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
                    ->discountAmount('discountAmount2')
                    ->shippingAmount('shippingAmount6')
                    ->shippingDiscountAmount('shippingDiscountAmount0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->shipTo(
                ShipTo11Builder::init()
                    ->firstName('RTS')
                    ->lastName('VDP')
                    ->address1('201 S. Division St.')
                    ->address2('address26')
                    ->locality('Ann Arbor')
                    ->administrativeArea('MI')
                    ->postalCode('48104-2201')
                    ->country('US')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->lineItems(
                [
                    LineItem9Builder::init()
                        ->productName('productName8')
                        ->productDescription('productDescription0')
                        ->productSku('productSku8')
                        ->quantity(132)
                        ->typeOfSupply('typeOfSupply8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->invoiceDetails(
                InvoiceDetails14Builder::init()
                    ->productDescription('productDescription6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('invoiceDescription', ApiHelper::deserialize('{"productDescription":"Description of the product invoice"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation17Builder::init()
            ->merchantDescriptor(
                MerchantDescriptor11Builder::init()
                    ->name('Merchant1')
                    ->email('merchant1@gmail.com')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation28Builder::init()
            ->paymentType(
                PaymentType19Builder::init()
                    ->name('ewallet')
                    ->method(
                        Method19Builder::init()
                            ->name('payPal')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation26Builder::init()
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

