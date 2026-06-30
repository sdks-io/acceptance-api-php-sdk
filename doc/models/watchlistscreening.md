
# Watchlistscreening

*This model accepts additional fields of type array.*

## Structure

`Watchlistscreening`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status for the call can be:<br><br>- COMPLETED<br>- INVALID_REQUEST<br>- DECLINED | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status. Value can be<br><br>- `CUSTOMER_WATCHLIST_MATCH`<br>- `ADDRESS_COUNTRY_WATCHLIST_MATCH`<br>- `EMAIL_COUNTRY_WATCHLIST_MATCH`<br>- `IP_COUNTRY_WATCHLIST_MATCH`<br>- `INVALID_MERCHANT_CONFIGURATION` | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The message describing the reason of the status. Value can be<br><br>- The customer matched the Denied Parties List<br>- The Export bill_country/ship_country  match<br>- Export email_country match<br>- Export hostname_country/ip_country match | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchlistscreeningBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$watchlistscreening = WatchlistscreeningBuilder::init()
    ->status('status2')
    ->reason('reason4')
    ->message('message0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

