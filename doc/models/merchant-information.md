
# Merchant Information

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantDescriptor` | [`?MerchantDescriptor`](../../doc/models/merchant-descriptor.md) | Optional | - | getMerchantDescriptor(): ?MerchantDescriptor | setMerchantDescriptor(?MerchantDescriptor merchantDescriptor): void |
| `domainName` | `?string` | Optional | This field will contain either the merchant url or the reverse domain as per the requirement for DSRP Format 3. This might vary transaction to transaction and might not be static. Merchant needs to have access to send this value for all DSRP program.<br><br>**Constraints**: *Maximum Length*: `127` | getDomainName(): ?string | setDomainName(?string domainName): void |
| `salesOrganizationId` | `?string` | Optional | Company ID assigned to an independent sales organization. Get this value from Mastercard.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCR6<br>- Position: 106-116<br>- Field: Independent Sales Organization ID<br><br>This field is supported for Visa, Mastercard and Discover Transactions.<br><br>**Note** The TC 33 Capture file contains information about the purchases and refunds that a merchant submits to Visa Acceptance. Visa Acceptance through VisaNet creates the TC 33 Capture file at the end of the day and sends it to the merchant’s acquirer, who uses this information to facilitate end-of-day clearing processing with payment card companies.<br><br>**Constraints**: *Maximum Length*: `11` | getSalesOrganizationId(): ?string | setSalesOrganizationId(?string salesOrganizationId): void |
| `categoryCode` | `?int` | Optional | The value for this field is a four-digit number that the payment card industry uses to classify<br>merchants into market segments. A payment card company assigned one or more of these values to your business when you started<br>accepting the payment card company’s cards. When you do not include this field in your request, Visa Acceptance uses the value in your<br>Visa Acceptance account.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCR4<br>- Position: 150-153<br>- Field: Merchant Category Code<br><br>**Constraints**: `<= 9999` | getCategoryCode(): ?int | setCategoryCode(?int categoryCode): void |
| `categoryCodeDomestic` | `?int` | Optional | Merchant category code for domestic transactions. The value for this field is a four-digit number that the payment<br>card industry uses to classify merchants into market segments. A payment card company assigned one or more of these<br>values to your business when you started accepting the payment card company’s cards. Including this field in a request<br>for a domestic transaction might reduce interchange fees.<br><br>When you include this field in a request:<br><br>- Do not include the `merchant_category_code` field.<br>- The value for this field overrides the value in your Visa Acceptance account.<br><br>This field is supported only for:<br><br>- Domestic transactions with Mastercard in Spain. Domestic means that you and the cardholder are in the same country.<br>- Merchants enrolled in the OmniPay Direct interchange program.<br>- First Data Merchant Solutions (Europe) on OmniPay Direct.<br><br>**Constraints**: `<= 9999` | getCategoryCodeDomestic(): ?int | setCategoryCodeDomestic(?int categoryCodeDomestic): void |
| `taxId` | `?string` | Optional | Your Cadastro Nacional da Pessoa Jurídica (CNPJ) number.<br><br>This field is supported only for BNDES transactions on Visa Acceptance through VisaNet.<br><br>The value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP07 TCR6<br>- Position: 40-59<br>- Field: BNDES Reference Field 1<br><br>**Constraints**: *Maximum Length*: `15` | getTaxId(): ?string | setTaxId(?string taxId): void |
| `vatRegistrationNumber` | `?string` | Optional | Your government-assigned tax identification number.<br><br>#### Tax Calculation<br><br>Required field for value added tax only. Not applicable to U.S. and Canadian taxes.<br><br>#### Visa Acceptance through VisaNet<br><br>For CtV processors, the maximum length is 20.<br><br>**Constraints**: *Maximum Length*: `21` | getVatRegistrationNumber(): ?string | setVatRegistrationNumber(?string vatRegistrationNumber): void |
| `cardAcceptorReferenceNumber` | `?string` | Optional | Reference number that facilitates card acceptor/corporation communication and record keeping.<br><br>**Constraints**: *Maximum Length*: `25` | getCardAcceptorReferenceNumber(): ?string | setCardAcceptorReferenceNumber(?string cardAcceptorReferenceNumber): void |
| `transactionLocalDateTime` | `?string` | Optional | Date and time at your physical location.<br><br>Format: `YYYYMMDDhhmmss`, where:<br><br>- `YYYY` = year<br>- `MM` = month<br>- `DD` = day<br>- `hh` = hour<br>- `mm` = minutes<br>- `ss` = seconds<br><br>#### Used by<br><br>**Authorization**<br>Required for these processors:<br><br>- American Express Direct                                                                                                                                                                                                                                                                                                                         - American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br><br>Optional for all other processors.<br><br>**Constraints**: *Maximum Length*: `14` | getTransactionLocalDateTime(): ?string | setTransactionLocalDateTime(?string transactionLocalDateTime): void |
| `serviceFeeDescriptor` | [`?ServiceFeeDescriptor`](../../doc/models/service-fee-descriptor.md) | Optional | - | getServiceFeeDescriptor(): ?ServiceFeeDescriptor | setServiceFeeDescriptor(?ServiceFeeDescriptor serviceFeeDescriptor): void |
| `cancelUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getCancelUrl(): ?string | setCancelUrl(?string cancelUrl): void |
| `successUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getSuccessUrl(): ?string | setSuccessUrl(?string successUrl): void |
| `failureUrl` | `?string` | Optional | customer would be redirected to this url based on the decision of the transaction<br><br>**Constraints**: *Maximum Length*: `255` | getFailureUrl(): ?string | setFailureUrl(?string failureUrl): void |
| `returnUrl` | `?string` | Optional | URL for displaying payment results to the consumer (notifications) after the transaction is processed. Usually this URL belongs to merchant and its behavior is defined by merchant<br><br>**Constraints**: *Minimum Length*: `7`, *Maximum Length*: `255` | getReturnUrl(): ?string | setReturnUrl(?string returnUrl): void |
| `partnerIdCode` | `?string` | Optional | #### Visa Platform Connect<br><br>This field may be used for transactions on accounts issued under co-branding agreements when one of the<br>co-branding partners.<br><br>**Constraints**: *Maximum Length*: `10` | getPartnerIdCode(): ?string | setPartnerIdCode(?string partnerIdCode): void |
| `serviceLocation` | [`?ServiceLocation`](../../doc/models/service-location.md) | Optional | - | getServiceLocation(): ?ServiceLocation | setServiceLocation(?ServiceLocation serviceLocation): void |
| `noteToBuyer` | `?string` | Optional | Free-form text field.<br><br>**Constraints**: *Maximum Length*: `165` | getNoteToBuyer(): ?string | setNoteToBuyer(?string noteToBuyer): void |
| `merchantName` | `?string` | Optional | Use this field only if you are requesting payment with Payer Authentication serice together.<br><br>Your company’s name as you want it to appear to the customer in the issuing bank’s authentication form.<br>This value overrides the value specified by your merchant bank.<br><br>**Constraints**: *Maximum Length*: `25` | getMerchantName(): ?string | setMerchantName(?string merchantName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation = MerchantInformationBuilder::init()
    ->merchantDescriptor(
        MerchantDescriptorBuilder::init()
            ->name('name2')
            ->alternateName('alternateName0')
            ->contact('contact0')
            ->address1('address10')
            ->locality('locality2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->domainName('domainName8')
    ->salesOrganizationId('salesOrganizationId2')
    ->categoryCode(8999)
    ->categoryCodeDomestic(8999)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

