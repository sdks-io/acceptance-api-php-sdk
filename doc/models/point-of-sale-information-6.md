
# Point of Sale Information 6

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `emv` | [`?Emv6`](../../doc/models/emv-6.md) | Optional | - | getEmv(): ?Emv6 | setEmv(?Emv6 emv): void |
| `amexCapnData` | `?string` | Optional | Point-of-sale details for the transaction. This value is returned only for **American Express Direct**.<br>Visa Acceptance generates this value, which consists of a series of codes that identify terminal capability,<br>security data, and specific conditions present at the time the transaction occurred. To comply with the CAPN<br>requirements, this value must be included in all subsequent follow-on requests, such as captures and follow-on<br>credits.<br><br>When you perform authorizations, captures, and credits through Visa Acceptance, Visa Acceptance passes this value from<br>the authorization service to the subsequent services for you. However, when you perform authorizations through<br>Visa Acceptance and perform subsequent services through other financial institutions, you must ensure that your<br>requests for captures and credits include this value.<br><br>**Constraints**: *Maximum Length*: `15` | getAmexCapnData(): ?string | setAmexCapnData(?string amexCapnData): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation6 = PointOfSaleInformation6Builder::init()
    ->emv(
        Emv6Builder::init()
            ->tags('tags4')
            ->fallback(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->amexCapnData('amexCapnData8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

