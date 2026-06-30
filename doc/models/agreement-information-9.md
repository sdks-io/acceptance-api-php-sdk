
# Agreement Information 9

*This model accepts additional fields of type array.*

## Structure

`AgreementInformation9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Identifier for the mandate.<br><br>**Constraints**: *Maximum Length*: `50` | getId(): ?string | setId(?string id): void |
| `dateSigned` | `?string` | Optional | Date the mandate has been signed.  Format YYYYMMdd<br><br>**Constraints**: *Maximum Length*: `8` | getDateSigned(): ?string | setDateSigned(?string dateSigned): void |
| `dateCreated` | `?string` | Optional | Date the mandate has been created.  Format YYYYMMdd<br><br>**Constraints**: *Maximum Length*: `8` | getDateCreated(): ?string | setDateCreated(?string dateCreated): void |
| `dateRevoked` | `?string` | Optional | Date the mandate has been revoked.  Format YYYYMMdd<br><br>**Constraints**: *Maximum Length*: `8` | getDateRevoked(): ?string | setDateRevoked(?string dateRevoked): void |
| `encodedHtml` | `?string` | Optional | Base64 encoded html string | getEncodedHtml(): ?string | setEncodedHtml(?string encodedHtml): void |
| `encodedHtmlPopup` | `?string` | Optional | Base64 encoded popup html string | getEncodedHtmlPopup(): ?string | setEncodedHtmlPopup(?string encodedHtmlPopup): void |
| `url` | `?string` | Optional | URL for redirecting the customer for creating<br>the mandate.<br><br>**Constraints**: *Maximum Length*: `2048` | getUrl(): ?string | setUrl(?string url): void |
| `transactionId` | `?string` | Optional | The Billing Agreement ID returned by processor (PayPal).<br><br>**Constraints**: *Maximum Length*: `50` | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agreementInformation9 = AgreementInformation9Builder::init()
    ->id('id6')
    ->dateSigned('dateSigned4')
    ->dateCreated('dateCreated2')
    ->dateRevoked('dateRevoked4')
    ->encodedHtml('encodedHtml6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

