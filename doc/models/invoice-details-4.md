
# Invoice Details 4

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `purchaseOrderNumber` | `?string` | Optional | Value used by your customer to identify the order. This value is typically a purchase order number. Visa Acceptance<br>recommends that you do not populate the field with all zeros or nines.<br><br>**Constraints**: *Maximum Length*: `50` | getPurchaseOrderNumber(): ?string | setPurchaseOrderNumber(?string purchaseOrderNumber): void |
| `purchaseOrderDate` | `?string` | Optional | Date the order was processed. `Format: YYYY-MM-DD`.<br><br>**Constraints**: *Maximum Length*: `10` | getPurchaseOrderDate(): ?string | setPurchaseOrderDate(?string purchaseOrderDate): void |
| `purchaseContactName` | `?string` | Optional | The name of the individual or the company contacted for company authorized purchases.<br><br>**Constraints**: *Maximum Length*: `36` | getPurchaseContactName(): ?string | setPurchaseContactName(?string purchaseContactName): void |
| `taxable` | `?bool` | Optional | Flag that indicates whether an order is taxable. This value must be true if the sum of all _lineItems[].taxAmount_ values > 0.<br><br>If you do not include any `lineItems[].taxAmount` values in your request, Visa Acceptance does not include<br>`invoiceDetails.taxable` in the data it sends to the processor.<br><br>Possible values:<br><br>- **true**<br>- **false** | getTaxable(): ?bool | setTaxable(?bool taxable): void |
| `vatInvoiceReferenceNumber` | `?string` | Optional | VAT invoice number associated with the transaction.<br><br>**Constraints**: *Maximum Length*: `15` | getVatInvoiceReferenceNumber(): ?string | setVatInvoiceReferenceNumber(?string vatInvoiceReferenceNumber): void |
| `commodityCode` | `?string` | Optional | International description code of the overall order’s goods or services or the Categorizes purchases for VAT<br>reporting. Contact your acquirer for a list of codes.<br><br>**Constraints**: *Maximum Length*: `4` | getCommodityCode(): ?string | setCommodityCode(?string commodityCode): void |
| `transactionAdviceAddendum` | [`?(TransactionAdviceAddendum[])`](../../doc/models/transaction-advice-addendum.md) | Optional | - | getTransactionAdviceAddendum(): ?array | setTransactionAdviceAddendum(?array transactionAdviceAddendum): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails4 = InvoiceDetails4Builder::init()
    ->purchaseOrderNumber('purchaseOrderNumber6')
    ->purchaseOrderDate('purchaseOrderDate2')
    ->purchaseContactName('purchaseContactName2')
    ->taxable(false)
    ->vatInvoiceReferenceNumber('vatInvoiceReferenceNumber2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

