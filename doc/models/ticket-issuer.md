
# Ticket Issuer

*This model accepts additional fields of type array.*

## Structure

`TicketIssuer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | IATA2 airline code.<br>Format: English characters only.<br>Required for Mastercard; optional for all other card types.<br><br>**Constraints**: *Maximum Length*: `4` | getCode(): ?string | setCode(?string code): void |
| `name` | `?string` | Optional | Name of the ticket issuer. If you do not include this field,<br>Visa Acceptance uses the value for your merchant name that is in the Visa Acceptance merchant configuration database.<br><br>**Constraints**: *Maximum Length*: `20` | getName(): ?string | setName(?string name): void |
| `address` | `?string` | Optional | Address of the company issuing the ticket.<br><br>**Constraints**: *Maximum Length*: `16` | getAddress(): ?string | setAddress(?string address): void |
| `locality` | `?string` | Optional | City in which the transaction occurred.<br>If the name of the city exceeds 18 characters, use meaningful abbreviations.<br>Format: English characters only.<br>Optional request field.<br><br>**Constraints**: *Maximum Length*: `18` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State in which transaction occured.<br><br>**Constraints**: *Maximum Length*: `18` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Zip code of the city in which transaction occured.<br><br>**Constraints**: *Maximum Length*: `15` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country in which transaction occured.<br><br>**Constraints**: *Maximum Length*: `18` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TicketIssuerBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$ticketIssuer = TicketIssuerBuilder::init()
    ->code('code2')
    ->name('name4')
    ->address('address0')
    ->locality('locality6')
    ->administrativeArea('administrativeArea0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

