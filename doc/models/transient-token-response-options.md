
# Transient Token Response Options

*This model accepts additional fields of type array.*

## Structure

`TransientTokenResponseOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `includeCardPrefix` | `?bool` | Optional | Use the transientTokenResponseOptions.includeCardPrefix field to choose your preferred card number prefix length: 6-digit, 8-digit, or no card number prefix.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>To select the type of card number prefix:<br><br>- No field included: A 6-digit prefix is returned (default)<br>- True: An 8-digit prefix is returned<br>- False: No prefix is returned<br><br><br><br>The following conditions apply:<br><br>- 8-digit card number prefixes only apply to Discover, JCB, Mastercard, UnionPay, and Visa brands with 16-digit card numbers or more.<br>- Any card with less than 16-digit numbers will return a 6-digit prefix even when the transientTokenResponseOptions.includeCardPrefix field is set to true.<br>- Any card brand other than Discover, JCB, Mastercard, UnionPay, or Visa will return a 6-digit prefix even when the transientTokenResponseOptions.includeCardPrefix field is set to true.<br>- If any card brand is co-branded with Discover, JCB, Mastercard, UnionPay, or Visa, an 8-digit prefix will be returned if the transientTokenResponseOptions.includeCardPrefix field is set to true.<br><br><br><br>**Important:**<br>If your application does NOT require a card number prefix for routing or identification purposes, set the transientTokenResponseOptions.includeCardPrefix field to False.  This will minimize your personal data exposure. | getIncludeCardPrefix(): ?bool | setIncludeCardPrefix(?bool includeCardPrefix): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TransientTokenResponseOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$transientTokenResponseOptions = TransientTokenResponseOptionsBuilder::init()
    ->includeCardPrefix(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

