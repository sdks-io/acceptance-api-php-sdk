
# Risk Information 22

*This model accepts additional fields of type array.*

## Structure

`RiskInformation22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `profile` | [`?Profile1`](../../doc/models/profile-1.md) | Optional | - | getProfile(): ?Profile1 | setProfile(?Profile1 profile): void |
| `rules` | [`?(Rule[])`](../../doc/models/rule.md) | Optional | - | getRules(): ?array | setRules(?array rules): void |
| `infoCodes` | [`?InfoCodes`](../../doc/models/info-codes.md) | Optional | - | getInfoCodes(): ?InfoCodes | setInfoCodes(?InfoCodes infoCodes): void |
| `velocity` | [`?Velocity`](../../doc/models/velocity.md) | Optional | - | getVelocity(): ?Velocity | setVelocity(?Velocity velocity): void |
| `casePriority` | `?int` | Optional | You receive this field only if you subscribe to the Enhanced Case Management service. The priority level ranges from 1 (highest) to 5 (lowest); the default value is 3. If you do not assign a priority to your rules or to your profiles, the default value is given to the order.<br><br>For all possible values, see the `decision_case_priority` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link). | getCasePriority(): ?int | setCasePriority(?int casePriority): void |
| `localTime` | `?string` | Optional | The customer's local time (`hh:mm:ss`), which is calculated from the transaction request time and the<br>customer's billing address.<br><br>For details, see the `score_time_local` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.](<br><br>**Constraints**: *Maximum Length*: `255` | getLocalTime(): ?string | setLocalTime(?string localTime): void |
| `score` | [`?Score`](../../doc/models/score.md) | Optional | - | getScore(): ?Score | setScore(?Score score): void |
| `ipAddress` | [`?IpAddress2`](../../doc/models/ip-address-2.md) | Optional | - | getIpAddress(): ?IpAddress2 | setIpAddress(?IpAddress2 ipAddress): void |
| `providers` | `?array<string,string>` | Optional | Name of the 3rd party provider, for example, Emailage.<br>For all possible values, see the `decision_provider_#_name` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link). | getProviders(): ?array | setProviders(?array providers): void |
| `travel` | [`?Travel`](../../doc/models/travel.md) | Optional | - | getTravel(): ?Travel | setTravel(?Travel travel): void |
| `processorResults` | [`?ProcessorResults`](../../doc/models/processor-results.md) | Optional | - | getProcessorResults(): ?ProcessorResults | setProcessorResults(?ProcessorResults processorResults): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RiskInformation22Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Profile1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\RuleBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InfoCodesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\VelocityBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MorphingBuilder;

$riskInformation22 = RiskInformation22Builder::init()
    ->profile(
        Profile1Builder::init()
            ->name('name0')
            ->desinationQueue('desinationQueue6')
            ->selectorRule('selectorRule8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->rules(
        [
            RuleBuilder::init()
                ->name('name8')
                ->decision('decision4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            RuleBuilder::init()
                ->name('name8')
                ->decision('decision4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            RuleBuilder::init()
                ->name('name8')
                ->decision('decision4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->infoCodes(
        InfoCodesBuilder::init()
            ->velocity(
                [
                    'velocity8',
                    'velocity9',
                    'velocity0'
                ]
            )
            ->address(
                [
                    'address8',
                    'address9',
                    'address0'
                ]
            )
            ->customerList(
                [
                    'customerList1'
                ]
            )
            ->deviceBehavior(
                [
                    'deviceBehavior1'
                ]
            )
            ->identityChange(
                [
                    'identityChange2',
                    'identityChange3'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->velocity(
        VelocityBuilder::init()
            ->morphing(
                [
                    MorphingBuilder::init()
                        ->count(234)
                        ->fieldName('fieldName4')
                        ->informationCode('informationCode8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    MorphingBuilder::init()
                        ->count(234)
                        ->fieldName('fieldName4')
                        ->informationCode('informationCode8')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->address(
                [
                    'address0'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->casePriority(190)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

