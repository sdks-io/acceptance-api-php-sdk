
# Invoice Details

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `invoiceNumber` | `?string` | Optional | Invoice Number. | getInvoiceNumber(): ?string | setInvoiceNumber(?string invoiceNumber): void |
| `barcodeNumber` | `?string` | Optional | Barcode Number. | getBarcodeNumber(): ?string | setBarcodeNumber(?string barcodeNumber): void |
| `expirationDate` | `?string` | Optional | Expiration Date. | getExpirationDate(): ?string | setExpirationDate(?string expirationDate): void |
| `purchaseOrderNumber` | `?string` | Optional | Value used by your customer to identify the order. This value is typically a purchase order number. Visa Acceptance<br>recommends that you do not populate the field with all zeros or nines.<br><br>**Constraints**: *Maximum Length*: `50` | getPurchaseOrderNumber(): ?string | setPurchaseOrderNumber(?string purchaseOrderNumber): void |
| `purchaseOrderDate` | `?string` | Optional | Date the order was processed. `Format: YYYY-MM-DD`.<br><br>**Constraints**: *Maximum Length*: `10` | getPurchaseOrderDate(): ?string | setPurchaseOrderDate(?string purchaseOrderDate): void |
| `purchaseContactName` | `?string` | Optional | The name of the individual or the company contacted for company authorized purchases.<br><br>**Constraints**: *Maximum Length*: `36` | getPurchaseContactName(): ?string | setPurchaseContactName(?string purchaseContactName): void |
| `taxable` | `?bool` | Optional | Flag that indicates whether an order is taxable. This value must be true if the sum of all _lineItems[].taxAmount_ values > 0.<br><br>If you do not include any `lineItems[].taxAmount` values in your request, Visa Acceptance does not include<br>`invoiceDetails.taxable` in the data it sends to the processor.<br><br>Possible values:<br><br>- **true**<br>- **false** | getTaxable(): ?bool | setTaxable(?bool taxable): void |
| `vatInvoiceReferenceNumber` | `?string` | Optional | VAT invoice number associated with the transaction.<br><br>**Constraints**: *Maximum Length*: `15` | getVatInvoiceReferenceNumber(): ?string | setVatInvoiceReferenceNumber(?string vatInvoiceReferenceNumber): void |
| `commodityCode` | `?string` | Optional | International description code of the overall order’s goods or services or the Categorizes purchases for VAT<br>reporting. Contact your acquirer for a list of codes.<br><br>**Constraints**: *Maximum Length*: `4` | getCommodityCode(): ?string | setCommodityCode(?string commodityCode): void |
| `merchandiseCode` | `?int` | Optional | Identifier for the merchandise. This field is supported only on the processors listed in this field description.<br><br>#### American Express Direct<br><br>Possible value:<br><br>- 1000: Gift card<br><br>#### Visa Acceptance through VisaNet<br><br>This value must be right justified. In Japan, this value is called a _goods code_.<br><br>#### JCN Gateway<br><br>This value must be right justified. In Japan, this value is called a _goods code_. | getMerchandiseCode(): ?int | setMerchandiseCode(?int merchandiseCode): void |
| `transactionAdviceAddendum` | [`?(TransactionAdviceAddendum[])`](../../doc/models/transaction-advice-addendum.md) | Optional | - | getTransactionAdviceAddendum(): ?array | setTransactionAdviceAddendum(?array transactionAdviceAddendum): void |
| `referenceDataCode` | `?string` | Optional | Code that identifies the value of the `referenceDataNumber` field.<br><br>This field is a pass-through, which means that Visa Acceptance does not verify the value or modify it in any way<br>before sending it to the processor.<br><br>**Constraints**: *Maximum Length*: `3` | getReferenceDataCode(): ?string | setReferenceDataCode(?string referenceDataCode): void |
| `referenceDataNumber` | `?string` | Optional | Reference number. The meaning of this value is identified by the value of the `referenceDataCode` field.<br><br>This field is a pass-through, which means that Visa Acceptance does not verify the value or modify it in any way<br>before sending it to the processor.<br><br>**Constraints**: *Maximum Length*: `30` | getReferenceDataNumber(): ?string | setReferenceDataNumber(?string referenceDataNumber): void |
| `salesSlipNumber` | `?int` | Optional | Transaction identifier that is generated. You have the option of printing the sales slip number on the receipt.<br>This field is supported only on Visa Acceptance through Visanet and JCN gateway.<br><br>Optional field.<br><br>#### Card Present processing message<br><br>If you included this field in the request, the returned value is the value that you sent in the request.<br>If you did not include this field in the request, the system generated this value for you.<br><br>The difference between this reply field and the `processorInformation.systemTraceAuditNumber` field is that the<br>system generates the system trace audit number (STAN), and you must print the receipt number on the receipt;<br>whereas you can generate the sales slip number, and you can choose to print the sales slip number on the receipt.<br><br>**Constraints**: `<= 99999` | getSalesSlipNumber(): ?int | setSalesSlipNumber(?int salesSlipNumber): void |
| `invoiceDate` | `?string` | Optional | Date of the tax calculation. Use format YYYYMMDD. You can provide a date in the past if you are calculating tax for a refund and want to know what the tax was on the date the order was placed.<br>You can provide a date in the future if you are calculating the tax for a future date, such as an upcoming tax holiday.<br><br>The default is the date, in Pacific time, that the bank receives the request.<br>Keep this in mind if you are in a different time zone and want the tax calculated with the rates that are applicable on a specific date.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br><br>**Constraints**: *Maximum Length*: `8` | getInvoiceDate(): ?string | setInvoiceDate(?string invoiceDate): void |
| `costCenter` | `?string` | Optional | Cost centre of the merchant<br><br>**Constraints**: *Maximum Length*: `25` | getCostCenter(): ?string | setCostCenter(?string costCenter): void |
| `issuerMessage` | `?string` | Optional | Text message from the issuer. If you give the customer a receipt, display this value on the receipt.<br><br>**Constraints**: *Maximum Length*: `41` | getIssuerMessage(): ?string | setIssuerMessage(?string issuerMessage): void |
| `productDescription` | `?string` | Optional | Brief description of item. | getProductDescription(): ?string | setProductDescription(?string productDescription): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails = InvoiceDetailsBuilder::init()
    ->invoiceNumber('invoiceNumber8')
    ->barcodeNumber('barcodeNumber8')
    ->expirationDate('expirationDate2')
    ->purchaseOrderNumber('purchaseOrderNumber8')
    ->purchaseOrderDate('purchaseOrderDate4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

