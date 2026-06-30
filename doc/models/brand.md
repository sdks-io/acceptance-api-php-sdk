
# Brand

*This model accepts additional fields of type array.*

## Structure

`Brand`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | This field contains a 3-digit numeric value that indicates the card type within Visa Acceptance eco-system.<br>Possible values from BIN Lookup Service (based on availability and enablement):<br><br>- `000`: Unsupported Card Type<br>- `001`: Visa<br>- `002`: Mastercard<br>- `003`: American Express<br>- `004`: Discover<br>- `005`: Diners Club<br>- `007`: JCB<br>- `036`: Cartes Bancaire<br>- `042`: Maestro<br>- `054`: Elo<br>- `058`: Carnet<br>- `060`: MADA<br>- `061`: RuPay<br>- `062`: China UnionPay<br>- `064`: Prompt Card<br>- `067`: Meeza<br>- `068`: PayPak<br>- `070`: EFTPOS<br>- `081`: Jaywan<br>- `082`: TPN<br><br>Glossary of possible values in the payments ecosystem:<br><br>- `001`: Visa<br>- `002`: Mastercard<br>- `003`: American Express<br>- `004`: Discover<br>- `005`: Diners Club<br>- `006`: Carte Blanche<br>- `007`: JCB<br>- `008`: Optima<br>- `009`: GE Private Label<br>- `010`: Beneficial Private Label<br>- `011`: Twinpay Credit Card<br>- `012`: Twinpay Debit Card<br>- `013`: Walmart<br>- `014`: EnRoute<br>- `015`: Lowe's Consumer<br>- `016`: Home Depot Consumer<br>- `017`: MBNA<br>- `018`: Dick's Sportwear<br>- `019`: Casual Corner<br>- `020`: Sears<br>- `021`: JAL<br>- `023`: Disney Card<br>- `024`: Switch/Solo<br>- `025`: Sam's Club Consumer<br>- `026`: Sam's Club Business<br>- `027`: Nico's<br>- `028`: Paymentech Bill Me Later<br>- `029`: Bebe<br>- `030`: Restoration Hardware<br>- `031`: Delta Online<br>- `032`: Solo<br>- `033`: Visa Electron<br>- `034`: Dankort<br>- `035`: Laser<br>- `036`: Cartes Bancaire<br>- `037`: Carta Si<br>- `040`: UATP<br>- `041`: HOUSEHOLD<br>- `042`: Maestro<br>- `043`: GE MONEY<br>- `044`: Korean Cards<br>- `045`: Style Cards<br>- `046`: J.Crew<br>- `047`: Payeasecn eWallet<br>- `048`: Payeasecn Bank Transfer<br>- `049`: Meijer<br>- `050`: Hipercard<br>- `051`: Aura<br>- `052`: Redecard<br>- `053`: Orico Card<br>- `054`: Elo<br>- `055`: Capital One Private Label<br>- `057`: Costco Private Label<br>- `058`: Carnet<br>- `059`: ValueLink<br>- `060`: MADA<br>- `061`: RuPay<br>- `062`: China UnionPay<br>- `063`: Falabella Private Label<br>- `064`: Prompt Card<br>- `065`: Korean Domestic<br>- `066`: Banricompras<br>- `067`: Meeza<br>- `068`: PayPak<br>- `070`: EFTPOS<br>- `071`: Codensa<br>- `072`: Olimpica<br>- `073`: Colsubsidio<br>- `074`: Tuya<br>- `075`: Sodexo<br>- `076`: Naranja<br>- `077`: Cabal<br>- `078`: DINELCO<br>- `079`: PANAL<br>- `080`: EPM<br>- `081`: Jaywan<br>- `082`: TPN<br><br>**Constraints**: *Maximum Length*: `3` | getType(): ?string | setType(?string type): void |
| `brandName` | `?string` | Optional | This field contains the card brand name.<br><br>Some of the possible values (not an exhaustive list) are -<br><br>- VISA<br>- MASTERCARD<br>- AMERICAN EXPRESS<br>- DISCOVER<br>- DINERS CLUB<br>- CARTE BLANCHE<br>- JCB<br>- OPTIMA<br>- TWINPAY CREDIT CARD<br>- TWINPAY DEBIT CARD<br>- WALMART<br>- ENROUTE<br>- LOWES CONSUMER<br>- HOME DEPOT CONSUMER<br>- MBNA<br>- DICKS SPORTWEAR<br>- CASUAL CORNER<br>- SEARS<br>- JAL<br>- DISNEY CARD<br>- SWITCH/SOLO<br>- SAMS CLUB CONSUMER<br>- SAMS CLUB BUSINESS<br>- NICOS HOUSE CARD<br>- BEBE<br>- RESTORATION HARDWARE<br>- DELTA ONLINE<br>- SOLO<br>- VISA ELECTRON<br>- DANKORT<br>- LASER<br>- CARTE BANCAIRE<br>- CARTA SI<br>- ENCODED ACCOUNT<br>- UATP<br>- HOUSEHOLD<br>- MAESTRO<br>- GE CAPITAL<br>- KOREAN CARDS<br>- STYLE CARDS<br>- JCREW<br>- MEIJER<br>- HIPERCARD<br>- AURA<br>- REDECARD<br>- ORICO HOUSE CARD<br>- MADA<br>- ELO<br>- CAPITAL ONE PRIVATE LABEL<br>- CARNET<br>- RUPAY<br>- CHINA UNION PAY<br>- FALABELLA PRIVATE LABEL<br>- PROMPTCARD<br>- KOREAN DOMESTIC<br>- BANRICOMPRAS<br>- MEEZA<br>- PAYPAK<br>- JAYWAN<br>- TPN<br><br>**Constraints**: *Maximum Length*: `20` | getBrandName(): ?string | setBrandName(?string brandName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BrandBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$brand = BrandBuilder::init()
    ->type('type6')
    ->brandName('brandName0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

