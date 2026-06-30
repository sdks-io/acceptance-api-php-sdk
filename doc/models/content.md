
# Content

*This model accepts additional fields of type array.*

## Structure

`Content`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | The MIME type of the Asset. | getType(): ?string | setType(?string type): void |
| `data` | `?string` | Optional | The base64-encoded data of the Asset. | getData(): ?string | setData(?string data): void |
| `width` | `?int` | Optional | The width of the Asset in pixels. | getWidth(): ?int | setWidth(?int width): void |
| `height` | `?int` | Optional | The height of the Asset in pixels. | getHeight(): ?int | setHeight(?int height): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ContentBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$content = ContentBuilder::init()
    ->type('image/png')
    ->data('iVBORw0KGgoAAAANSUhEUgAA...')
    ->width(1536)
    ->height(969)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

