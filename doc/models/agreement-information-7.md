
# Agreement Information 7

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Identifier for the mandate.<br><br>**Constraints**: *Maximum Length*: `50` | getId(): ?string | setId(?string id): void |
| `dateSigned` | `?string` | Optional | Date the mandate has been signed.  Format YYYYMMdd<br><br>**Constraints**: *Maximum Length*: `8` | getDateSigned(): ?string | setDateSigned(?string dateSigned): void |
| `dateCreated` | `?string` | Optional | Date the mandate has been created.  Format YYYYMMdd<br><br>**Constraints**: *Maximum Length*: `8` | getDateCreated(): ?string | setDateCreated(?string dateCreated): void |
| `encodedHtml` | `?string` | Optional | Base64 encoded html string | getEncodedHtml(): ?string | setEncodedHtml(?string encodedHtml): void |
| `encodedHtmlPopup` | `?string` | Optional | Base64 encoded popup html string | getEncodedHtmlPopup(): ?string | setEncodedHtmlPopup(?string encodedHtmlPopup): void |
| `url` | `?string` | Optional | URL for redirecting the customer for creating<br>the mandate.<br><br>**Constraints**: *Maximum Length*: `2048` | getUrl(): ?string | setUrl(?string url): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation7 = AgreementInformation7Builder::init()
    ->id('id4')
    ->dateSigned('dateSigned4')
    ->dateCreated('dateCreated4')
    ->encodedHtml('encodedHtml8')
    ->encodedHtmlPopup('encodedHtmlPopup8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

