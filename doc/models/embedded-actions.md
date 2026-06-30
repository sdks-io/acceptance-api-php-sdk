
# Embedded Actions

Contains embedded actions, that includes status and response for every actions in the list.

*This model accepts additional fields of type array.*

## Structure

`EmbeddedActions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capture` | [`?Capture1`](../../doc/models/capture-1.md) | Optional | - | getCapture(): ?Capture1 | setCapture(?Capture1 capture): void |
| `decision` | [`?Decision`](../../doc/models/decision.md) | Optional | - | getDecision(): ?Decision | setDecision(?Decision decision): void |
| `consumerAuthentication` | [`?Consumerauthentication`](../../doc/models/consumerauthentication.md) | Optional | - | getConsumerAuthentication(): ?Consumerauthentication | setConsumerAuthentication(?Consumerauthentication consumerAuthentication): void |
| `validateConsumerAuthentication` | [`?Validateconsumerauthentication`](../../doc/models/validateconsumerauthentication.md) | Optional | - | getValidateConsumerAuthentication(): ?Validateconsumerauthentication | setValidateConsumerAuthentication(?Validateconsumerauthentication validateConsumerAuthentication): void |
| `watchlistScreening` | [`?Watchlistscreening`](../../doc/models/watchlistscreening.md) | Optional | - | getWatchlistScreening(): ?Watchlistscreening | setWatchlistScreening(?Watchlistscreening watchlistScreening): void |
| `tokenCreate` | [`?Tokencreate`](../../doc/models/tokencreate.md) | Optional | - | getTokenCreate(): ?Tokencreate | setTokenCreate(?Tokencreate tokenCreate): void |
| `tokenUpdate` | [`?Tokenupdate`](../../doc/models/tokenupdate.md) | Optional | - | getTokenUpdate(): ?Tokenupdate | setTokenUpdate(?Tokenupdate tokenUpdate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EmbeddedActionsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Capture1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\DecisionBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ConsumerauthenticationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ValidateconsumerauthenticationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchlistscreeningBuilder;

$embeddedActions = EmbeddedActionsBuilder::init()
    ->capture(
        Capture1Builder::init()
            ->status('status8')
            ->reason('reason4')
            ->message('message0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->decision(
        DecisionBuilder::init()
            ->status('status4')
            ->reason('reason8')
            ->message('message2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->consumerAuthentication(
        ConsumerauthenticationBuilder::init()
            ->status('status0')
            ->reason('reason4')
            ->message('message8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->validateConsumerAuthentication(
        ValidateconsumerauthenticationBuilder::init()
            ->status('status8')
            ->reason('reason2')
            ->message('message6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->watchlistScreening(
        WatchlistscreeningBuilder::init()
            ->status('status8')
            ->reason('reason4')
            ->message('message0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

