
# Custom Header Signature



Documentation for accessing and setting credentials for BearerAuth.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| authorization | `string` | Enter your bearer token in the format **Bearer &lt;token&gt;** | `authorization` | `getAuthorization()` |



**Note:** Auth credentials can be set using `BearerAuthCredentialsBuilder::init()` in `bearerAuthCredentials` method in the client builder and accessed through `getBearerAuthCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use VisaAcceptanceMergedSpecLib\Authentication\BearerAuthCredentialsBuilder;
use VisaAcceptanceMergedSpecLib\VisaAcceptanceMergedSpecClientBuilder;

$client = VisaAcceptanceMergedSpecClientBuilder::init()
    ->bearerAuthCredentials(
        BearerAuthCredentialsBuilder::init(
            'authorization'
        )
    )
    ->build();
```


