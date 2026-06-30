
# Direct Debit Sepa

*This model accepts additional fields of type array.*

## Structure

`DirectDebitSepa`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reference` | `?string` | Optional | Mandate reference as returned on the first transaction in the<br>sequence<br><br>**Constraints**: *Maximum Length*: `255` | getReference(): ?string | setReference(?string reference): void |
| `signatureDate` | `?string` | Optional | Date of the initial transaction, format is YYYY-MM-DD. Date<br>can be taken from the finaltimestamp of the SUCCEEDED<br>notification for the first transaction in the sequence.<br><br>**Constraints**: *Maximum Length*: `255` | getSignatureDate(): ?string | setSignatureDate(?string signatureDate): void |
| `url` | `?string` | Optional | Valid URL pointing to the SEPA mandate, needs to be accessible<br>by our risk and compliance department.<br><br>**Constraints**: *Maximum Length*: `255` | getUrl(): ?string | setUrl(?string url): void |
| `type` | `?string` | Optional | Sequence type of the direct debit, defaults to “oneOff”. Valid<br>values:<br>oneOff The direct debit is executed once.<br>first First direct debit in a series of recurring ones.<br><br>**Constraints**: *Maximum Length*: `255` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DirectDebitSepaBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$directDebitSepa = DirectDebitSepaBuilder::init()
    ->reference('reference4')
    ->signatureDate('signatureDate4')
    ->url('url4')
    ->type('type0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

