---
title: 'Lync Server 2013: Schema Klassen und-Beschreibungen'
description: 'Lync Server 2013: Schema Klassen und-Beschreibungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557101"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Schema Klassen und Beschreibungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

In diesem Abschnitt werden alle Schemaklassen beschrieben, die von lync Server 2013 verwendet werden.

<div>

## <a name="schema-classes-and-descriptions"></a>Schemaklassen und Beschreibungen


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
<td><p>Mail-Recipient</p></td>
<td><p>Exchange Unified Messaging (um) e-Mail-Empfänger.</p></td>
<td><p>Diese Erweiterungsklasse wird für Exchange um freigegeben.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Anwendungskontakte und enthält selbst keine Attribute.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt für eine Instanz von Unified Communications-Anwendungsdiensten.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und dem Anwendungsdienst bereit.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Diese Auxiliary-Klasse für msRTCSIP-ApplicationServer hält Attribute, die Einstellungen für Instanzen des Anwendungsdienst darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (veraltet)</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf die Archivierung beziehen.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (veraltet)</p></td>
<td><p>Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungsserver dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungsserver (z. B. ein Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist) aktiviert wird.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-conferencedirectories "</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Instanzen von Konferenzverzeichnissen und enthält selbst keine Attribute.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>Allgemeiner Dienststeuerungspunkt (Service Control Points, SCP) zum Angeben des Computers als Server mit lync Server.</p></td>
<td><p>Neu in lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Diese Auxiliary-Klasse beinhaltet die Einstellungen für eine Microsoft lync Web App Bank.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domäne</p></td>
<td><p>Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierung definieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Dieser Klassencontainer stellt einen einzelnen Zugriffs-Edgedienst dar. Da ein Zugriffs-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden normalerweise nicht Active Directory-Domänendienste Zugriff aus dem Umkreisnetzwerk zulassen, werden Instanzen von Zugriffs-Edgedienst nicht mit dem Active Directory Netzwerk des Intranets verbunden. Somit werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das vorhanden sein jeder Instanz von Zugriffs-Edgedienst in AD DS manuell konfigurieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-MCU" enthält Attribute, die Einstellungen für Konferenzserver darstellen.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-MediationServer" enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-Server" enthält Attribute, die Einstellungen für SIP-Server darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Partnerverbund</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf den Partnerverbund beziehen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Global Container</p></td>
<td><p>Diese Klasse umfasst alle Einstellungen, die in einer lync Server-Bereitstellung gelten.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (veraltet)</p></td>
<td><p>Diese Klasse stellt eine einzelne Office Communications Server Besprechungsrichtlinie dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Das lokale Einstellungsobjekt für die globale Topologie.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Container mit Einstellungsobjekten für die globale Topologie.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Standortnormalisierungsregel dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Diese Klasse wird vom Konferenzzentrale erstellt und hält Attribute, die zum Kategorisieren von Konferenztelefon Nummern nach Regionen verwendet werden.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Instanzen von Standortkontaktzuordnungen und enthält selbst keine Attribute.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Diese Klasse ist ein Container und stellt ein bestimmtes Standortprofil dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Standortprofile und enthält selbst keine Attribute.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält selbst keine Attribute.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Diese Klasse stellt einen einzelnen Konferenzserver dar.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Diese Klasse enthält mehrere msRTCSIP-MCUFactory-Klassen und weist selbst keine Attribute auf.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Zuordnungsinstanz für Konferenzserver für einen einzelnen Medientyp dar. Eine Instanz dieser Klasse wird erstellt, sobald der erste Konferenzserver für diesen spezifischen Typ und Hersteller aktiviert wird.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und der dazugehörigen Zuordnungsinstanz für Konferenzserver bereit.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt eines Vermittlungsservers.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (veraltet)</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobilität</p></td>
<td><p>Container zum Speichern der globalen Mobilitätseinstellungen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Diese Klasse umfasst Attribute, die Einstellungen für einen einzelnen Monitoring Server darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Least-Cost-Route zu einem Gateway oder einem Satz mehrerer Gateways dar. Diese Informationen werden von allen Enterprise-Pools oder Standard Edition-Servern verwendet, um ausgehende Gespräche möglichst kosteneffizient an das PSTN-Netzwerk weiterzuleiten.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Least-Cost-Routen und enthält selbst keine Attribute.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere lync Server Richtlinien Klassen und weist selbst keine Attribute auf.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Diese Klasse stellt einen einzelnen lync Server Pool dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Diese Klasse enthält mehrere lync Server Pools und verfügt über keine Attribute selbst.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Diese Klasse stellt den Dienststeuerungspunkt eines Pools dar. Das msRTCSIP-PrimaryHomeServer-Attribut von Benutzern in einem Pool zeigt auf eine Instanz dieser Klasse.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Anwesenheit</p></td>
<td><p>Container zum Speichern der globalen Anwesenheitseinstellungen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die von den SIP-Registrierungsservern verwaltete Benutzereinstellungen darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Telefonroutenverwendung dar. Eine Verwendungsklasse für Telefonrouten besteht aus einem Attribut- und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Beschreibungsfeld können Administratoren Hinweise zur Verwendung dieses Attributs in der Telefonroute angeben.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-RouteUsage" und weist selbst keine Attribute auf.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Suche</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die den Umfang von Suchergebnissen begrenzen und steuern.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Diese Klasse stellt einen einzelnen Server mit lync Server dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Diese Klasse enthält den Container für globale Einstellungen und msRTCSIP-Domain-Objekte.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedMCU" und weist selbst keine Attribute auf.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Diese Klasse enthält mehrere msRTCSIP-TrustedProxy-Klassen und weist selbst keine Attribute auf.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Diese Klasse ist ein Container und stellt einen Server dar, auf dem ein Proxyserver ausgeführt wird. Eine Instanz dieser Klasse wird erstellt, sobald ein neuer Proxyserver auf einem Computer aktiviert wird, der Mitglied von AD DS ist.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Diese Klasse ist ein Container und stellt einen vertrauenswürdigen Dienst dar, der unter Verwendung einer GRUU-Adresse (Globally Routable User Agent URI) routingfähig ist. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von lync Server als vertrauenswürdig eingestuft wird. Dieser vertrauenswürdige Server muss Mitglied einer Active Directory-Domäne sein.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Diese Klasse ist ein Container für mehrere GRUU-Server und enthält selbst keine Attribute.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedWebComponentServer" und weist selbst keine Attribute auf.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (veraltet)</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die Unified Communications betreffen.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Webkomponenten</p></td>
<td><p>Diese Klasse enthält den Dienststeuerungspunkt für Internetinformationsdienste (Internet Information Services, IIS). Sie identifiziert einen Server als Webkomponentenserver.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Diese Klasse liefert eine Zuordnung zwischen einem bestimmten Pool und den Webkomponenten, die für diesen Pool verwendet werden.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Diese Erweiterungsklasse zu "msRTCSIP-WebComponents" enthält Attribute, die Einstellungen für Webkomponenten darstellen.</p></td>
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

