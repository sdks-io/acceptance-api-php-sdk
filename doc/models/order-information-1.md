
# Order Information 1

*This model accepts additional fields of type array.*

## Structure

`OrderInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails2`](../../doc/models/amount-details-2.md) | Optional | - | getAmountDetails(): ?AmountDetails2 | setAmountDetails(?AmountDetails2 amountDetails): void |
| `invoiceDetails` | [`?InvoiceDetails2`](../../doc/models/invoice-details-2.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails2 | setInvoiceDetails(?InvoiceDetails2 invoiceDetails): void |
| `rewardPointsDetails` | [`?RewardPointsDetails`](../../doc/models/reward-points-details.md) | Optional | - | getRewardPointsDetails(): ?RewardPointsDetails | setRewardPointsDetails(?RewardPointsDetails rewardPointsDetails): void |
| `billTo` | [`?BillTo1`](../../doc/models/bill-to-1.md) | Optional | - | getBillTo(): ?BillTo1 | setBillTo(?BillTo1 billTo): void |
| `shipTo` | [`?ShipTo1`](../../doc/models/ship-to-1.md) | Optional | - | getShipTo(): ?ShipTo1 | setShipTo(?ShipTo1 shipTo): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RewardPointsDetailsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo1Builder;

$orderInformation1 = OrderInformation1Builder::init()
    ->amountDetails(
        AmountDetails2Builder::init()
            ->totalAmount('totalAmount4')
            ->authorizedAmount('authorizedAmount0')
            ->currency('currency0')
            ->settlementAmount('settlementAmount0')
            ->settlementCurrency('settlementCurrency8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->invoiceDetails(
        InvoiceDetails2Builder::init()
            ->level3TransmissionStatus(false)
            ->salesSlipNumber(98999)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->rewardPointsDetails(
        RewardPointsDetailsBuilder::init()
            ->pointsBeforeRedemption('pointsBeforeRedemption8')
            ->pointsValueBeforeRedemption('pointsValueBeforeRedemption0')
            ->pointsRedeemed('pointsRedeemed8')
            ->pointsValueRedeemed('pointsValueRedeemed8')
            ->pointsAfterRedemption('pointsAfterRedemption2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillTo1Builder::init()
            ->firstName('firstName4')
            ->lastName('lastName2')
            ->address1('address16')
            ->address2('address20')
            ->locality('locality8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo1Builder::init()
            ->firstname('firstname2')
            ->lastname('lastname8')
            ->address1('address12')
            ->address2('address26')
            ->locality('locality4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

