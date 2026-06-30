
# Account Features

*This model accepts additional fields of type array.*

## Structure

`AccountFeatures`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountType` | `?string` | Optional | Type of account. This value is returned only if you requested a balance inquiry. Possible values:<br><br>- `00`: Not applicable or not specified<br>- `10`: Savings account<br>- `20`: Checking account<br>- `30`: Credit card account<br>- `40`: Universal account<br><br>#### PIN debit<br><br>Type of account. This value is returned only if you requested a balance inquiry.<br><br>Possible values:<br><br>- `00`: Not applicable or not specified<br>- `10`: Savings account<br>- `20`: Checking account<br>- `40`: Universal account<br>- `96`: Cash benefits account<br>- `98`: Food stamp account<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `2` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `accountStatus` | `?string` | Optional | Possible values:<br><br>- `N`: Nonregulated<br>- `R`: Regulated<br><br>Returned by PIN debit credit or PIN debit purchase.<br><br>**Note** This field is returned only for Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `1` | getAccountStatus(): ?string | setAccountStatus(?string accountStatus): void |
| `balances` | [`?(Balance[])`](../../doc/models/balance.md) | Optional | This is an array of multiple balances information an issuer can return for a given card. | getBalances(): ?array | setBalances(?array balances): void |
| `balanceAmount` | `?string` | Optional | Remaining balance on the account.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Remaining balance on the prepaid card.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `12` | getBalanceAmount(): ?string | setBalanceAmount(?string balanceAmount): void |
| `balanceAmountType` | `?string` | Optional | Type of amount. This value is returned only if you requested a balance inquiry. The issuer determines the value<br>that is returned. Possible values for deposit accounts:<br><br>- `01`: Current ledger (posted) balance.<br>- `02`: Current available balance, which is typically the ledger balance less outstanding authorizations.<br><br>Some depository institutions also include pending deposits and the credit or overdraft line associated with the<br>account. Possible values for credit card accounts:<br><br>- `01`: Credit amount remaining for customer (open to buy).<br>- `02`: Credit limit.<br><br>**Constraints**: *Maximum Length*: `2` | getBalanceAmountType(): ?string | setBalanceAmountType(?string balanceAmountType): void |
| `currency` | `?string` | Optional | Currency of the remaining balance on the account. For the possible values, see the [ISO Standard Currency Codes.](<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Currency of the remaining balance on the prepaid card.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `5` | getCurrency(): ?string | setCurrency(?string currency): void |
| `balanceSign` | `?string` | Optional | Sign for the remaining balance on the account. Returned only when the processor returns this value. Possible values:<br><br>Possible values:<br><br>- `Positive`<br>- `Negative`<br><br>#### PIN debit<br><br>Sign for the remaining balance on the prepaid card. Returned only when the processor returns this value.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `8` | getBalanceSign(): ?string | setBalanceSign(?string balanceSign): void |
| `affluenceIndicator` | `?string` | Optional | **Chase Paymentech Solutions**<br><br>Indicates whether a customer has high credit limits. This information enables you to market high cost items to<br>these customers and to understand the kinds of cards that high income customers are using.<br><br>This field is supported for Visa, Mastercard, Discover, and Diners Club. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>#### Litle<br><br>Flag that indicates that a Visa cardholder or Mastercard cardholder is in one of the affluent categories.<br>Possible values:<br><br>- `AFFLUENT`: High income customer with high spending pattern (>100k USD annual income and >40k USD annual<br>  card usage).<br>- `MASS AFFLUENT`: High income customer (>100k USD annual income).<br><br>Maximum length is 13.<br><br>#### Chase Paymentech Solutions<br><br>Maximum length is 1.<br><br>**Constraints**: *Maximum Length*: `13` | getAffluenceIndicator(): ?string | setAffluenceIndicator(?string affluenceIndicator): void |
| `category` | `?string` | Optional | #### GPX<br><br>Mastercard product ID associated with the primary account number (PAN).<br>Returned by authorization service.<br><br>#### Visa Acceptance through VisaNet<br><br>Visa or Mastercard product ID that is associated with the primary account number (PAN).<br>For descriptions of the Visa product IDs, see the Product ID table on the [Visa<br>Request & Response Codes web page.](<br><br>Data Length: String (3)<br><br>#### GPN<br><br>Visa or Mastercard product ID that is associated with the primary account number (PAN).<br>For descriptions of the Visa product IDs, see the Product ID table on the<br>[Visa Request & Response Codes web page.](<br><br>Data Length: String (3)<br><br>#### Worldpay VAP<br><br>**Important** Before using this field on Worldpay VAP,<br>you must contact Visa Acceptance Customer Support to have<br>your account configured for this feature.<br><br>Type of card used in the transaction. The only possible value is:<br><br>- `PREPAID`: Prepaid Card<br><br>Data Length: String (7)<br><br>#### RBS WorldPay Atlanta<br><br>Type of card used in the transaction. Possible values:<br><br>- `B`: Business Card<br>- `O`: Noncommercial Card<br>- `R`: Corporate Card<br>- `S`: Purchase Card<br>- `Blank`: Purchase card not supported<br><br>Data Length: String (1)<br><br>**Constraints**: *Maximum Length*: `7` | getCategory(): ?string | setCategory(?string category): void |
| `commercial` | `?string` | Optional | Indicates whether the card is a commercial card, which enables you to include Level II data in your transaction<br>requests. This field is supported for Visa and Mastercard on **Chase Paymentech Solutions**. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getCommercial(): ?string | setCommercial(?string commercial): void |
| `group` | `?string` | Optional | Type of commercial card. This field is supported only for Visa Acceptance through VisaNet. Possible values:<br><br>- `B`: Business card<br>- `R`: Corporate card<br>- `S`: Purchasing card<br>- `0`: Noncommercial card<br><br>Returned by authorization service.<br><br>**Constraints**: *Maximum Length*: `1` | getGroup(): ?string | setGroup(?string group): void |
| `healthCare` | `?string` | Optional | Indicates whether the card is a healthcare card. This field is supported for Visa and Mastercard on **Chase<br>Paymentech Solutions**. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getHealthCare(): ?string | setHealthCare(?string healthCare): void |
| `payroll` | `?string` | Optional | Indicates whether the card is a payroll card. This field is supported for Visa, Discover, Diners Club, and JCB<br>on **Chase Paymentech Solutions**. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getPayroll(): ?string | setPayroll(?string payroll): void |
| `level3Eligible` | `?string` | Optional | Indicates whether the card is eligible for Level III interchange fees, which enables you to include Level III<br>data in your transaction requests. This field is supported for Visa and Mastercard on **Chase Paymentech<br>Solutions**. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getLevel3Eligible(): ?string | setLevel3Eligible(?string level3Eligible): void |
| `pinlessDebit` | `?string` | Optional | Indicates whether the card is a PINless debit card. This field is supported for Visa and Mastercard on **Chase<br>Paymentech Solutions**. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getPinlessDebit(): ?string | setPinlessDebit(?string pinlessDebit): void |
| `signatureDebit` | `?string` | Optional | Indicates whether the card is a signature debit card.<br><br>This information enables you to alter the way an order is processed. For example, you might not want to reauthorize a transaction for a signature debit card, or you might<br>want to perform reversals promptly for a signature debit card. This field is supported for Visa, Mastercard, and<br>Maestro (International) on Chase Paymentech Solutions. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getSignatureDebit(): ?string | setSignatureDebit(?string signatureDebit): void |
| `prepaid` | `?string` | Optional | Indicates whether the card is a prepaid card. This information enables you to determine when a gift card or<br>prepaid card is presented for use when establishing a new recurring, installment, or deferred billing<br>relationship.<br><br>This field is supported for Visa, Mastercard, Discover, Diners Club, and JCB on Chase Paymentech Solutions.<br>Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getPrepaid(): ?string | setPrepaid(?string prepaid): void |
| `regulated` | `?string` | Optional | Indicates whether the card is regulated according to the Durbin Amendment. If the card is regulated, the card<br>issuer is subject to price caps and interchange rules. This field is supported for Visa, Mastercard, Discover,<br>Diners Club, and JCB on Chase Paymentech Solutions. Possible values:<br><br>- `Y`: Yes<br>- `N`: No<br>- `X`: Not applicable / Unknown<br><br>**Constraints**: *Maximum Length*: `1` | getRegulated(): ?string | setRegulated(?string regulated): void |
| `accountHolderType` | `?string` | Optional | This is the account owner information, valid values are:<br><br>- `01` : primary account holder<br>- `02` : secondary account holder<br>  This is returned in the response of an account verification transaction by the Issuer.<br><br>**Constraints**: *Maximum Length*: `25` | getAccountHolderType(): ?string | setAccountHolderType(?string accountHolderType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountFeaturesBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BalanceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$accountFeatures = AccountFeaturesBuilder::init()
    ->accountType('accountType8')
    ->accountStatus('accountStatus6')
    ->balances(
        [
            BalanceBuilder::init()
                ->accountType('accountType0')
                ->amount('amount2')
                ->amountType('amountType2')
                ->currency('currency0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            BalanceBuilder::init()
                ->accountType('accountType0')
                ->amount('amount2')
                ->amountType('amountType2')
                ->currency('currency0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            BalanceBuilder::init()
                ->accountType('accountType0')
                ->amount('amount2')
                ->amountType('amountType2')
                ->currency('currency0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->balanceAmount('balanceAmount0')
    ->balanceAmountType('balanceAmountType8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

