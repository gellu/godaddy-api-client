# DomainDetail

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain_id** | **double** | Unique identifier for this Domain | 
**domain** | **string** | Name of the domain | 
**status** | **string** | Processing status of the domain&lt;br/&gt;&lt;ul&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;ACTIVE&lt;/strong&gt; - All is well&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;AWAITING*&lt;/strong&gt; - System is waiting for the end-user to complete an action&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;CANCELLED*&lt;/strong&gt; - Domain has been cancelled, and may or may not be reclaimable&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;CONFISCATED&lt;/strong&gt; - Domain has been confiscated, usually for abuse, chargeback, or fraud&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;DISABLED*&lt;/strong&gt; - Domain has been disabled&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;EXCLUDED*&lt;/strong&gt; - Domain has been excluded from Firehose registration&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;EXPIRED*&lt;/strong&gt; - Domain has expired&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;FAILED*&lt;/strong&gt; - Domain has failed a required action, and the system is no longer retrying&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;HELD*&lt;/strong&gt; - Domain has been placed on hold, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;LOCKED*&lt;/strong&gt; - Domain has been locked, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;PARKED*&lt;/strong&gt; - Domain has been parked, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;PENDING*&lt;/strong&gt; - Domain is working its way through an automated workflow&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;RESERVED*&lt;/strong&gt; - Domain is reserved, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;REVERTED&lt;/strong&gt; - Domain has been reverted, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;SUSPENDED*&lt;/strong&gt; - Domain has been suspended, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;TRANSFERRED*&lt;/strong&gt; - Domain has been transferred out&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;UNKNOWN&lt;/strong&gt; - Domain is in an unknown state&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;UNLOCKED*&lt;/strong&gt; - Domain has been unlocked, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;UNPARKED*&lt;/strong&gt; - Domain has been unparked, and likely requires intervention from Support&lt;/li&gt; &lt;li&gt;&lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;UPDATED*&lt;/strong&gt; - Domain ownership has been transferred to another account&lt;/li&gt; &lt;/ul&gt; | 
**expires** | [**\GoDaddyDomainsClient\Model\Datetime**](Datetime.md) | Date and time when this domain will expire | [optional] 
**expiration_protected** | **bool** | Whether or not the domain is protected from expiration | 
**hold_registrar** | **bool** | Whether or not the domain is on-hold by the registrar | 
**locked** | **bool** | Whether or not the domain is locked to prevent transfers | 
**privacy** | **bool** | Whether or not the domain has privacy protection | 
**renew_auto** | **bool** | Whether or not the domain is configured to automatically renew | 
**renew_deadline** | [**\GoDaddyDomainsClient\Model\Datetime**](Datetime.md) | Date the domain must renew on | 
**transfer_protected** | **bool** | Whether or not the domain is protected from transfer | 
**created_at** | [**\GoDaddyDomainsClient\Model\Datetime**](Datetime.md) | Date and time when this domain was created | 
**auth_code** | **string** | Authorization code for transferring the Domain | 
**name_servers** | **string[]** | Fully-qualified domain names for DNS servers | 
**contact_registrant** | [**\GoDaddyDomainsClient\Model\Contact**](Contact.md) | Registration contact for the domain | 
**contact_billing** | [**\GoDaddyDomainsClient\Model\Contact**](Contact.md) | Billing contact for the domain registration | 
**contact_admin** | [**\GoDaddyDomainsClient\Model\Contact**](Contact.md) | Administrative contact for the domain registration | 
**contact_tech** | [**\GoDaddyDomainsClient\Model\Contact**](Contact.md) | Technical contact for the domain registration | 
**real_name_validation** | [**\GoDaddyDomainsClient\Model\RealNameValidation**](RealNameValidation.md) |  | [optional] 
**subaccount_id** | **string** | Reseller subaccount shopperid who can manage the domain | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


