---
title: 'Lync Server 2013: Schema Attribute nach Klasse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86c2c4a494408f619fc7162c70cba0570b62bd09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a>Schema Attribute nach Klasse in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-29_

In diesem Abschnitt werden die Schema Attribute aufgelistet, die in den einzelnen lync Server 2013 Klassen enthalten sein können, sowie die Klassen, die in anderen Klassen enthalten sein können. Eine Liste aller Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Eine Liste aller Attribute und deren Beschreibungen finden Sie unter [Schema Attribute and Descriptions in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).

<div>

## <a name="attributes-by-class"></a>Attribute nach Klasse


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasse</th>
<th>Kann diese Attribute enthalten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Kontakt</p></td>
<td><p>MSDS-SourceObjectDN</p>
<p>msRTCSIP-AcpInfo</p>
<p>msRTCSIP-ApplicationDestination</p>
<p>msRTCSIP-ApplicationOptions</p>
<p>msRTCSIP-ApplicationPrimaryLanguage</p>
<p>msRTCSIP-ApplicationSecondaryLanguages</p>
<p>msRTCSIP-ArchivingEnabled</p>
<p>msRTCSIP-DeploymentLocator</p>
<p>msRTCSIP-FederationEnabled</p>
<p>msRTCSIP-Gruppierung</p>
<p>msRTCSIP-InternetAccessEnabled</p>
<p>msRTCSIP-Reihe</p>
<p>msRTCSIP-LineServer</p>
<p>msRTCSIP-OptionFlags</p>
<p>msRTCSIP-OriginatorSid</p>
<p>msRTCSIP-OwnerUrn</p>
<p>msRTCSIP-PrimaryHomeServer</p>
<p>msRTCSIP-PrimaryUserAddress</p>
<p>msRTCSIP-Privatsphäre</p>
<p>msRTCSIP-proxyAddresses</p>
<p>msRTCSIP-Quellobjekttyp</p>
<p>msRTCSIP-TargetHomeServer</p>
<p>msRTCSIP-TargetUserPolicies</p>
<p>msRTCSIP-Mandanten-Nr</p>
<p>msRTCSIP-UserEnabled</p>
<p>msRTCSIP-UserExtension</p>
<p>msRTCSIP-UserLocationProfile</p>
<p>msRTCSIP-UserPolicies</p>
<p>msRTCSIP-UserPolicy</p>
<p>msRTCSIP-UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
<tr class="even">
<td><p>Mail-Recipient</p></td>
<td><p>"msexchucvoicemailsettings"</p>
<p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>msRTCSIP-ApplicationServerBL</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>msRTCSIP-applicationlist</p>
<p>msRTCSIP-ApplicationServerPoolLink</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p>
<p>msRTCSIP-ConferenceDirectoryId</p>
<p>msRTCSIP-ConferenceDirectoryTargetPool</p>
<p>msRTCSIP-ExtensionData</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>msRTCSIP-DefaultCWAExternalURL</p>
<p>msRTCSIP-DefaultCWAInternalURL</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Domäne</p></td>
<td><p>msRTCSIP – Standard</p>
<p>msRTCSIP-DomainData</p>
<p>msRTCSIP-Domänenname</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>msRTCSIP-EdgeProxyData</p>
<p>msRTCSIP-EdgeProxyFQDN</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>msRTCSIP-MCUData</p>
<p>msRTCSIP-MCUFactoryAddress</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-Server Version vom</p>
<p>msRTCSIP-TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>msRTCSIP-EnterpriseServices</p>
<p>msRTCSIP-PoolAddress</p>
<p>msRTCSIP-Server</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>msRTCSIP-BackEndServer</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-MirrorBackEndServer</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-MappingContact</p>
<p>msRTCSIP-MappingLocation</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>msRTCSIP-ExternalAccessCode</p>
<p>msRTCSIP-LocationProfileOptions</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>msRTCSIP-MCUFactoryData</p>
<p>msRTCSIP-MCUFactoryProviderID</p>
<p>msRTCSIP-MCUServers</p>
<p>msRTCSIP-MCUType</p>
<p>msRTCSIP-MCUVendor</p>
<p>msRTCSIP-PoolAddresses</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>msRTCSIP-MCUFactoryPath</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobilität</p></td>
<td><p>msRTCSIP-MobilityFlags</p>
<p>msRTCSIP-MobilityPolicy</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>DNSHostName</p>
<p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pool</p></td>
<td><p>msRTCSIP-applicationlist</p>
<p>msRTCSIP-BackEndServer</p>
<p>msRTCSIP-DNSHostName</p>
<p>msRTCSIP-PoolData</p>
<p>msRTCSIP-PoolDisplayName</p>
<p>msRTCSIP-PoolDomainFQDN</p>
<p>msRTCSIP-PoolFunctionality</p>
<p>msRTCSIP-pooltype</p>
<p>msRTCSIP-PoolVersion</p>
<p>msRTCSIP-TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>msRTCSIP-FrontEndServers</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Anwesenheit</p></td>
<td><p>msRTCSIP-PresenceFlags</p>
<p>msRTCSIP-PresencePolicy</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>msRTCSIP-MCUType</p>
<p>msRTCSIP-MCUVendor</p>
<p>msRTCSIP-RoutingPoolDN</p>
<p>msRTCSIP-TrustedMCUData</p>
<p>msRTCSIP-TrustedMCUFQDN</p>
<p>msRTCSIP-TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>msRTCSIP-TrustedProxyData</p>
<p>msRTCSIP-TrustedProxyFQDN</p>
<p>msRTCSIP-TrustedServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>msRTCSIP-TrustedServerData</p>
<p>msRTCSIP-TrustedServerFQDN</p>
<p>msRTCSIP-TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>msRTCSIP-ExtensionData</p>
<p>msRTCSIP – routingfähig</p>
<p>msRTCSIP-RoutingPoolDN</p>
<p>msRTCSIP-ServerBL</p>
<p>msRTCSIP-TrustedServerFQDN</p>
<p>msRTCSIP-TrustedServerVersion</p>
<p>msRTCSIP-TrustedServiceFlags</p>
<p>msRTCSIP-TrustedServicePort</p>
<p>msRTCSIP-TrustedServiceType</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>msRTCSIP-TrustedWebComponentsServerData</p>
<p>msRTCSIP-TrustedWebComponentsServerFQDN</p>
<p>msRTCSIP-TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>msRTCSIP-WebComponentsServers</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>msRTCSIP-WebComponentsData</p>
<p>msRTCSIP-WebComponentsPoolAddress</p>
<p>msRTCSIP-Server Version vom</p></td>
</tr>
<tr class="even">
<td><p>Benutzer</p></td>
<td><p>msRTCSIP-AcpInfo</p>
<p>msRTCSIP-ApplicationOptions</p>
<p>msRTCSIP-ArchivingEnabled</p>
<p>msRTCSIP-DeploymentLocator</p>
<p>msRTCSIP-FederationEnabled</p>
<p>msRTCSIP-Gruppierung</p>
<p>msRTCSIP-InternetAccessEnabled</p>
<p>msRTCSIP-Reihe</p>
<p>msRTCSIP-LineServer</p>
<p>msRTCSIP-OptionFlags</p>
<p>msRTCSIP-OriginatorSid</p>
<p>msRTCSIP-OwnerUrn</p>
<p>msRTCSIP-PrimaryHomeServer</p>
<p>msRTCSIP-PrimaryUserAddress</p>
<p>msRTCSIP-Privatsphäre</p>
<p>msRTCSIP-TargetHomeServer</p>
<p>msRTCSIP-TargetUserPolicies</p>
<p>msRTCSIP-Mandanten-Nr</p>
<p>msRTCSIP-UserEnabled</p>
<p>msRTCSIP-UserExtension</p>
<p>msRTCSIP-UserLocationProfile</p>
<p>msRTCSIP-UserPolicies</p>
<p>msRTCSIP-UserPolicy</p>
<p>msRTCSIP-UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a>In anderen Klassen enthaltene Klassen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasse</th>
<th>Kann diese Klasse enthalten</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serviceConnectionPoint</p></td>
<td><p>msRTCSIP-Server</p>
<p>msRTCSIP-PoolService</p>
<p>msRTCSIP-MCU</p>
<p>msRTCSIP-MCUFactoryService</p>
<p>msRTCSIP-Webkomponenten</p>
<p>msRTCSIP-WebComponentsService</p>
<p>msRTCSIP-ApplicationServerService</p>
<p>msRTCSIP-Service</p>
<p>msRTCSIP-ConnectionPoint</p>
<p>msRTCSIP-MediationServer</p>
<p>msRTCSIP-ApplicationServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>msRTCSIP-Global Container</p>
<p>msRTCSIP-Pools</p>
<p>msRTCSIP-MCUFactories</p>
<p>msRTCSIP-TrustedMCUs</p>
<p>msRTCSIP-TrustedWebComponentsServers</p>
<p>msRTCSIP-TrustedProxies</p>
<p>msRTCSIP-TrustedServices</p>
<p>msRTCSIP-ApplicationContacts</p>
<p>msRTCSIP-LocationContactMappings</p>
<p>msRTCSIP-conferencedirectories "</p>
<p>msRTCSIP-GlobalTopologySettings</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Global Container</p></td>
<td><p>msRTCSIP-Domäne</p>
<p>msRTCSIP-TrustedServer</p>
<p>msRTCSIP-EdgeProxy</p>
<p>msRTCSIP-MonitoringServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>msRTCSIP-Pool</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>msRTCSIP-MCUFactory</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>msRTCSIP-TrustedMCU</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>msRTCSIP-TrustedProxy</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>msRTCSIP-TrustedService</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>msRTCSIP-LocationContactMapping</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-conferencedirectories "</p></td>
<td><p>msRTCSIP-ConferenceDirectory</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

