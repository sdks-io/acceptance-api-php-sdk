
# Hosted Payment Information

*This model accepts additional fields of type array.*

## Structure

`HostedPaymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hostName` | `?string` | Optional | The title of the hosted payment page, displayed in the browser’s tab. If<br>not set, defaults to the title set in the merchant configuration.<br><br>**Constraints**: *Maximum Length*: `255` | getHostName(): ?string | setHostName(?string hostName): void |
| `ipAddress` | `?string` | Optional | URL of the merchant’s logo to be displayed in Klarna’s hosted payment<br>page. If not set, defaults to the logo set in the merchant configuration.<br><br>**Constraints**: *Maximum Length*: `255` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `userAgent` | [`?UserAgent2`](../../doc/models/user-agent-2.md) | Optional | - | getUserAgent(): ?UserAgent2 | setUserAgent(?UserAgent2 userAgent): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\HostedPaymentInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\UserAgent2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$hostedPaymentInformation = HostedPaymentInformationBuilder::init()
    ->hostName('hostName4')
    ->ipAddress('ipAddress0')
    ->userAgent(
        UserAgent2Builder::init()
            ->url('url0')
            ->width(200)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

