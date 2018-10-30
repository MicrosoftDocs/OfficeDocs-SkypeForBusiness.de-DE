---
title: Schemaklassen und Beschreibungen in Lync Server 2013
TOCTitle: Schemaklassen und Beschreibungen in Lync Server 2013
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398625(v=OCS.15)
ms:contentKeyID: 49294530
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schemaklassen und Beschreibungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden alle von Lync Server 2013 verwendeten Schemaklassen beschrieben.

## Schemaklassen und Beschreibungen


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
<td><p>Exchange Unified Messaging (UM)-E-Mail-Empfänger.</p></td>
<td><p>Diese Erweiterungsklasse wird gemeinsam mit Exchange UM verwendet.</p></td>
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
<td><p>Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und dem zugehörigen Anwendungsdienst bereit.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-ApplicationServer&quot; enthält Attribute, die Einstellungen für Instanzen des Anwendungsdiensts darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (veraltet)</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält alle Einstellungen, die sich auf die Archivierung beziehen.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (veraltet)</p></td>
<td><p>Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungsserver dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungsserver (z. B. ein Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist) aktiviert wird.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
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
<td><p>Generischer Dienststeuerungspunkt zur Angabe des Computers als Server, auf dem Lync Server ausgeführt wird.</p></td>
<td><p>Neu in Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Diese Erweiterungsklasse enthält die Einstellungen für eine Microsoft Lync Web App-Bank.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierung definieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Dieser Klassencontainer stellt einen einzelnen Zugriffs-Edgedienst dar. Da ein Zugriffs-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden normalerweise keinen Zugriff auf die Inhalte in Active Directory-Domänendienste vom Umkreisnetzwerk aus zulassen, werden Instanzen des Zugriffs-Edgediensts nicht in das Active Directory-Netzwerk für das Intranet aufgenommen. Somit werden Zugriffsproxys nicht automatisch in AD DS registriert. Der Administrator muss das Vorhandensein der einzelnen Instanzen des Zugriffs-Edgedienst in AD DS manuell konfigurieren.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-MCU&quot; enthält Attribute, die Einstellungen für Konferenzserver darstellen.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-MediationServer&quot; enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-Server&quot; enthält Attribute, die Einstellungen für SIP-Server darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält alle Einstellungen, die sich auf den Partnerverbund beziehen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Diese Klasse enthält alle Einstellungen, die innerhalb einer Lync Server-Bereitstellung angewendet werden.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (veraltet)</p></td>
<td><p>Diese Klasse stellt eine einzelne Office Communications Server-Besprechungsrichtlinie dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Das lokale Einstellungsobjekt für die globale Topologie.</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Container mit Einstellungsobjekten für die globale Topologie.</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Standortnormalisierungsregel dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Diese Klasse wird von der Konferenzzentrale erstellt und enthält Attribute, mit denen Konferenztelefonnummern nach Region kategorisiert werden.</p></td>
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
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält selbst keine Attribute.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
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
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Container zum Speichern der globalen Mobilitätseinstellungen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Diese Klasse enthält Attribute, die Einstellungen für einen einzelnen Monitoring-Server darstellen.</p></td>
<td><p>Neu in Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Least-Cost-Route zu einem Gateway oder einem Satz mehrerer Gateways dar. Diese Informationen werden von allen Enterprise-Pools oder Standard Edition-Servern verwendet, um ausgehende Gespräche möglichst kosteneffizient an das PSTN-Netzwerk weiterzuleiten.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container für mehrere Least-Cost-Routen und enthält selbst keine Attribute.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere Lync Server-Richtlinienklassen und weist selbst keine Attribute auf.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Diese Klasse stellt einen einzelnen Lync Server-Pool dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>Diese Klasse enthält mehrere Lync Server-Pools und weist selbst keine Attribute auf.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Diese Klasse stellt den Dienststeuerungspunkt eines Pools dar. Das msRTCSIP-PrimaryHomeServer-Attribut von Benutzern in einem Pool zeigt auf eine Instanz dieser Klasse.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Container zum Speichern der globalen Anwesenheitseinstellungen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält Attribute, die von den SIP-Registrierungsservern verwaltete Benutzereinstellungen darstellen.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (veraltet)</p></td>
<td><p>Diese Klasse ist ein Container und stellt eine Instanz einer Telefonroutenverwendung dar. Eine Verwendungsklasse für Telefonrouten besteht aus einem Attribut- und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Beschreibungsfeld können Administratoren Hinweise zur Verwendung dieses Attributs in der Telefonroute angeben.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (veraltet)</p></td>
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse &quot;msRTCSIP-RouteUsage&quot; und weist selbst keine Attribute auf.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält Attribute, die den Umfang von Suchergebnissen begrenzen und steuern.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Diese Klasse stellt einen einzelnen Server mit Lync Server dar.</p></td>
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
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse &quot;msRTCSIP-TrustedMCU&quot; und weist selbst keine Attribute auf.</p></td>
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
<td><p>Diese Klasse ist ein Container und stellt einen vertrauenswürdigen Dienst dar, der unter Verwendung einer GRUU-Adresse (Globally Routable User Agent URI) routingfähig ist. Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von Lync Server als vertrauenswürdig eingestuft wird. Dieser vertrauenswürdige Server muss Mitglied einer Active Directory-Domäne sein.</p></td>
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
<td><p>Diese Klasse enthält mehrere Instanzen der Klasse &quot;msRTCSIP-TrustedWebComponentServer&quot; und weist selbst keine Attribute auf.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (veraltet)</p></td>
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-GlobalContainer&quot; enthält Attribute, die Unified Communications betreffen.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
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
<td><p>Diese Erweiterungsklasse zu &quot;msRTCSIP-WebComponents&quot; enthält Attribute, die Einstellungen für Webkomponenten darstellen.</p></td>
<td><p>Neu in Communications Server 2007.</p></td>
</tr>
</tbody>
</table>

