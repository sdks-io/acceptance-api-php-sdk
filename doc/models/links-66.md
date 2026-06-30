
# Links 66

*This model accepts additional fields of type array.*

## Structure

`Links66`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self65`](../../doc/models/self-65.md) | Optional, Read-only | - | getSelf(): ?Self65 | setSelf(?Self65 self): void |
| `first` | [`?First`](../../doc/models/first.md) | Optional, Read-only | - | getFirst(): ?First | setFirst(?First first): void |
| `prev` | [`?Prev`](../../doc/models/prev.md) | Optional, Read-only | - | getPrev(): ?Prev | setPrev(?Prev prev): void |
| `next` | [`?Next`](../../doc/models/next.md) | Optional, Read-only | - | getNext(): ?Next | setNext(?Next next): void |
| `last` | [`?Last`](../../doc/models/last.md) | Optional, Read-only | - | getLast(): ?Last | setLast(?Last last): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links66Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self65Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PrevBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\NextBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LastBuilder;

$links66 = Links66Builder::init()
    ->self(
        Self65Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->first(
        FirstBuilder::init()
            ->href('href2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->prev(
        PrevBuilder::init()
            ->href('href8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->next(
        NextBuilder::init()
            ->href('href4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->last(
        LastBuilder::init()
            ->href('href2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

