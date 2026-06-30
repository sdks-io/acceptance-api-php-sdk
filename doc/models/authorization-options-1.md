
# Authorization Options 1

*This model accepts additional fields of type array.*

## Structure

`AuthorizationOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `panReturnIndicator` | `?string` | Optional | #### Visa Platform Connect<br><br>The field contains the PAN translation indicator for American Express Contactless Transaction. Valid value is<br><br>1- Expresspay Translation, PAN request<br>2- Expresspay Translation, PAN and Expiry date request<br><br>**Constraints**: *Maximum Length*: `1` | getPanReturnIndicator(): ?string | setPanReturnIndicator(?string panReturnIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationOptions1 = AuthorizationOptions1Builder::init()
    ->panReturnIndicator('panReturnIndicator4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

