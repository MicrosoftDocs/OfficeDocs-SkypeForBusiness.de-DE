---
title: 'Lync Server 2013: Schema Klassen und Beschreibungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Schema Klassen und Beschreibungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In diesem Abschnitt werden alle von lync Server 2013 verwendeten Schemaklassen beschrieben.

<div>

## <a name="schema-classes-and-descriptions"></a>Schema Klassen und Beschreibungen


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Klasse</th>
<th>Beschreibung</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>E-Mail-Empfänger</p></td>
<td><p>Exchange Unified Messaging (um)-e-Mail-Empfänger.</p></td>
<td><p>Diese Auxiliary-Klasse wird für Exchange um freigegeben.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationContacts</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Anwendungskontakte und enthält keine Attribute selbst.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ApplicationServer</p></td>
<td><p>Diese Klasse enthält den Eintrag für den Dienst Kontrollpunkt für eine Instanz von Unified Communications Application Services (UCAS).</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationServerService</p></td>
<td><p>Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu seinem Anwendungsdienst bereit.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-ApplicationServer enthält Attribute, die Einstellungen für Instanzen des Anwendungsdiensts darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Archiv (veraltet)</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält alle Einstellungen im Zusammenhang mit der Archivierung.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ArchivingServer (veraltet)</p></td>
<td><p>Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungs Server dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungs Server aktiviert wird, beispielsweise einen Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ConferenceDirectories</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Instanzen von Konferenz Verzeichnissen und enthält keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ConferenceDirectory</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ConnectionPoint</p></td>
<td><p>Generic Service Control Point (SCP), um den Computer als einen Server mit lync Server festzulegen.</p></td>
<td><p>Neu in lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefaultCWABank</p></td>
<td><p>Diese Auxiliary-Klasse enthält die Einstellungen für eine Microsoft lync Web App-Bank.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Domäne</p></td>
<td><p>Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierungsstelle definieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-EdgeProxy</p></td>
<td><p>Dieser Klassencontainer stellt einen einzelnen Access-Edgedienst dar. Da ein Access-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden in der Regel keinen Zugriff auf Active Directory-Domänendienste aus dem Umkreisnetzwerk zulassen, sind Instanzen des Access-Edgedienst nicht dem Active Directory-Netzwerk des Intranets beigetreten. Daher werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das vorhanden sein jeder Instanz von Access Edge Service in AD DS manuell konfigurieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Diese Erweiterungsklasse für Attribut msRTCSIP-MCU enthält Attribute, die Einstellungen für Konferenzserver darstellen.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-MediationServer enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Server enthält Attribute, die Einstellungen für SIP-Server darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Federation</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält alle Einstellungen, die sich auf den Verbund beziehen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Global Container</p></td>
<td><p>Diese Klasse enthält alle Einstellungen, die in einer lync Server-Bereitstellung gelten.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-GlobalUserPolicy (veraltet)</p></td>
<td><p>Diese Klasse stellt eine einzelne Office Communications Server-Besprechungsrichtlinie dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Das Setting-Objekt der lokalen globalen Topologie.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Container, in dem globale Topologie-Einstellungsobjekte enthalten sind.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocalNormalization</p></td>
<td><p>Diese Klasse ist ein Container, der eine Instanz einer Standort Normalisierungsregel darstellt.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocationContactMapping</p></td>
<td><p>Diese Klasse wird von der Conferencing Attendant-Anwendung erstellt und enthält Attribute, mit denen Konferenz Telefonnummern nach Regionen kategorisiert werden.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocationContactMappings</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Instanzen von Standortkontaktzuordnungen und enthält keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocationProfile</p></td>
<td><p>Diese Klasse ist ein Container, der ein bestimmtes Standortprofil darstellt.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocationProfiles (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Standortprofile und enthält keine Attribute selbst.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocalNormalizations (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält keine Attribute selbst.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCU</p></td>
<td><p>Diese Klasse stellt einen einzelnen Konferenzserver dar.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUFactories</p></td>
<td><p>Diese Klasse enthält mehrere Attribut msRTCSIP-MCUFactory-Klassen und besitzt keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCUFactory</p></td>
<td><p>Bei dieser Klasse handelt es sich um einen Container, der eine Konferenz Server Factory für einen einzelnen Medientyp darstellt. Eine Instanz dieser Klasse wird erstellt, wenn der erste Konferenzserver für diesen bestimmten Typ und Lieferanten aktiviert ist.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUFactoryService</p></td>
<td><p>Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu seiner Konferenz Server Factory bereit.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MediationServer</p></td>
<td><p>Diese Klasse enthält den Eintrag für den Dienst Kontrollpunkt für einen Vermittlungs Server.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Besprechung (veraltet)</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP – Mobilität</p></td>
<td><p>Container, in dem die globalen Mobilitätseinstellungen gespeichert sind.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MonitoringServer</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen einzelnen Überwachungs Server darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PhoneRoute (veraltet)</p></td>
<td><p>Bei dieser Klasse handelt es sich um einen Container, der eine Instanz einer Least Cost-Route zu einem Gateway oder einer Gruppe von Gateways darstellt. Diese Informationen werden von allen Enterprise-Pools oder Servern mit Standard Edition verwendet, um ausgehende Anrufe auf die kostengünstigste Weise an das öffentlich geschaltete Telefonnetz (PSTN) weiterzuleiten.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PhoneRoutes (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere, kostengünstigste Routen und enthält keine Attribute selbst.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Richtlinien (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere lync Server-Richtlinien Klassen und hat keine Attribute selbst.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Pool</p></td>
<td><p>Diese Klasse stellt einen einzelnen lync Server-Pool dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Pools</p></td>
<td><p>Diese Klasse enthält mehrere lync Server-Pools und hat keine Attribute selbst.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PoolService</p></td>
<td><p>Diese Klasse stellt den Kontrollpunkt des Dienst Steuerelements pointservice eines Pools dar. Für Benutzer, die in einem Pool gehostet werden, wird Ihr Attribut msRTCSIP-PrimaryHomeServer-Attribut auf eine Instanz dieser Klasse verweisen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Anwesenheitsinformationen</p></td>
<td><p>Container, in dem die globalen Anwesenheitseinstellungen gespeichert sind.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Registrar</p></td>
<td><p>Diese Hilfsklasse für Attribut msRTCSIP-Global Container enthält Attribute, die Benutzereinstellungen darstellen, die von den SIP-Registrierungs Servern verwaltet werden.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-RouteUsage (veraltet)</p></td>
<td><p>Bei dieser Klasse handelt es sich um einen Container, der eine Instanz einer Telefonrouten Verwendung darstellt. Eine Telefonroute-Nutzungsklasse besteht aus einem Attributfeld und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Feld Beschreibung können Administratoren die Verwendung dieses Attributs auf der Telefonroute beschreiben.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-RouteUsages (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-RouteUsage-Klasse und hat keine Attribute selbst.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Suche</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die den Umfang der Suchergebnisse einschränken und steuern.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Server</p></td>
<td><p>Diese Klasse steht für einen einzelnen Server, auf dem lync Server ausgeführt wird.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Service</p></td>
<td><p>Diese Klasse enthält den Container für globale Einstellungen und Attribut msRTCSIP-Domänenobjekte.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedMCU</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedMCUs</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-TrustedMCU-Klasse und hat keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedProxies</p></td>
<td><p>Diese Klasse enthält mehrere Attribut msRTCSIP-TrustedProxy-Klassen und enthält keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedProxy</p></td>
<td><p>Diese Klasse ist ein Container, der einen Server mit Proxy Server darstellt. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Proxy Server auf einem Computer aktiviert wird, der mit AD DS verbunden ist.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServer</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedService</p></td>
<td><p>Diese Klasse ist ein Container, der einen vertrauenswürdigen Dienst darstellt, der mithilfe einer Global routingfähigen Benutzer-Agent-URI-Adresse (GRUU) geroutet werden kann. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von lync Server als vertrauenswürdig eingestuft wird. Dieser vertrauenswürdige Server muss einer Active Directory-Domäne angehören.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServices</p></td>
<td><p>Diese Klasse ist ein Container für mehrere GRUU-Server und enthält keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Attribut msRTCSIP-TrustedWebComponentServer-Klasse und hat keine Attribute selbst.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UnifiedCommunications (veraltet)</p></td>
<td><p>Diese Auxiliary-Klasse für Attribut msRTCSIP-Global Container enthält Attribute, die sich auf Unified Communications beziehen.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Webkomponenten</p></td>
<td><p>Diese Klasse enthält den pointservice-Kontrollpunkt für Dienst Steuerelemente für Internet Information Server (IIS). Es identifiziert einen Server als Web Components-Server.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-WebComponentsService</p></td>
<td><p>Diese Klasse stellt eine Zuordnung von einem bestimmten Pool zu den Webkomponenten bereit, die vom Pool verwendet werden.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-WebComponentSettings</p></td>
<td><p>Diese zusätzliche Klasse für Attribut msRTCSIP-Webkomponenten enthält Attribute, die Einstellungen für Webkomponenten darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

