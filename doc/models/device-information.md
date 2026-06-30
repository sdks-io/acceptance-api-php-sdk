
# Device Information

*This model accepts additional fields of type array.*

## Structure

`DeviceInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Value created by the client software that uniquely identifies the POS device.<br>Visa Acceptance does not forward this value to the processor. Instead, the value is forwarded to<br>the Visa Acceptance reporting functionality.<br><br>This field is supported only for authorizations and credits on these processors:<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- OmniPay Direct<br>- SIX<br><br>Optional field.<br>String (32) | getId(): ?string | setId(?string id): void |
| `hostName` | `?string` | Optional | DNS resolved hostname from `ipAddress`.<br><br>**Constraints**: *Maximum Length*: `60` | getHostName(): ?string | setHostName(?string hostName): void |
| `ipAddress` | `?string` | Optional | IP address of the customer.<br><br>#### Used by<br><br>**Authorization, Capture, and Credit**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `45` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `userAgent` | `?string` | Optional | Customer’s browser as identified from the HTTP header data. For example, `Mozilla` is the value that identifies<br>the Netscape browser.<br><br>**Constraints**: *Maximum Length*: `40` | getUserAgent(): ?string | setUserAgent(?string userAgent): void |
| `fingerprintSessionId` | `?string` | Optional | Field that contains the session ID that you send to Decision Manager to obtain the device fingerprint<br>information. The string can contain uppercase and lowercase letters, digits, hyphen (-), and<br>underscore (_). However, do not use the same uppercase and lowercase letters to indicate<br>different session IDs.<br><br>The session ID must be unique for each merchant ID. You can use any string that you are already<br>generating, such as an order number or web session ID.<br><br>The session ID must be unique for each page load, regardless of an individual’s web session ID.<br>If a user navigates to a profiled page and is assigned a web session, navigates away from the<br>profiled page, then navigates back to the profiled page, the generated session ID should be different<br>and unique. You may use a web session ID, but it is preferable to use an application GUID (Globally<br>Unique Identifier). This measure ensures that a unique ID is generated every time the page is<br>loaded, even if it is the same user reloading the page. | getFingerprintSessionId(): ?string | setFingerprintSessionId(?string fingerprintSessionId): void |
| `useRawFingerprintSessionId` | `?bool` | Optional, Read-only | Boolean that indicates whether request contains the device fingerprint information.<br>Values:<br><br>- `true`: Use raw fingerprintSessionId when looking up device details.<br>- `false` (default): Use merchant id + fingerprintSessionId as the session id for Device detail collection. | getUseRawFingerprintSessionId(): ?bool | setUseRawFingerprintSessionId(?bool useRawFingerprintSessionId): void |
| `deviceType` | `?string` | Optional | The device type at the client side.<br><br>**Constraints**: *Maximum Length*: `60` | getDeviceType(): ?string | setDeviceType(?string deviceType): void |
| `appUrl` | `?string` | Optional | This field will contain the deep link that would help the Customer App to wake up. | getAppUrl(): ?string | setAppUrl(?string appUrl): void |
| `metadata` | `?string` | Optional | Verifies that the payment is originating from a valid, user-approved application and device. Sending this field helps reduce fraud and declined transactions.<br>Note The length is set for a hexadecimal representation of the GUID/UUID. This field accepts a 36-character string (with hyphens) or a 32-character string (without hyphens).<br>Example 123e4567-e89b-12d3-a456-426655440000<br>Example 123e4567e89b12d3a456426655440000<br><br>**Constraints**: *Maximum Length*: `36` | getMetadata(): ?string | setMetadata(?string metadata): void |
| `rawData` | [`?(RawDatum[])`](../../doc/models/raw-datum.md) | Optional | - | getRawData(): ?array | setRawData(?array rawData): void |
| `httpAcceptBrowserValue` | `?string` | Optional | Value of the Accept header sent by the customer’s web browser.<br>**Note** If the customer’s browser provides a value, you must include it in your request.<br><br>**Constraints**: *Maximum Length*: `255` | getHttpAcceptBrowserValue(): ?string | setHttpAcceptBrowserValue(?string httpAcceptBrowserValue): void |
| `httpAcceptContent` | `?string` | Optional | The exact content of the HTTP accept header.<br><br>**Constraints**: *Maximum Length*: `256` | getHttpAcceptContent(): ?string | setHttpAcceptContent(?string httpAcceptContent): void |
| `httpBrowserEmail` | `?string` | Optional | Email address set in the customer’s browser, which may differ from customer email. | getHttpBrowserEmail(): ?string | setHttpBrowserEmail(?string httpBrowserEmail): void |
| `httpBrowserLanguage` | `?string` | Optional | Value represents the browser language as defined in IETF BCP47.<br>Example:en-US, refer   for more details.<br><br>**Constraints**: *Maximum Length*: `8` | getHttpBrowserLanguage(): ?string | setHttpBrowserLanguage(?string httpBrowserLanguage): void |
| `httpBrowserJavaEnabled` | `?bool` | Optional | A Boolean value that represents the ability of the cardholder browser to execute Java.<br>Value is returned from the navigator.javaEnabled property. Possible Values:True/False | getHttpBrowserJavaEnabled(): ?bool | setHttpBrowserJavaEnabled(?bool httpBrowserJavaEnabled): void |
| `httpBrowserJavaScriptEnabled` | `?bool` | Optional | A Boolean value that represents the ability of the cardholder browser to execute JavaScript. Possible Values:True/False.<br>**Note**: Merchants should be able to know the values from fingerprint details of cardholder's browser. | getHttpBrowserJavaScriptEnabled(): ?bool | setHttpBrowserJavaScriptEnabled(?bool httpBrowserJavaScriptEnabled): void |
| `httpBrowserColorDepth` | `?string` | Optional | Value represents the bit depth of the color palette for displaying images, in bits per pixel.<br>Example : 24, refer  for more details<br><br>**Constraints**: *Maximum Length*: `2` | getHttpBrowserColorDepth(): ?string | setHttpBrowserColorDepth(?string httpBrowserColorDepth): void |
| `httpBrowserScreenHeight` | `?string` | Optional | Total height of the Cardholder's scree in pixels, example: 864.<br><br>**Constraints**: *Maximum Length*: `6` | getHttpBrowserScreenHeight(): ?string | setHttpBrowserScreenHeight(?string httpBrowserScreenHeight): void |
| `httpBrowserScreenWidth` | `?string` | Optional | Total width of the cardholder's screen in pixels. Example: 1536.<br><br>**Constraints**: *Maximum Length*: `6` | getHttpBrowserScreenWidth(): ?string | setHttpBrowserScreenWidth(?string httpBrowserScreenWidth): void |
| `httpBrowserTimeDifference` | `?string` | Optional | Time difference between UTC time and the cardholder browser local time, in minutes, Example:300<br><br>**Constraints**: *Maximum Length*: `5` | getHttpBrowserTimeDifference(): ?string | setHttpBrowserTimeDifference(?string httpBrowserTimeDifference): void |
| `userAgentBrowserValue` | `?string` | Optional | Value of the User-Agent header sent by the customer’s web browser.<br>Note If the customer’s browser provides a value, you must include it in your request.<br><br>**Constraints**: *Maximum Length*: `255` | getUserAgentBrowserValue(): ?string | setUserAgentBrowserValue(?string userAgentBrowserValue): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$deviceInformation = DeviceInformationBuilder::init()
    ->id('id6')
    ->hostName('hostName8')
    ->ipAddress('ipAddress6')
    ->userAgent('userAgent2')
    ->fingerprintSessionId('fingerprintSessionId4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

