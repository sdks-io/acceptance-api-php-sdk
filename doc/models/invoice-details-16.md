
# Invoice Details 16

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails16`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `salesSlipNumber` | `?int` | Optional | Transaction identifier that is generated. You have the option of printing the sales slip number on the receipt.<br>This field is supported only on Visa Acceptance through Visanet and JCN gateway.<br><br>Optional field.<br><br>#### Card Present processing message<br><br>If you included this field in the request, the returned value is the value that you sent in the request.<br>If you did not include this field in the request, the system generated this value for you.<br><br>The difference between this reply field and the `processorInformation.systemTraceAuditNumber` field is that the<br>system generates the system trace audit number (STAN), and you must print the receipt number on the receipt;<br>whereas you can generate the sales slip number, and you can choose to print the sales slip number on the receipt.<br><br>**Constraints**: `<= 99999` | getSalesSlipNumber(): ?int | setSalesSlipNumber(?int salesSlipNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails16Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails16 = InvoiceDetails16Builder::init()
    ->salesSlipNumber(98999)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

