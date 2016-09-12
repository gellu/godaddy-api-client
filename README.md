# GoDaddy Domains API Client

API client for [GoDaddy Domains](https://developer.godaddy.com) 

## Requirements

PHP 5.4.0 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```php
{
  "require" : {
    "gellu/godaddy-api-client" : "1.*"
  }
}
```

Then run `composer install`


## Example - Domain purchase

```php
<?php

const API_KEY 		= ''; // key obtained from https://developer.godaddy.com
const API_SECRET 	= ''; // secret obtained from https://developer.godaddy.com

$domain 			= 'test-domain.com';
$domainPeriod 		= 1;
$domainAutoRenew	= false;
$domainTLD 			= 'pl';
$contact 			= [
	'name'			=> 'John',
	'surname'		=> 'Doe',
	'email'			=> 'john.doe@test-domain.com',
	'phone'			=> '+48.111111111',
	'organization'	=> 'Corporation Inc.',
	'street'		=> 'Street Ave. 666',
	'city'			=> 'New City',
	'country'		=> 'PL',
	'postal-code'	=> '11-111',
	'state'			=> 'state of art'
];

$configuration = new \GoDaddyDomainsClient\Configuration();
$configuration->addDefaultHeader("Authorization", "sso-key ". API_KEY .":". API_SECRET);
$configuration->setDebug(true);

$apiClient = new \GoDaddyDomainsClient\ApiClient($configuration);
$apiInstance = new \GoDaddyDomainsClient\Api\VdomainsApi($apiClient);

$agreement = $apiInstance->getAgreement($domainTLD, false);
$agreementKeys = [$agreement[0]->getAgreementKey()];

$domainPurchase = new \GoDaddyDomainsClient\Model\DomainPurchase();
$domainPurchase->setDomain($domain);

$domainPurchaseConsent = new \GoDaddyDomainsClient\Model\Consent();
$domainPurchaseConsent->setAgreementKeys($agreementKeys);
$domainPurchaseConsent->setAgreedBy($contact['name'] . ' ' . $contact['surname']);
$domainPurchaseConsent->setAgreedAt(date("Y-m-d\TH:i:s\Z"));
$domainPurchase->setConsent($domainPurchaseConsent);

$domainContactAdmin = new \GoDaddyDomainsClient\Model\Contact();
$domainContactAdmin->setNameFirst($contact['name']);
$domainContactAdmin->setNameLast($contact['surname']);
$domainContactAdmin->setEmail($contact['email']);
$domainContactAdmin->setPhone($contact['phone']);
$domainContactAdmin->setOrganization($contact['organization']);

$domainContactAdminAddressMailing = new \GoDaddyDomainsClient\Model\Address();
$domainContactAdminAddressMailing->setAddress1($contact['street']);
$domainContactAdminAddressMailing->setCity($contact['city']);
$domainContactAdminAddressMailing->setCountry($contact['country']);
$domainContactAdminAddressMailing->setPostalCode($contact['postal-code']);
$domainContactAdminAddressMailing->setState($contact['state']);

$domainContactAdmin->setAddressMailing($domainContactAdminAddressMailing);

$domainPurchase->setContactAdmin($domainContactAdmin);
$domainPurchase->setContactBilling($domainContactAdmin);
$domainPurchase->setContactRegistrant($domainContactAdmin);
$domainPurchase->setContactTech($domainContactAdmin);
$domainPurchase->setPeriod(1);
$domainPurchase->setRenewAuto(false);

$purchase = $apiInstance->purchase($domainPurchase);
```

## Documentation For Models

 - [Address](godaddy-api-client/blob/master/docs/Model/Address.md)
 - [Consent](godaddy-api-client/blob/master/docs/Model/Consent.md)
 - [Contact](godaddy-api-client/blob/master/docs/Model/Contact.md)
 - [DNSRecord](godaddy-api-client/blob/master/docs/Model/DNSRecord.md)
 - [DNSRecordCreateType](godaddy-api-client/blob/master/docs/Model/DNSRecordCreateType.md)
 - [DNSRecordCreateTypeName](godaddy-api-client/blob/master/docs/Model/DNSRecordCreateTypeName.md)
 - [Domain](godaddy-api-client/blob/master/docs/Model/Domain.md)
 - [DomainAvail](godaddy-api-client/blob/master/docs/Model/DomainAvail.md)
 - [DomainAvailableResponse](godaddy-api-client/blob/master/docs/Model/DomainAvailableResponse.md)
 - [DomainContacts](godaddy-api-client/blob/master/docs/Model/DomainContacts.md)
 - [DomainDetail](godaddy-api-client/blob/master/docs/Model/DomainDetail.md)
 - [DomainPurchase](godaddy-api-client/blob/master/docs/Model/DomainPurchase.md)
 - [DomainPurchaseResponse](godaddy-api-client/blob/master/docs/Model/DomainPurchaseResponse.md)
 - [DomainRenew](godaddy-api-client/blob/master/docs/Model/DomainRenew.md)
 - [DomainSuggestion](godaddy-api-client/blob/master/docs/Model/DomainSuggestion.md)
 - [DomainSummary](godaddy-api-client/blob/master/docs/Model/DomainSummary.md)
 - [DomainTransferIn](godaddy-api-client/blob/master/docs/Model/DomainTransferIn.md)
 - [DomainUpdate](godaddy-api-client/blob/master/docs/Model/DomainUpdate.md)
 - [Error](godaddy-api-client/blob/master/docs/Model/Error.md)
 - [ErrorField](godaddy-api-client/blob/master/docs/Model/ErrorField.md)
 - [ErrorLimit](godaddy-api-client/blob/master/docs/Model/ErrorLimit.md)
 - [IdentityDocumentCreate](godaddy-api-client/blob/master/docs/Model/IdentityDocumentCreate.md)
 - [JsonDataType](godaddy-api-client/blob/master/docs/Model/JsonDataType.md)
 - [JsonProperty](godaddy-api-client/blob/master/docs/Model/JsonProperty.md)
 - [JsonSchema](godaddy-api-client/blob/master/docs/Model/JsonSchema.md)
 - [LegalAgreement](godaddy-api-client/blob/master/docs/Model/LegalAgreement.md)
 - [PrivacyPurchase](godaddy-api-client/blob/master/docs/Model/PrivacyPurchase.md)
 - [RealNameValidation](godaddy-api-client/blob/master/docs/Model/RealNameValidation.md)
 - [TldSummary](godaddy-api-client/blob/master/docs/Model/TldSummary.md)


This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 2.4.8
- Build date: 2016-09-01T15:18:33.475Z
- Build package: class io.swagger.codegen.languages.PhpClientCodegen

