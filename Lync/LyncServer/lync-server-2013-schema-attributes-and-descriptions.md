---
title: 'Lync Server 2013: Schema Attribute und-Beschreibungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc1d6f5041564c1b865e49ef73a539f3addb75dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Schema Attribute und-Beschreibungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

In diesem Abschnitt werden alle Schema Attribute beschrieben, die von lync Server 2013 verwendet werden. Informationen zu den Klassen, die Attributen zugeordnet sind, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Eine Liste der Klassen und Attribute, die neu in lync Server 2013 sind, finden Sie unter [Schema Changes in lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Attribute, bei denen es sich um verknüpfte Paare handelt, werden als Weiterleitungslinks oder als Backlinks angegeben. Ein Attribut, das auf ein anderes Objekt verweist, ist eine Weiterleitungsverbindung; das Attribut des anderen Objekts, das auf das erste Objekt zurückverweist, ist eine Rückverknüpfung. Weiterleitungslinks sind aktualisierbar, während Rück Verknüpfungen schreibgeschützt sind.

Einige Attribute weisen einen Bitmaskenwert auf. Für diese Attribute wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert stellt die Bit-Position dar. Bit-Positionen beginnen mit Bit 0. Beispiel: 1 (binär) ist Bit 0 und 10000 (binär) ist Bit 4 festgelegt. Jedes Bit stellt eine Eigenschaft dar. Im Folgenden finden Sie einige Beispiele:

  - 10000 (Binary) hat den Dezimalwert 16 (das heißt, Bit 4 ist festgelegt).

  - 100 Millionen (binär) hat den Dezimalwert 256 (das heißt, Bit 8 ist festgelegt).

  - 1100 (Binary) hat den Dezimalwert 12 (d. r., Bits 2 und 3 sind festgelegt; die durch beide Bits dargestellten Eigenschaften sind aktiviert).

  - 1111000001 (Binary) hat den Dezimalwert 961 (d. r., Bits 0, 6, 7, 8 und 9 sind festgelegt; Eigenschaften für jedes dieser Bits sind aktiviert).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Schema Attribute für lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Beschreibung</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNSHostName</p></td>
<td><p>Ein vorhandenes Attribut in Active Directory-Domänendienste, das nun den Klassen <strong>msRTCSIP-Pool</strong> und <strong>msRTCSIP-MonitoringServer</strong> zugeordnet ist. Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Monitoring Server an.</p>
<p>Ein gültiger Wert für jedes Segment ist 63 Zeichen; ein gültiger Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>MSDS-SourceObjectDN</p></td>
<td><p>Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, die diesem Objekt entspricht. Dieses Attribut wird für die Expansion von Verteilergruppen und die automatische Teilnahme verwendet. Dieses Attribut ist im Standard Active Directory Schema für Windows Server 2003 R2 definiert.</p>
<p>Um zu vermeiden, dass ein Upgrade von AD DS auf Windows Server 2003 R2 erforderlich ist, erweitert Active Directory Schemavorbereitung das Windows Server 2003 Schema mit dieser Attributdefinition.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>"msexchucvoicemailsettings"</p></td>
<td><p>Dieses mehrwertige Attribut umfasst Einstellungen für Voicemail. Dieses Attribut ist für Exchange Unified Messaging (um) freigegeben.</p></td>
<td><p>Neu in Microsoft lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten. Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert. Dieses Attribut ist für Exchange 2013 freigegeben.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Dieses Attribut speichert Informationen zu Audiokonferenz-Anbietern für einen Benutzer.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Dieses Attribut verweist auf den vertrauenswürdigen Diensteintrag für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-applicationlist</p></td>
<td><p>Dieses Attribut enthält eine Liste der gehosteten Anwendungen auf dem Anwendungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Dieses Attribut gibt die Optionen für den Anwendungs Kontakt an.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Dieses Attribut enthält die primäre Sprache für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Dieses Attribut mit mehreren Werten enthält die sekundären Sprachen für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Dieses Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören. Der entsprechende Weiterleitungslink zu diesem Backlink <strong>-Attribut lautet msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Dieses Attribut verweist auf den Pool, zu dem dieser Anwendungsserver gehört. Dies ist der Weiterleitungslink. Der entsprechende abwärts Link ist <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Office Communications Server 2007 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (veraltet)</p></td>
<td><p>Dieses Attribut gibt den globalen Standardwert innerhalb der Gesamtstrukturgrenze für die Archivierung der gesamten Benutzerkommunikation an. Dies wird durch die Archivierungs-Agent-Schicht erzwungen. Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p><strong>True</strong>: Archivieren aller Benutzer</p></li>
<li><p><strong>False</strong>: nicht alle Benutzer archivieren</p></li>
</ul>
<p>Dieses Attribut steuert Global innerhalb der Gesamtstruktur Begrenzung, wie die Benutzerkommunikation innerhalb eines internen Netzwerks archiviert wird.</p>
<p><strong>Live Communications Server 2005 Verhalten (jetzt veraltet)</strong></p>
<p>Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p>0: Nachrichtentext archivieren [Bit 0]</p></li>
<li><p>1: Nachrichtentext nicht archivieren [Bit 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007 Verhalten</strong></p>
<p>Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (veraltet)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Office Communications Server 2007 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Office Communications Server 2007 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Dieses Attribut ist eine ganze Zahl, die als Bit-Feld verwendet wird, um zu steuern, ob die Kommunikation eines einzelnen Benutzers archiviert werden soll. Dieses Steuerelement wird von der Archivierungs-Agent-Schicht erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Der Bereich dieses Attributs ist für einen einzelnen Benutzer oder Kontakt spezifisch. Die gültigen Werte (und zugeordneten Bit-Positionen) in lync Server lauten wie folgt:</p>
<ul>
<li><p>0: nicht archivieren (keine Bit-Festlegung)</p></li>
<li><p>1: zurückgezogen (Bit-Position 0)</p></li>
<li><p>2: zurückgezogen (Bit-Position 1)</p></li>
<li><p>4: Archivieren der internen Kommunikation (Bit-Position 2)</p></li>
<li><p>8: Archivieren der Verbundkommunikation (Bit-Position 3)</p></li>
</ul>
<p>Zuvor gültige Werte in Live Communications Server 2005 lauten wie folgt:</p>
<ul>
<li><p>0: Verwenden Sie den von <strong>msRTCSIP-ArchiveDefault</strong> und <strong>msRTCSIP-ArchiveFederation</strong> in dieser Rangfolge definierten Standardwert:</p>
<ul>
<li><p>1: Archiv</p></li>
<li><p>2: nicht archivieren</p></li>
<li><p>3: Archivieren ohne Nachrichtentext</p></li>
</ul></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (veraltet)</p></td>
<td><p>Dieses Attribut definiert die Version des Archivierungsdiensts. Dieses Attribut ist ein monoton zunehmender ganzzahliger Typ, der mit jeder offiziellen Produktversion inkrementiert wird. Die zulässigen Werte sind:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Dieses Attribut gibt den FQDN des Back-End-Servers des Pools an. Da es nur einen einzelnen Back-End-Server pro Pool geben kann, handelt es sich um ein einwertiges Attribut.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Dieses Attribut enthält den Bezeichner des Pools, der das Konferenzverzeichnis hostet.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Dieses Attribut enthält den Bezeichner eines Konferenz Verzeichnisses.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Dieses Attribut enthält den Bezeichner des Pools, in den das Konferenzverzeichnis verschoben wird.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP – Standard</p></td>
<td><p>Dieses boolesche Attribut legt fest, ob es sich bei der Telefonverwendung um eine Standardverwendung handelt. Wenn dieses Attribut auf <strong>true</strong>festgelegt ist, ist die Telefonverwendung eine standardmäßige Verwendung und kann vom Administrator nicht gelöscht werden. Wenn dieses Attribut auf <strong>false</strong>festgelegt ist, kann die Verwendung gelöscht werden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer außerhalb der Organisation.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer, die sich innerhalb der Organisation befinden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält den Distinguished Name (DN) eines Standortprofil-Klassenobjekts, das ihm zugewiesen ist.</p>
<p>Link weiterleiten: <strong>Link ID 11036</strong></p>
<p>Der entsprechende abwärts Link ist <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (veraltet)</p></td>
<td><p>Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt. Die Richtlinie ist eine Standardrichtlinie, wenn Sie auf <strong>true</strong>festgelegt ist.</p></td>
<td><p>Neu in Office Communications Server 2007</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</p></td>
<td><p>Dieses Attribut gibt den FQDN der Edgeserver an, auf die der Zugriffs-Edgedienst, auf den direkt zugegriffen werden kann, oder das Hardwaregerät zum Lastenausgleich für einen Serverpool mit Zugriffs-Edgedienst. Wenn auf den Servern mit Zugriffs-Edgedienst nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und optional die Portnummer des Directors oder des Hardware-Lastenausgleichs an, der eine Directorpool bedient.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</p></td>
<td><p>Dieses Attribut stellt die Portnummer dar, die zum Herstellen einer Verbindung mit dem Server mit Zugriffs-Edgedienst verwendet werden soll.</p>
<p>Der gültige Wert ist ein ganzzahliger Wert, der den zu verwendenden Port angibt. Der Standardwert lautet 5061.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Standardtimeout Zeitraum für Anwesenheitsabonnements dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das standardmäßige Registrierungstimeout Fenster dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Standardtimeout Fenster für das Roaming-Datenabonnement dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Dieses Attribut wird in einer geteilten Domänentopologie verwendet und enthält einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut enthält eine benutzerfreundliche Beschreibung dieser Telefonroute oder Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Domänenname</p></td>
<td><p>Dieses Attribut stellt eine für die Registrierungsstelle konfigurierte Domäne dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Dieses Attribut gibt den FQDN des Servers an, auf dem Zugriffs-Edgedienst ausführt.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (veraltet)</p></td>
<td><p>Dieses Attribut steuert, ob ein Server eine Benachrichtigungsanforderung (Best Effort notify, BENOTIFY) anstelle einer Notify-Anforderung als Antwort auf eine subscribe-Anforderung eines Clients generiert. BENOTIFY ist eine leistungssteigernde Erweiterung des Subscribe-Benachrichtigungs Handshakes, bei dem der Server BENOTIFY-Anforderungen anstelle von regulären NOTIFY-Anforderungen generiert. Der Leistungsvorteil besteht darin, dass für eine BENOTIFY-Anforderung keine 200 OK-Antwort vom Client erforderlich ist, wenn die Notify-Anforderung dies tut.</p>
<p>Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</p>
<div>

> [!NOTE]  
> BENOTIFY-Anforderungen werden von Live Communications Server 2003 nicht unterstützt. Zur Zusammenarbeit mit Serveranwendungen, die mit der Live Communications Server 2003 Server-API geschrieben werden, die auf Live Communications Server 2005-und Drittanbieterservern ausgeführt wird, können BENOTIFY-Anforderungen deaktiviert werden, indem der Wert auf <STRONG>false</STRONG>festgelegt wird. BENOTIFY ist derzeit nicht Teil des IETF-Standardisierungsprozesses (Internet Engineering Task Force).


</div></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (veraltet)</p></td>
<td><p>Dieses Attribut ist ein globaler Switch, mit dem IT-Administratoren konfigurieren können, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen. Es ermöglicht einem Administrator das Überschreiben des <strong>FederationEnabled</strong> -Attributs eines einzelnen Benutzers. Dieses Attribut kann hilfreich sein, um das interne Netzwerk vor Internet Angriffen zu schützen, die möglicherweise durch Würmer, Viren oder gezielte Angriffe auf das Unternehmen verursacht werden.</p>
<p>Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: für öffentliche Chat Verbindungen aktiviert (Bit-Position 0)</p></li>
<li><p>2: reserviert (Bit-Position 1)</p></li>
<li><p>4: reserviert (Bit-Position 2)</p></li>
<li><p>8: reserviert (Bit-Position 3)</p></li>
<li><p>16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</p></li>
<li><p>128: UCEnabled (Benutzer für Unified Communications aktivieren) (Bit-Position 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bit-Position 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Dieses Attribut gibt an, ob die Enterprise-Dienste auf dem angegebenen Server geladen werden.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Dieses Attribut enthält die Wählnummer für den externen Zugriff.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Partnerverbund aktiviert ist. Sie wird von der Enterprise Services-Schicht erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</p>
<p>Link zurück: <strong>Link ID 11023</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (veraltet)</p></td>
<td><p>Dieses mehrwertige Zeichenfolgenattribut enthält eine Liste von Gateways und Ports (pro Gateway).</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (veraltet)</p></td>
<td><p>Dieses Attribut speichert Name: Wert-Paare. Das bereits definierte Name: Value-Paar ist für die Einstellung <strong>Abruf für Anwesenheit zulassen</strong> .</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gruppierung</p></td>
<td><p>Dieses Attribut ist ein eindeutiger Bezeichner einer Gruppe, die zum Gruppieren von Adressbucheinträgen verwendet wird.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Homeserver (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003 (nicht verwendet).</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Heimuser (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003 (nicht verwendet).</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Zugriff durch externe Benutzer aktiviert ist. Sie wird von der Enterprise Services-Schicht erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Reihe</p></td>
<td><p>Dieses einwertige Attribut enthält die Geräte-ID (entweder den SIP-URI oder den Tel-URI des Telefons, den der Benutzer steuert), der von lync für die Telefonie verwendet wird. Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet und wird indiziert. Wenn ein Benutzer für Enterprise-VoIP aktiviert ist, wird in diesem Attribut die normalisierte E. 164-Version der Telefonnummer des Benutzers gespeichert.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Dieses Attribut mit einem Wert enthält den SIP-URI des CSTA-SIP-Gatewayservers. Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet, jedoch nicht indiziert.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der lokalen normalisierungs Namen (Distinguished Names, DN), die diesem Standortprofil zugeordnet sind. Der Typ dieses Attributs ist eine DN-Binärdatei. Es gibt eine 1: n-Beziehung zwischen Standortprofil und lokalen Normalisierungsregeln. Die Sortierung der Liste der lokalen normalisierungs-DNS muss in der vom Administrator angegebenen Reihenfolge aufrecht erhalten werden. Die Beibehaltung der Reihenfolge wird durch den binären Teil der DN-Binärdatei verwaltet, der den Reihenfolgeindex angibt.</p>
<p>Link weiterleiten: <strong>Link ID 11034</strong></p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Dieses Attribut enthält eine Liste von Optionen für die Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält einen Anzeigenamen für das Standortprofil, das angibt, welche Position dieses Profil darstellt. Da es mehrere Standortprofile geben kann, benötigt der Administrator eine Möglichkeit, zwischen unterschiedlichen Profilen zu unterscheiden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Standortprofil-Distinguished Names. Dieses Attribut gibt die Rückverknüpfung zu einem oder mehreren Standortprofilen an.</p>
<p>Link zurück: <strong>Link ID 11035</strong></p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Dieses Attribut enthält die Optionen für das Standortprofil.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Dieses mehrwertige Attribut umfasst eine Liste von Anwendungs Kontakten.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Dieses mehrwertige Attribut umfasst eine Liste von Standortprofilen.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</p></td>
<td><p>Dieses Attribut stellt die maximale Anzahl ausstehender Suchanforderungen pro Server dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</p></td>
<td><p>Das-Attribut stellt die maximale Anzahl von Abonnements pro Benutzer dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das maximale Timeout Fenster für Abonnements dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für maximale Registrierungen dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für das maximale Roaming von Daten Abonnements dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Dieses Attribut ist ein Dienststeuerungspunkt-Attribut unter der Computerklasse, das einen Link zurück zur MCU-Factory (Multipoint Control Unit) angibt, zu der es gehört. Dieser Dienst Steuerungs Pfad und das Attribut werden für jede Microsoft MCU erstellt. Jede Microsoft MCU muss den Back-End-Server des Pools finden, zu dem Sie gehört, um Einstellungen auf Poolebene daraus abzurufen.</p>
<p>Der Wert dieses Attributs ist der DN (Distinguished Name) der MCU-Factory. Hierbei handelt es sich um ein einwertiges Attribut, das für die Replikation des globalen Katalogs gekennzeichnet ist.</p>
<p>Link weiterleiten: <strong>Link ID 11026</strong></p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Dies ist ein reserviertes Attribut mit mehreren Zeichenfolgen. In diesem Attribut gespeicherte Einstellungen werden als Name = Wert-Paare dargestellt. Aktuell definierte Name = Wert-Paare sind:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Hierbei handelt es sich um ein einwertiges Attribut, das den Distinguished Name (DN) einer einzelnen MCU-Factory enthält, die einem Pool zugeordnet ist.</p>
<p>Link weiterleiten: <strong>Link ID 11024</strong></p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Dieses Attribut ist eine einwertige Zeichenfolge, die die GUID des MCU-Factory-Anbieters angibt. Basierend auf dem GUID-Wert bestimmt der MCU-factoryprozess, ob dieser MCU-Typ gewartet werden soll. Wenn der GUID-Wert <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>ist, wird der MCU-factoryprozess (standardmäßig in lync Server verfügbar) verarbeitet. Für jeden anderen GUID-Wert wird der MCU-Prozess vom MCU-factoryprozess nicht gewartet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names (DN). Dieses Attribut enthält eine Liste aller MCU-Server desselben Typs und Anbieters, die dieser MCU-Factory zugeordnet sind. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p>
<p>Link zurück: Link ID 11027</p>
<p>Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Dieses Attribut ist eine einwertige Zeichenfolge, die das Medium angibt, mit dem die MCU umgehen kann.</p>
<p>Unterstützte gültige Typen:</p>
<ul>
<li><p>Besprechungs</p></li>
<li><p>Audio-Video</p></li>
<li><p>Chat</p></li>
<li><p>Telefon-conf</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Dieses Attribut ist eine einwertige Zeichenfolge, die den Namen eines MCU-Anbieters angibt. Alle Microsoft-MCU gibt dieses Attribut als <strong>Microsoft Corporation</strong>an.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert unterschiedliche Besprechungsoptionen, die Global für alle Benutzer oder Kontaktobjekte aktiviert sind. Dieses Attribut ist ein Bitmaskenwert des Typs Integer.</p>
<p>Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants lautet ist keine (Benutzer dürfen keine anonymen Benutzer zu Besprechungen einladen) (keine Bits festgelegt)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants lautet ist jeder (gestatten Sie allen Benutzern, anonyme Benutzer zu Besprechungen einzuladen) (Bit-Position 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants lautet ist UsePerUserSetting (Benutzern das einladen anonymer Benutzer zu Besprechungen basierend auf der Einstellung pro Benutzer) (Bit-Position 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (Besprechungsrichtlinie wird pro Benutzerdefiniert) (Bit-Position 4)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-meetingpolicy "(veraltet)</p></td>
<td><p>Dieses Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator diesem Benutzer als einwertiges Attribut zugewiesen hat.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für das minimale Anwesenheits Abonnement dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für die minimale Registrierung dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für das minimale Roaming-Datenabonnement dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags zur Definition von Mobilitätseinstellungen.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein mobilitätsrichtlinien Objekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (veraltet)</p></td>
<td><p>Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen ein Benutzer für die SIP-Kommunikation registrieren und die Anwesenheit abonnieren kann.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Dieses Attribut gibt die Optionen an, die für das Benutzer-oder Kontaktobjekt aktiviert sind. Dieses Attribut ist ein Bitmaskenwert vom Typ Integer. Jede Option wird durch ein Bit dargestellt. Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</p>
<p>Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: für die Verbindung mit öffentlichen Sofortnachrichtendiensten (Bit-Position 0) aktiviert</p></li>
<li><p>2: reserviert (Bit-Position 1)</p></li>
<li><p>4: reserviert (Bit-Position 2)</p></li>
<li><p>8: reserviert (Bit-Position 3)</p></li>
<li><p>16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</p></li>
<li><p>128: UCEnabled (Aktivieren von Benutzern für UC) (Bit-Position 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bit-Position 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Dieses Attribut wird in den Ressourcen-und zentralen Gesamtstruktur-Topologien verwendet, um einmaliges Anmelden zu aktivieren, wenn die Objekt-Nr eines Benutzers aus dem Windows NT Server-Prinzipal Konto in dieses Attribut des entsprechenden Benutzer-oder Kontaktobjekts in der Ressourcen-oder zentralen Gesamtstruktur kopiert wird. Communicator-Webzugriff sucht in AD DS mithilfe dieses Attributs oder der Objekt-Nr des Benutzers nach einem Benutzer. Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Dieses Attribut ist der URN (Uniform Resource Name) des Besitzers für einen Anwendungs Kontakt.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (veraltet)</p></td>
<td><p>Dieses einwertige Zeichenfolgenattribut enthält ein Muster, das zum Zuordnen von Wähl Nummern zum E. 164-Format verwendet wird. Wenn die Wählnummer mit diesem Muster übereinstimmt, wird die Übersetzung auf die gewählte Nummer angewendet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der Distinguished Names (DN) der Telefonroute. Dieses Attribut gibt den hinteren Link zu einer oder mehreren Telefonrouten an.</p>
<p>Link zurück: <strong>Link ID 11033</strong></p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (veraltet)</p></td>
<td><p>Dieses einfache Unicode-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass vom Administrator einfach auf ihn verwiesen werden kann.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (veraltet)</p></td>
<td><p>Dieses Attribut ist eine Unicode-Zeichenfolge mit einer einwertigen Wert. Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format. Die XML-Schema Definition ist in verschiedenen Richtlinientypen üblich, nur die Einstellungen unterscheiden sich für jeden Richtlinientyp.</p>
<p>Die XML-Schema Definition (XSD) ist wie folgt definiert:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Spalte PolicyData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-policyType (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut enthält den Richtlinientyp. Gültige Richtlinientypen lauten wie folgt:</p>
<ul>
<li><p>Besprechungs</p></li>
<li><p>Telefonie</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Dieses Attribut gibt einen Link zurück zu dem Pool, zu dem ein Computer gehört. Dieses Attribut wird unabhängig davon festgelegt, ob der Computer die Standard Edition oder die Enterprise Edition von lync Server ausführt. Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</p>
<p>Der gültige Wert ist der Domänenname des Pools.</p>
<p>Link weiterleiten: <strong>Link ID 11022</strong></p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste der Distinguished Names (DN) von Pools enthält, mit denen die MCU-Factory verknüpft ist.</p>
<p>Link zurück: <strong>Link ID 11025</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Dieses Attribut gibt einen beliebigen Namen für einen Pool an, der von der Verwaltungskonsole angezeigt wird. Dieser Name kann vom Administrator geändert werden.</p>
<p>Der gültige Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Dieses Attribut ist ein einwertiger Zeichenfolgenwert. Der Wert dieses Attributs stellt, sofern vorhanden, den Domänen-FQDN des Pools dar, wenn der Administrator eine Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory Domänenstruktur entspricht, in der das Front-End-Pool erstellt wird (beispielsweise ein SIP Namespace, der von Domain Name System (DNS) Namespace nicht verbunden ist).</p>
<p>Es wird empfohlen, den Domänen-FQDN Front-End-Pool Domänennamen als Active Directory Domäne, in der sich der Pool befindet, dem Domänennamens Teil zuzuordnen. Wenn in diesem Attribut kein Wert vorhanden ist, wird der Front-End-Pool-FQDN standardmäßig auf die Active Directory Domänennamenstruktur, wie durch das <strong>dNSHostName</strong> -Attribut gekennzeichnet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Eine mehrwertige Liste der Domänennamen aller lync Server Enterprise Edition-Server, die einem Pool zugeordnet sind. Dieses Attribut vom Typ Integer definiert, ob der Pool Sofortnachrichten und Anwesenheitsinformationen und Besprechungen unterstützt.</p>
<p>Die möglichen gültigen Wertetypen lauten wie folgt:</p>
<ul>
<li><p>Nicht definiert: Chat-und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</p></li>
<li><p>1: Chat und Anwesenheitsdienst (lync Server)</p></li>
<li><p>2: Sofortnachrichten und Anwesenheits-und Besprechungs Dienst (lync Server)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pooltype</p></td>
<td><p>Dieses Attribut gibt an, ob ein Serverpool Standard Edition-Server oder Enterprise Edition-Server ausführt. Dieses Attribut ist ein Bitmaskenwert vom Typ Integer. Jede Option wird durch ein Bit dargestellt.</p>
<p>Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: Standard Edition-Server, hostet Benutzer (Bit-Position 0)</p></li>
<li><p>2: Enterprise Edition-Server, hostet Benutzer (Bit-Position 1)</p></li>
<li><p>4: Standard Edition-Server, hostet Anwendungen (Bit-Position 2)</p></li>
<li><p>8: Enterprise Edition-Server, hostet Anwendungen (Bit-Position 3)</p></li>
</ul>
<p>Da lync Server keine Pools unterstützt, die nur Anwendungen hosten, gelten die folgenden Werte nur:</p>
<ul>
<li><p>5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 0 und 2)</p></li>
<li><p>10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 1 und 3)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Dieses Attribut definiert die Pool Version. Es handelt sich um einen ganzzahligen Typ, der mit jeder Hauptprodukt Version inkrementiert wird.</p>
<p>Die möglichen gültigen Wertetypen lauten wie folgt:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags, die Anwesenheitseinstellungen definieren.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein Präsenz Richtlinienobjekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Dieses Attribut aktiviert einen Benutzer oder Kontakt für SIP-Messaging. Sie wird der Contact-Klasse hinzugefügt, da in der Topologie der zentralen Gesamtstruktur Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</p>
<p>Der gültige Wert ist der DN der Standard Edition-Server-oder Enterprise Edition-Front-End-Pool, in der ein Benutzer verwaltet wird.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Dieses Attribut enthält die SIP-Adresse eines bestimmten Benutzers.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Privatsphäre</p></td>
<td><p>Dieses Attribut enthält die Geräte-ID des privaten Leitungen-Geräts.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP – routingfähig</p></td>
<td><p>Dieses Attribut ist ein boolesches Attribut, das verwendet wird, um zu bestimmen, ob lync Server berechtigt ist, zu diesem Dienst unter Verwendung seiner GRUU-Adresse weiterzuleiten. Wenn dieser Wert auf <strong>true</strong>festgelegt ist, ist lync Server berechtigt, zu diesem Dienst weiterzuleiten. Wenn dieser Wert auf " <strong>false</strong>" festgelegt ist, ist lync Server nicht berechtigt, zu diesem Dienst weiterzuleiten.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut definiert ein Attribut, das die Verwendung für eine Telefonroute qualifiziert. Die Auswahl einer Telefonroute wird basierend auf zwei Elementen bestimmt: dem Verwendungsattribut, das der Telefonroute zugewiesen ist, und den zulässigen Richtlinien Verwendungsattributen des Anrufers. Die erste Telefonroute mit einem Nutzungs Attribut, das mit der zulässigen Verwendung des Anrufers übereinstimmt, wird ausgewählt.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (veraltet)</p></td>
<td><p>Dieses mehrwertige Distinguished Name (DN)-Attribut enthält eine Liste der definierten Namen für die Routenverwendung.</p>
<p>Link weiterleiten: <strong>Link ID 11032</strong></p>
<p>Dieses Attribut ist eine Weiterleitungs Verknüpfung mit der entsprechenden <strong>msRTCSIP-PhoneRouteBL-</strong>Back Link.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Dieses Attribut enthält den DN, der auf den Pool zeigt, für den der gesamte an diesen MCU-oder vertrauenswürdigen Dienst adressierte SIP-Datenverkehr durchlaufen werden muss.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass von einem Administrator einfach auf ihn verwiesen werden kann.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Schemaversion</p></td>
<td><p>Dieses Attribut stellt die derzeit in der Organisation bereitgestellte Schemaversion dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (veraltet)</p></td>
<td><p>Dieses Attribut schränkt die Anzahl der Suchergebnisse ein, die von einer Verzeichnissuche zurückgegeben werden, wenn ein Benutzer einen Kontakt mithilfe von Communicator sucht. Dieses Attribut setzt den vom Client bereitgestellten Wert außer Kraft.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (veraltet)</p></td>
<td><p>Dieses Attribut schränkt die Anzahl der zurückgegebenen Suchanforderungen ein.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Dieses mehrwertige Attribut ist ein Link zurück, der eine Liste mit Distinguished Names (DN) enthält. Diese DNS verweist auf ein Pool-oder <strong>TrustedService</strong> -Objekt.</p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names. Diese Distinguished Names sind Back Links, die auf andere Serverobjekte verweisen, denen ein Standardmäßiges Standortprofil zugewiesen werden kann.</p>
<p>Link zurück: <strong>Link ID 11037</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Dieses Back Link-Attribut verweist nur auf Pools und Vermittlungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server Version vom</p></td>
<td><p>Dieses Attribut definiert die Versionsinformationen des Servers. Diese Versionsnummer gilt für alle Serverrollen. Es handelt sich um eine monoton wachsende ganze Zahl, die mit jeder offiziellen Produktversion inkrementiert wird.</p>
<p>Die möglichen gültigen Werte lauten wie folgt:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: lync Server 2010</p></li>
<li><p>6: lync Server 2013</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Quellobjekttyp</p></td>
<td><p>Dieses einwertige Attribut vom Typ Integer gibt den Typ des Objekts an, auf das das <strong>msDS-SourceObjectDN</strong> zeigt, wie folgt:</p>
<ul>
<li><p>NULL | 0x00000001: stellt ein Windows NT Server-Prinzipal Benutzerobjekt aus einer anderen Gesamtstruktur dar.</p></li>
<li><p>Die folgenden Attribute stellen einen Gruppentyp aus einer anderen Gesamtstruktur für die Erweiterung der Verteilergruppe dar:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: stellt eine automatische Telefonzentrale oder ein Teilnehmerzugriffs Objekt aus derselben Gesamtstruktur oder einer anderen Gesamtstruktur dar.</p></li>
</ul></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Mit diesem Attribut können Sie ein Benutzer-oder Kontaktobjekt von einem lync Server Pool in einen anderen migrieren. Dieses Attribut wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstruktur-Topologie Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</p>
<p>Der gültige Wert ist der DN des Ziel Standard Edition-Server oder Front-End-Pool, zu dem ein Benutzer verschoben werden soll.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (veraltet)</p></td>
<td><p>Dieses einwertige Zeichenfolgenattribut enthält ein Telefonnummernmuster oder einen Bereich, der an die in <strong>msRTCSIP-Gateways</strong>definierten Gateways weitergeleitet werden soll.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Dieses Attribut speichert Name/Wert-Paare für Zielrichtlinien für lync Server Benutzer.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Mandanten-Nr</p></td>
<td><p>Dieses Attribut speichert den eindeutigen Bezeichner für einen Mandanten.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (veraltet)</p></td>
<td><p>Dieses Attribut wird von der VoIP-Funktion von lync Server verwendet und enthält die Übersetzungs Zeichenfolge, die für die gewählte Nummer angewendet wird, wenn eine Übereinstimmung gefunden wird.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Dieses Attribut ist ein String-Wert, der den FQDN der MCU enthält. Hierbei handelt es sich um ein einwertiges Attribut. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Dieses Attribut ist ein String-Wert, der den FQDN des Servers mit Proxy Server enthält. Dieses Attribut ist ein einwertiger Wert. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Dieses Attribut ist ein Attribut mit einem Wert, das den FQDN eines vertrauenswürdigen Servers darstellt.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Dieses Attribut gibt die Versionsnummer eines Servers in der Liste der vertrauenswürdigen Server an.</p>
<p>Die möglichen gültigen Werte lauten wie folgt:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: lync Server 2010</p></li>
<li><p>6: lync Server 2013</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Dieses Attribut definiert die Optionen, die für den vertrauenswürdigen Dienst aktiviert sind.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, beispielsweise einen Medien Relay-Authentifizierungsdienst. Ein Medien Relay-Authentifizierungsdienst (physisch zusammen mit dem Edgeserver, auf dem der A/V-Konferenzdienst ausgeführt wird) muss einem Pool zugeordnet sein, um audioszenarioe für Remotebenutzer zu unterstützen.</p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Dieses Attribut ist eine ganze Zahl, die die Portnummer definiert, die zum Herstellen einer Verbindung mit diesem GRUU-Dienst verwendet wird.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Dieses Attribut ist ein String-Wert, der den Typ des GRUU-Diensts definiert, den er darstellt.</p>
<p>Die gültigen GRUU-Diensttypen lauten wie folgt:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Medien Relay-Authentifizierungsdienst (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension-GAV</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Dieses Attribut ist ein String-Wert, der den FQDN des IIS-lync Server Webdienste enthält. Hierbei handelt es sich um ein einwertiges Attribut. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert unterschiedliche UC-Optionen, die Global für alle Benutzer-oder Kontaktobjekte aktiviert sind. Dieses Attribut ist ein Bitmaskenwert des Typs Integer. Jede Option wird durch das vorhanden sein von ein Bit dargestellt.</p>
<p>Der mögliche gültige Wert (und die zugehörige Bit-Position) lauten wie folgt:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (Bit-Position 2)</p></li>
</ul>
<p>Wenn dieses Bit festgelegt ist, wird die UC-Richtlinie pro Benutzerdefiniert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator diesem Benutzer zugewiesen hat.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (veraltet)</p></td>
<td><p>Dieses Attribut enthält eine Liste aller Domänen in einer Gesamtstruktur, die SIP-aktivierte Benutzer hosten. Der Standardwert ist eine leere Liste, die angibt, dass alle Domänen in der Gesamtstruktur SIP-fähig sind.</p>
<p>Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen einzelner Domänen darstellen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Dieses Attribut bestimmt, ob der Benutzer derzeit für lync Server aktiviert ist.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Name-Wert-Paaren im Format &quot;von Name = Value. &quot; Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt zeigt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Dieses Attribut speichert Name/Wert-Paare für Benutzerrichtlinien.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut mit einer Liste von Distinguished Names with Binary (DN_WITH_BINARY), die auf globale Benutzerrichtlinien verschiedener Typen verweist. Der binäre Teil gibt den Typ der Richtlinie an, auf die der DN-Teil zeigt.</p>
<p>Die gültigen binären Werte lauten wie folgt:</p>
<ul>
<li><p>0x00000001: Besprechungsrichtlinie</p></li>
<li><p>0x00000002: UC-Richtlinie</p></li>
<li><p>0x00000005: Anwesenheitsrichtlinie</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut. Dieses Attribut ist für die zukünftige Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Dieses einwertige Attribut verweist auf den Pool oder Standard Edition-Server, zu dem die Webkomponenten gehören.</p>
<p>Link weiterleiten: <strong>Link ID 11028</strong></p>
<p>Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names. Dieses Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</p>
<p>Link zurück: <strong>Link ID 11029</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Dieses vorhandene Active Directory-Attribut wird von der Telefonie verwendet, um die Liste der alternativen TCP/IP-Adressen für ein Telefon anzugeben.</p></td>
<td><p>Neu in Windows Server 2008 Betriebssystem.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Dieses vorhandene Active Directory Attribut wird von den VoIP-Komponenten in lync Server nur für Kontaktobjekte verwendet, um Anrufe an die automatische Telefonzentrale und Teilnehmerzugriffsnummern weiterzuleiten. Die bedingungslose Anruf Weiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert. Dieses Konto wird für den speziellen Zweck der automatischen Telefonzentrale und des Teilnehmerzugriffs erstellt. Die Attribute dieses Kontos sollten von Administratoren nicht geändert werden.</p></td>
<td><p>Neu im Betriebssystem Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Dieses vorhandene Active Directory mehrwertige Attribut ist Teil des grundlegenden Active Directory Schemas, das in Windows 2000 eingeführt wurde. Dieses Attribut enthält die verschiedenen X400-, x500-und SMTP-Adressen der e-Mail-Adresse des Benutzers. In Live Communications Server 2003 und höher wird der SIP-URI des Benutzers mithilfe des &quot;SIP:&quot; -Tags zu dieser Liste hinzugefügt.</p>
<p>Die folgenden Anwendungen durchsuchen den SIP-URI des Benutzers aus diesem Attribut:</p>
<ul>
<li><p>Microsoft Office Outlook 2003 Messaging-und Zusammenarbeitsclient</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Neu im Betriebssystem Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Dieses vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</p></td>
<td><p>Neu im Betriebssystem Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

