---
title: 'Lync Server 2013: Schema Attribute und Beschreibungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Schema Attribute und Beschreibungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In diesem Abschnitt werden alle Schema Attribute beschrieben, die von lync Server 2013 verwendet werden. Informationen zu den Klassen, die Attributen zugeordnet sind, finden Sie unter [Schema Attribute nach Klasse in lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Eine Liste der Klassen und Attribute, die in lync Server 2013 neu sind, finden Sie unter [Schema Änderungen in lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Attribute, die verknüpfte Paare sind, werden als Weiterleitungs-oder zurück-Links angegeben. Ein Attribut, das auf ein anderes Objekt verweist, ist ein Weiterleitungslink; das Attribut des anderen Objekts, das auf das erste Objekt zurückverweist, ist ein Link zurück. Forward-Links sind aktualisierbare, während zurück-Links schreibgeschützt sind.

Einige Attribute weisen einen Bitmaskenwert auf. Bei diesen Attributen wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert stellt die Bit-Position dar. Bit-Positionen beginnen mit Bit 0. Beispiel: 1 (Binary) ist Bit 0-Satz und 10000 (binär) ist Bit 4 gesetzt. Jedes Bit stellt eine Eigenschaft dar. Im folgenden finden Sie einige Beispiele:

  - 10000 (Binary) hat einen Dezimalwert von 16 (das heißt, Bit 4 ist festzulegen).

  - 100 Millionen (Binary) hat einen Dezimalwert von 256 (das heißt, Bit 8 ist festzulegen).

  - 1100 (Binary) hat den Dezimalwert 12 (das heißt, Bits 2 und 3 werden festgesetzt; die von beiden Bits dargestellten Eigenschaften sind aktiviert).

  - 1111000001 (Binary) hat einen Dezimalwert von 961 (das heißt, Bits 0, 6, 7, 8 und 9 werden festgesetzt; Eigenschaften für jedes dieser Bits sind aktiviert).

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
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNSHostName</p></td>
<td><p>Ein vorhandenes Attribut in den Active Directory-Domänendiensten, das jetzt den <strong>Attribut msRTCSIP-</strong> und <strong>Attribut msRTCSIP-MonitoringServer</strong> -Klassen zugeordnet ist. Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Überwachungsservers an.</p>
<p>Ein gültiger Wert für jedes Segment ist 63 Zeichen; ein gültiger Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>MSDS-SourceObjectDN</p></td>
<td><p>Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, die diesem Objekt entspricht. Dieses Attribut wird für die Erweiterung der Verteilergruppe und für die automatische Anwesenheit verwendet. Dieses Attribut ist im standardmäßigen Active Directory-Schema für Windows Server 2003 R2 definiert.</p>
<p>Um zu vermeiden, dass ein Upgrade von AD DS auf Windows Server 2003 R2 erforderlich ist, wird das Windows Server 2003-Schema durch die Active Directory-Schemavorbereitung mit dieser Attributdefinition erweitert.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Dieses mehrwertige Attribut enthält Einstellungen für Voicemail. Dieses Attribut wird für Exchange Unified Messaging (um) freigegeben.</p></td>
<td><p>Neu in Microsoft lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien. Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei. Dieses Attribut wird für Exchange 2013 freigegeben.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-AcpInfo</p></td>
<td><p>Dieses Attribut speichert Informationen zu Audiokonferenz-Anbietern für einen Benutzer.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationDestination</p></td>
<td><p>Dieses Attribut verweist auf den vertrauenswürdigen Diensteintrag für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-applicationlist</p></td>
<td><p>Dieses Attribut enthält eine Liste der gehosteten Anwendungen auf dem Anwendungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationOptions</p></td>
<td><p>Dieses Attribut gibt die Optionen für den Anwendungs Kontakt an.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Dieses Attribut enthält die primäre Sprache für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Dieses Attribut mit mehreren Werten enthält die sekundären Sprachen für den Anwendungs Kontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ApplicationServerBL</p></td>
<td><p>Dieses Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören. Der entsprechende Forward-Link zu diesem zurück Link-Attribut lautet <strong>Attribut msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Dieses Attribut verweist auf den Pool, zu dem dieser Anwendungsserver gehört. Dies ist der Link weiterleiten. Der entsprechende rückwärts Link lautet <strong>Attribut msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ArchiveDefault (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>Veraltet in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ArchiveDefaultFlags (veraltet)</p></td>
<td><p>Dieses Attribut gibt den globalen Standardwert innerhalb der Gesamtstrukturgrenze für die Archivierung der gesamten Benutzerkommunikation an. Dies wird vom Archivierungs-Agent-Layer erzwungen. Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p><strong>True</strong>: alle Benutzer archivieren</p></li>
<li><p><strong>Falsch</strong>: nicht alle Benutzer archivieren</p></li>
</ul>
<p>Dieses Attribut steuert Global innerhalb der Gesamtstruktur-Grenze, wie die Benutzerkommunikation in einem internen Netzwerk archiviert wird.</p>
<p><strong>Live Communications Server 2005-Verhalten (jetzt eingestellt)</strong></p>
<p>Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p>0: Archivieren des Nachrichtentexts [Bit 0]</p></li>
<li><p>1: den Nachrichtentext nicht archivieren [Bit 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007-Verhalten</strong></p>
<p>Der Wertebereich für dieses Attribut lautet wie folgt:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (eingestellt)</p></li>
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
<td><p>Attribut msRTCSIP-ArchiveFederationDefault (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>Veraltet in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ArchiveFederationDefaultFlags (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>Veraltet in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ArchivingEnabled</p></td>
<td><p>Dieses Attribut ist eine ganze Zahl, die als Bitfeld verwendet wird, um zu steuern, ob die Kommunikation eines einzelnen Benutzers archiviert werden soll. Dieses Steuerelement wird vom Archivierungs-Agent-Layer erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Der Bereich dieses Attributs ist für einen einzelnen Benutzer oder Kontakt spezifisch. Die gültigen Werte (und zugeordnete Bit-Positionen) in lync Server lauten wie folgt:</p>
<ul>
<li><p>0: nicht archivieren (kein Bit-Satz)</p></li>
<li><p>1: eingestellt (Bit-Position 0)</p></li>
<li><p>2: eingestellt (Bit-Position 1)</p></li>
<li><p>4: Archivieren interner Kommunikation (Bit-Position 2)</p></li>
<li><p>8: Archivieren der Föderations Kommunikation (Bit-Position 3)</p></li>
</ul>
<p>Zuvor gültige Werte in Live Communications Server 2005 lauten wie folgt:</p>
<ul>
<li><p>0: Verwenden Sie den Standardwert, der in dieser Rangfolge von <strong>Attribut msRTCSIP-ArchiveDefault</strong> und <strong>Attribut msRTCSIP-ArchiveFederation</strong> definiert ist:</p>
<ul>
<li><p>1: Archivieren</p></li>
<li><p>2: nicht archivieren</p></li>
<li><p>3: Archivieren ohne Nachrichtentext</p></li>
</ul></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ArchivingServerData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ArchivingServerVersion (veraltet)</p></td>
<td><p>Dieses Attribut definiert die Version des Archivierungsdiensts. Bei diesem Attribut handelt es sich um einen monoton zunehmenden ganzzahligen Typ, der mit jeder offiziellen Produktversion inkrementiert wird. Die möglichen gültigen Werte lauten:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-BackEndServer</p></td>
<td><p>Dieses Attribut gibt den FQDN des Back-End-Servers des Pools an. Da es nur einen einzigen Back-End-Server pro Pool geben kann, handelt es sich hierbei um ein Single-Value-Attribut.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Dieses Attribut enthält den Bezeichner des Pools, der das Konferenzverzeichnis hostet.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Dieses Attribut enthält den Bezeichner eines Konferenz Verzeichnisses.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Dieses Attribut enthält den Bezeichner des Pools, in den das Konferenzverzeichnis verschoben wird.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Standard</p></td>
<td><p>Dieses boolesche Attribut definiert, ob es sich bei der Verwendung des Telefons um eine Standardverwendung handelt. Wenn dieses Attribut auf " <strong>true</strong>" festgelegt ist, handelt es sich bei der Verwendung des Telefons um eine Standardverwendung, die vom Administrator nicht gelöscht werden kann. Wenn dieses Attribut auf " <strong>false</strong>" festgelegt ist, kann die Verwendung gelöscht werden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich außerhalb der Organisation befinden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich innerhalb der Organisation befinden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefaultLocationProfileLink (veraltet)</p></td>
<td><p>Dieses Attribut mit einem Wert enthält den Distinguished Name (DN) eines ihm zugewiesenen Standortprofil-Klassenobjekts.</p>
<p>Link weiterleiten: <strong>Link-ID 11036</strong></p>
<p>Der entsprechende rückwärts Link lautet <strong>Attribut msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-DefaultPolicy (veraltet)</p></td>
<td><p>Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt. Die Richtlinie ist eine Standardrichtlinie, wenn Sie auf " <strong>true</strong>" festgelegt ist.</p></td>
<td><p>Neu in Office Communications Server 2007</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</p></td>
<td><p>Dieses Attribut gibt den FQDN des Edge-Servers an, auf dem der Access-Edgedienst ausgeführt wird, wenn er direkt aufgerufen werden kann, oder des Hardwarelastenausgleichs für einen Serverpool, auf dem Access Edge Service ausgeführt wird. Wenn auf den Servern, auf denen Access Edge Service ausgeführt wird, nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und optional die Portnummer des Directors oder des Hardwarelastenausgleichs an, der einen Director-Pool bereitstellt.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</p></td>
<td><p>Dieses Attribut stellt die Portnummer dar, die für die Verbindung mit dem Server, auf dem Access Edge Service ausgeführt wird, verwendet werden soll.</p>
<p>Der gültige Wert ist ein ganzzahliger Wert, der den zu verwendenden Port angibt. Der Standardwert ist 5061.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Standardtimeout Zeitraum für Anwesenheitsabonnements dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-DefRegistrationTimeout (veraltet)</p></td>
<td><p>Dieses Attribut steht für das Standardtimeout Fenster für die Registrierung.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut steht für das Standardtimeout Fenster des Roaming-Daten Abonnements.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Dieses Attribut wird in einer geteilten Domänentopologie verwendet und enthält einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Description (veraltet)</p></td>
<td><p>Dieses Single-Value-UNICODE-Zeichenfolgenattribut enthält eine Beschreibung dieser Telefonroute oder Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-DomainData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Domänenname</p></td>
<td><p>Dieses Attribut stellt eine für die Registrierungsstelle konfigurierte Domäne dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-EdgeProxyData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Dieses Attribut gibt den FQDN des Servers an, auf dem Access Edge-Dienst ausgeführt wird.</p>
<p>Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-EnableBestEffortNotify (veraltet)</p></td>
<td><p>Dieses Attribut steuert, ob ein Server als Antwort auf eine subscribe-Anforderung von einem Client eine Aufforderung zur Benachrichtigung über beste Leistung (BENOTIFY) anstelle einer Benachrichtigungsanforderung generiert. BENOTIFY ist eine leistungsverbessernde Erweiterung des Subscribe-Benachrichtigungs Handshakes, bei der der Server statt regelmäßiger Benachrichtigungsanforderungen BENOTIFY-Anforderungen generiert. Der Leistungsvorteil besteht darin, dass eine BENOTIFY-Anforderung keine 200-OK-Antwort vom Client erfordert, wie dies bei der Benachrichtigungsanforderung der Fall ist.</p>
<p>Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 unterstützt keine BENOTIFY-Anforderungen. Um mit Serveranwendungen zu interagieren, die mit der Live Communications Server 2003-Server-API auf Live Communications Server 2005-und Drittanbieterservern geschrieben wurden, können BENOTIFY-Anforderungen deaktiviert werden, indem der Wert auf <STRONG>false</STRONG>festgelegt wird. BENOTIFY ist derzeit nicht Teil des IETF (Internet Engineering Task Force) SIP-Standardisierungsprozesses.


</div></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-EnableFederation (veraltet)</p></td>
<td><p>Dieses Attribut ist ein globaler Schalter, den IT-Administratoren verwenden, um zu konfigurieren, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen. Sie ermöglicht es einem Administrator, das <strong>FederationEnabled</strong> -Attribut eines einzelnen Benutzers zu überschreiben. Dieses Attribut kann hilfreich sein, um das interne Netzwerk vor Internet Angriffen zu schützen, die möglicherweise durch Würmer, Viren oder gezielte Angriffe auf das Unternehmen verursacht werden.</p>
<p>Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: aktiviert für öffentliche Chat Verbindungen (Bit-Position 0)</p></li>
<li><p>2: reserviert (Bit-Position 1)</p></li>
<li><p>4: reserviert (Bit-Position 2)</p></li>
<li><p>8: reserviert (Bit-Position 3)</p></li>
<li><p>16: Remote-Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen (Bit-Position 6)</p></li>
<li><p>128: UCEnabled (Aktivieren von Benutzern für Unified Communications) (Bit-Position 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Aktivieren des Benutzers für öffentliche Chat Verbindungen) (Bit-Position 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bit-Position 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-EnterpriseServices</p></td>
<td><p>Dieses Attribut gibt an, ob die Enterprise-Dienste auf dem angegebenen Server geladen werden.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-ExtensionData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ExternalAccessCode</p></td>
<td><p>Dieses Attribut enthält die Wähl Vorwahl für den externen Zugriff.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-FederationEnabled</p></td>
<td><p>Dieses Attribut steuert, ob ein einzelner Benutzer für den Verbund aktiviert ist. Sie wird von der Enterprise Services-Schicht erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-FrontEndServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</p>
<p>Link zurück: <strong>Link-ID 11023</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Gateways (veraltet)</p></td>
<td><p>Dieses Attribut für mehrwertige Zeichenfolgen enthält eine Liste der Gateways und Ports (pro Gateway).</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-GlobalSettingsData (veraltet)</p></td>
<td><p>Dieses Attribut speichert Name: Wert-Paare. Das bereits definierte Name: Wert-Paar ist für die Einstellung <strong>Polling für Anwesenheit zulassen</strong> .</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Gruppierungs-Nr</p></td>
<td><p>Dieses Attribut ist ein eindeutiger Bezeichner einer Gruppe, die zum Gruppieren von Adressbucheinträgen verwendet wird.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Homeserver (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003 (nicht verwendet).</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-HomeServerString (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Heimuser (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003 (nicht verwendet).</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Dieses Attribut steuert, ob ein einzelner Benutzer für den Zugriff durch externe Benutzer aktiviert ist. Sie wird von der Enterprise Services-Schicht erzwungen. Sie ist für die Replikation des globalen Katalogs markiert.</p>
<p>Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-IsMaster (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Zeile</p></td>
<td><p>Dieses Attribut mit einem Wert enthält die Geräte-ID (entweder den SIP-URI oder den Tel-URI des Telefons, den der Benutzer steuert), der von lync für die Telefonie verwendet wird. Dieses Attribut ist für die Replikation des globalen Katalogs markiert und indiziert. Wenn ein Benutzer für Enterprise-VoIP aktiviert ist, speichert dieses Attribut die normalisierte E. 164-Version der Telefonnummer des Benutzers.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LineServer</p></td>
<td><p>Dieses Attribut mit einem Wert enthält den SIP-URI des CSTA-SIP-Gatewayservers. Dieses Attribut ist für die Replikation des globalen Katalogs markiert, aber nicht indiziert.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocalNormalizationData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocalNormalizationLinks (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der lokalen normalisierungs Namen (Distinguished Names, DN), die diesem Standortprofil zugeordnet sind. Der Typ dieses Attributs ist eine DN-Binärdatei. Es gibt eine 1: n-Beziehung zwischen Standortprofil und lokalen Normalisierungsregeln. Die Reihenfolge der Liste der DNS für die lokale Normalisierung muss in der vom Administrator angegebenen Reihenfolge verwaltet werden. Die Beibehaltung der Reihenfolge wird durch den binären Teil der DN-Binärdatei verwaltet, der den Reihenfolgeindex angibt.</p>
<p>Link weiterleiten: <strong>Link-ID 11034</strong></p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Dieses Attribut enthält eine Liste der Optionen für die Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocationName (veraltet)</p></td>
<td><p>Dieses Attribut mit einem Wert enthält einen Anzeigenamen für das Standortprofil, das angibt, an welcher Position dieses Profil steht. Da es mehrere Standortprofile geben kann, benötigt der Administrator eine Möglichkeit, zwischen verschiedenen Profilen zu unterscheiden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-locationProfileBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit definierten Namen für Standortprofile. Dieses Attribut gibt den zurück-Link zu einem oder mehreren Standortprofilen an.</p>
<p>Link zurück: <strong>Link-ID 11035</strong></p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-LocationProfileData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-LocationProfileOptions</p></td>
<td><p>Dieses Attribut enthält die Optionen für das Standortprofil.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MappingContact</p></td>
<td><p>Dieses Attribut mit mehreren Werten enthält eine Liste von Anwendungs Kontakten.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MappingLocation</p></td>
<td><p>Dieses Attribut mit mehreren Werten enthält eine Liste von Standortprofilen.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</p></td>
<td><p>Dieses Attribut stellt die maximale Anzahl ausstehender Suchanforderungen pro Server dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</p></td>
<td><p>Das Attribut stellt die maximale Anzahl von Abonnements pro Benutzer dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das maximale Timeout Fenster für Abonnements dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MaxRegistrationsTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das Timeout Fenster für maximale Registrierungen dar.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut steht für das maximale Timeout Fenster für Roaming-Daten Abonnements.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Bei diesem Attribut handelt es sich um ein Dienst Kontrollpunkt-Attribut unter der Computerklasse, das einen Link zurück zur Factory-Einheit (Multipoint Control Unit, MCU) angibt, zu der er gehört. Dieser Dienst Kontrollpunkt und das Attribut werden für jede Microsoft-MCU erstellt. Jede Microsoft-MCU muss den Back-End-Server des Pools finden, zu dem Sie gehört, um Einstellungen auf Poolebene abzurufen.</p>
<p>Der Wert dieses Attributs ist der Distinguished Name (DN) der MCU-Factory. Hierbei handelt es sich um ein Single-Value-Attribut, das für die Replikation des globalen Katalogs markiert ist.</p>
<p>Link weiterleiten: <strong>Link-ID 11026</strong></p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUFactoryData</p></td>
<td><p>Hierbei handelt es sich um ein reserviertes Attribut mit mehreren Zeichenfolgen. In diesem Attribut gespeicherte Einstellungen werden als Name = Wert-Paare dargestellt. Derzeit definierte Name = Wert-Paare:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCUFactoryPath</p></td>
<td><p>Hierbei handelt es sich um ein Single-Value-Attribut, das den Distinguished Name (DN) einer einzelnen MCU-Factory enthält, die einem Pool zugeordnet ist.</p>
<p>Link weiterleiten: <strong>Link-ID 11024</strong></p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Dieses Attribut ist eine Single-Wert-Zeichenfolge, die die GUID des MCU-Factory-Anbieters angibt. Basierend auf dem GUID-Wert bestimmt der MCU Factory-Prozess, ob dieser MCU-Typ gewartet werden soll. Wenn es sich bei dem GUID-Wert um <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>handelt, wird der MCU-factoryprozess (standardmäßig in lync Server verfügbar) verarbeitet. Für einen beliebigen anderen GUID-Wert wird der MCU-factoryprozess nicht von dem MCU-Typ gewartet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCUServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names (DN). Dieses Attribut enthält eine Liste aller MCU-Server desselben Typs und Lieferanten, die dieser MCU-Factory zugeordnet sind. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p>
<p>Link zurück: Link-ID 11027</p>
<p>Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MCUType</p></td>
<td><p>Dieses Attribut ist eine einwertige Zeichenfolge, die das Medium angibt, das die MCU verarbeiten kann.</p>
<p>Unterstützte gültige Typen:</p>
<ul>
<li><p>Besprechung</p></li>
<li><p>Audio-Video</p></li>
<li><p>Chat</p></li>
<li><p>Telefon-conf</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MCUVendor</p></td>
<td><p>Dieses Attribut ist eine Single-Wert-Zeichenfolge, die den Namen eines MCU-Anbieters angibt. Dieses Attribut wird von allen Microsoft-MCU als <strong>Microsoft Corporation</strong>angegeben.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MeetingFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert verschiedene Besprechungsoptionen, die für alle Benutzer oder Kontaktobjekte global aktiviert sind. Dieses Attribut ist ein Bitmaskenwert vom Typ "ganze Zahl".</p>
<p>Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants lautet ist keine (Benutzer dürfen keine anonymen Benutzer zu Besprechungen einladen) (kein Bits-Satz)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants lautet ist jeder (allen Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen) (Bit-Position 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants lautet ist UsePerUserSetting (Benutzern gestatten, anonyme Benutzer zu Besprechungen basierend auf der Einstellung pro Benutzer einzuladen) (Bit-Position 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (die Besprechungsrichtlinie wird pro Benutzerdefiniert) (Bit-Position 4)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MeetingPolicy (veraltet)</p></td>
<td><p>Dieses Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator für diesen Benutzer als Single-Wert-Attribut zugewiesen hat.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut steht für das minimale Timeout Fenster für Anwesenheitsabonnements.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MinRegistrationTimeout (veraltet)</p></td>
<td><p>Dieses Attribut steht für das minimale Registrierungstimeout Fenster.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt das minimale Timeout Fenster für Roaming-Daten Abonnements dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-MobilityFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags, mit denen Mobilitätseinstellungen definiert werden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-MobilityPolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein mobilitätsrichtlinien Objekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-NumDevicesPerUser (veraltet)</p></td>
<td><p>Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen ein Benutzer für die SIP-Kommunikation registrieren und den Anwesenheitsstatus abonnieren kann.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-OptionFlags</p></td>
<td><p>Dieses Attribut gibt die Optionen an, die für den Benutzer oder das Kontaktobjekt aktiviert sind. Dieses Attribut ist ein Bitmaskenwert vom Typ Integer. Jede Option wird durch ein Bit dargestellt. Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</p>
<p>Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: für öffentliche Instant Messaging (im)-Konnektivität (Bit-Position 0) aktiviert</p></li>
<li><p>2: reserviert (Bit-Position 1)</p></li>
<li><p>4: reserviert (Bit-Position 2)</p></li>
<li><p>8: reserviert (Bit-Position 3)</p></li>
<li><p>16: Remote-Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen (Bit-Position 6)</p></li>
<li><p>128: UCEnabled (Aktivieren von Benutzern für UC) (Bit-Position 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Aktivieren des Benutzers für öffentliche Chat Verbindungen) (Bit-Position 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bit-Position 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Dieses Attribut wird in Ressourcen-und zentralen Gesamtstruktur Topologien verwendet, um die einmalige Anmeldung zu aktivieren, wenn die Objekt-Nr des Benutzers aus dem Windows NT Server-Prinzipal Konto in dieses Attribut des entsprechenden Benutzers oder Kontaktobjekts in der Ressource oder der zentralen Gesamtstruktur kopiert wird. Communicator Web Access sucht nach einem Benutzer in AD DS mithilfe dieses Attributs oder der Objekt-Nr des Benutzers. Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-OwnerUrn</p></td>
<td><p>Dieses Attribut ist der Uniform Resource Name (URN) des Besitzers für einen Anwendungs Kontakt.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Muster (veraltet)</p></td>
<td><p>Dieses Attribut mit einer Wert Zeichenfolge enthält ein Muster, das für die Übereinstimmung von Wähl Nummern im E. 164-Format verwendet wird. Wenn die Wählnummer mit diesem Muster übereinstimmt, wird die Übersetzung auf die gewählte Nummer angewendet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PhoneRouteBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names (DN) für die Telefonroute. Dieses Attribut gibt den zurück-Link zu einer oder mehreren Telefonrouten an.</p>
<p>Link zurück: <strong>Link-ID 11033</strong></p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PhoneRouteData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PhoneRouteName (veraltet)</p></td>
<td><p>Dieses Single-Value-UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass vom Administrator einfach darauf verwiesen werden kann.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PhoneUsageData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PolicyContent (veraltet)</p></td>
<td><p>Dieses Attribut ist eine Unicode-Zeichenfolge mit einem Wert. Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format. Die XML-Schema Definition ist in verschiedenen Richtlinientypen üblich, nur die Einstellungen unterscheiden sich für jeden Richtlinientyp.</p>
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
<td><p>Attribut msRTCSIP-Spalte PolicyData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-policyType (veraltet)</p></td>
<td><p>Dieses Single-Value-UNICODE-Zeichenfolgenattribut enthält den Richtlinientyp. Gültige Richtlinientypen lauten wie folgt:</p>
<ul>
<li><p>Besprechung</p></li>
<li><p>Telefonie</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PoolAddress</p></td>
<td><p>Dieses Attribut gibt einen Link zurück zu dem Pool, zu dem ein Computer gehört. Dieses Attribut wird unabhängig davon festgesetzt, ob auf dem Computer die Standard Edition oder die Enterprise-Edition von lync Server ausgeführt wird. Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</p>
<p>Der gültige Wert ist der Domänenname des Pools.</p>
<p>Link weiterleiten: <strong>Link-ID 11022</strong></p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PoolAddresses</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste der Distinguished Names (DN) der Pools enthält, denen die MCU-Factory zugeordnet ist.</p>
<p>Link zurück: <strong>Link-ID 11025</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PoolData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PoolDisplayName</p></td>
<td><p>Dieses Attribut gibt einen beliebigen Namen für einen Pool an, der von der Verwaltungskonsole angezeigt wird. Dieser Name kann vom Administrator geändert werden.</p>
<p>Der gültige Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Dieses Attribut ist ein einwertiger Zeichenfolgenwert. Der Wert dieses Attributs steht, sofern vorhanden, für den Domänen-FQDN des Pools, wenn der Administrator einen Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory-Domänenstruktur entspricht, in der der Front-End-Pool erstellt wird (beispielsweise ein SIP der Namespace wurde vom DNS-Namespace (Domain Name System) nicht mehr verwendet.</p>
<p>Wir empfehlen, dass Sie den Domänen-FQDN des Front-End-Pools dem Domänennamen Teil als die Active Directory-Domäne zuordnen, in der sich der Pool befindet. Wenn in diesem Attribut kein Wert vorhanden ist, wird der FQDN des Front-End-Pools standardmäßig auf die Active Directory-Domänennamenstruktur zurückgeführt, die durch das <strong>dNSHostName</strong> -Attribut gekennzeichnet ist.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PoolFunctionality</p></td>
<td><p>Eine mehrwertige Liste der Domänennamen aller lync Server-Enterprise Edition-Server, die einem Pool zugeordnet sind. Dieses Attribut des Typs Integer definiert, ob der Pool Instant Messaging (im) und Anwesenheitsfunktionen und Besprechungen unterstützt.</p>
<p>Die möglichen gültigen Wertetypen lauten wie folgt:</p>
<ul>
<li><p>Undefined: Chat-und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</p></li>
<li><p>1: Chat und Anwesenheitsdienst (lync Server)</p></li>
<li><p>2: Chat und Anwesenheits-und Besprechungs Dienst (lync Server)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-pooltype</p></td>
<td><p>Dieses Attribut gibt an, ob ein Serverpool den Standard Edition-Server oder Enterprise Edition-Server ausführt. Dieses Attribut ist ein Bitmaskenwert vom Typ Integer. Jede Option wird durch ein Bit dargestellt.</p>
<p>Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</p>
<ul>
<li><p>1: Standard Edition-Server, hostet Benutzer (Bit-Position 0)</p></li>
<li><p>2: Enterprise Edition-Server, hostet Benutzer (Bit-Position 1)</p></li>
<li><p>4: Standard Edition-Server, Host-Anwendungen (Bit-Position 2)</p></li>
<li><p>8: Enterprise Edition-Server, Host-Anwendungen (Bit-Position 3)</p></li>
</ul>
<p>Da lync Server keine Pools unterstützt, die nur Anwendungen hosten, gelten die einzigen gültigen Werte wie folgt:</p>
<ul>
<li><p>5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 0 und 2)</p></li>
<li><p>10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 1 und 3)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PoolVersion</p></td>
<td><p>Dieses Attribut definiert die Pool-Version. Hierbei handelt es sich um einen ganzzahligen Typ, der mit jeder Hauptprodukt Version inkrementiert wird.</p>
<p>Die möglichen gültigen Wertetypen lauten wie folgt:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PresenceFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags, mit denen Anwesenheitseinstellungen definiert werden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-PresencePolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein Anwesenheitsrichtlinienobjekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Dieses Attribut ermöglicht einem Benutzer oder Kontakt für SIP-Nachrichten. Sie wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie die Kontaktobjekte, nicht die Benutzerobjekte, SIP-fähig sind.</p>
<p>Der gültige Wert ist der DN des Standard Edition-Servers oder des Enterprise Edition-Front-End-Pools, in dem ein Benutzer beheimatet ist.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Dieses Attribut enthält die SIP-Adresse eines angegebenen Benutzers.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Privatsphäre</p></td>
<td><p>Dieses Attribut enthält die Geräte-ID des privaten Leitungs Geräts.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-routingfähig</p></td>
<td><p>Dieses Attribut ist ein boolesches Attribut, das verwendet wird, um zu ermitteln, ob lync Server zum Weiterleiten an diesen Dienst mit seiner GRUU-Adresse autorisiert ist. Wenn dieser Wert auf " <strong>true</strong>" festgelegt ist, ist lync Server zum Weiterleiten an diesen Dienst autorisiert. Wenn dieser Wert auf " <strong>false</strong>" festgelegt ist, ist lync Server nicht zum Weiterleiten an diesen Dienst autorisiert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-RouteUsageAttribute (veraltet)</p></td>
<td><p>Dieses Single-Value-UNICODE-Zeichenfolgenattribut definiert ein Attribut, das die Verwendung für eine Telefonroute qualifiziert. Die Auswahl einer Telefonroute wird auf der Grundlage von zwei Elementen bestimmt: dem Nutzungs Attribut, das der Telefonroute zugewiesen ist, und den zulässigen Richtlinien Verwendungsattributen des Anrufers. Die erste Telefonroute mit einem Nutzungs Attribut, das der zulässigen Verwendung des Anrufers entspricht, ist ausgewählt.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-RouteUsageLinks (veraltet)</p></td>
<td><p>Dieses Attribut für mehrwertigen Distinguished Name (DN) enthält eine Liste der definierten Namen für die Routenverwendung.</p>
<p>Link weiterleiten: <strong>Link-ID 11032</strong></p>
<p>Dieses Attribut ist ein Forward-Link zum entsprechenden Backlink <strong>Attribut msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-RoutingPoolDN</p></td>
<td><p>Dieses Attribut enthält den DN, der auf den Pool verweist, der den gesamten SIP-Datenverkehr an diesen MCU oder vertrauenswürdigen Dienst durchlaufen muss.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-RuleName (veraltet)</p></td>
<td><p>Dieses einmalige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass von einem Administrator einfach darauf verwiesen werden kann.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Schemaversion</p></td>
<td><p>Dieses Attribut steht für die Schemaversion, die derzeit in der Organisation bereitgestellt wird.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-SearchMaxRequests (veraltet)</p></td>
<td><p>Dieses Attribut schränkt die Anzahl der Suchergebnisse ein, die von einer Verzeichnissuche zurückgegeben werden sollen, wenn ein Benutzer mit Communicator nach einem Kontakt sucht. Mit diesem Attribut wird der vom Client bereitgestellte Wert überschrieben.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-SearchMaxResults (veraltet)</p></td>
<td><p>Dieses Attribut schränkt die Anzahl der zurückgegebenen Suchanforderungen ein.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ServerBL</p></td>
<td><p>Bei diesem mehrwertigen Attribut handelt es sich um einen Link zurück, der eine Liste von Distinguished Names (DN) enthält. Dieser DNS-Punkt verweist auf ein Pool-oder <strong>TrustedService</strong> -Objekt.</p>
<p>Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Server</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-ServerReferenceBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names. Bei diesen definierten Namen handelt es sich um zurück-Links, die auf andere Serverobjekte verweisen, denen ein Standardstandortprofil zugewiesen werden kann.</p>
<p>Link zurück: <strong>Link-ID 11037</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Dieses zurück Link-Attribut verweist nur auf Pools und Vermittlungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Server Version vom</p></td>
<td><p>Dieses Attribut definiert die Versionsinformationen des Servers. Diese Versionsnummer gilt für alle Serverrollen. Hierbei handelt es sich um eine monoton-Ganzzahl, die mit jeder offiziellen Produktversion inkrementiert wird.</p>
<p>Die möglichen gültigen Werte lauten wie folgt:</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: lync Server 2010</p></li>
<li><p>6: lync Server 2013</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Quellobjekttyp</p></td>
<td><p>Dieses Attribut mit einem Wert vom Typ "Ganzzahl" gibt den Typ des Objekts an, auf das <strong>msDS-SourceObjectDN</strong> zeigt, wie im folgenden Beispiel:</p>
<ul>
<li><p>NULL | 0x00000001: stellt ein Windows NT Server Principal-Benutzerobjekt aus einer anderen Gesamtstruktur dar.</p></li>
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
<td><p>Attribut msRTCSIP-SubscriptionAuthRequired (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TargetHomeServer</p></td>
<td><p>Mit diesem Attribut können Sie einen Benutzer oder ein Kontaktobjekt aus einem lync Server-Pool in einen anderen verschieben. Dieses Attribut wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie die Kontaktobjekte, nicht die Benutzerobjekte, SIP-fähig sind.</p>
<p>Der gültige Wert ist der DN des Ziel-Standard Edition-Servers oder-Front-End-Pools, in den ein Benutzer verschoben werden soll.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TargetPhoneNumber (veraltet)</p></td>
<td><p>Dieses Attribut mit einer Wert Zeichenfolge enthält ein Telefonnummernmuster oder einen Bereich, der an die in <strong>Attribut msRTCSIP-Gateways</strong>definierten Gateways weitergeleitet werden soll.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TargetUserPolicies</p></td>
<td><p>Dieses Attribut speichert Name-Wert-Paare für Zielrichtlinien für lync Server-Benutzer.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-Mandanten-Nr</p></td>
<td><p>Dieses Attribut speichert den eindeutigen Bezeichner für einen Mandanten.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-Translation (veraltet)</p></td>
<td><p>Dieses Attribut wird von der Sprachfunktion von lync Server verwendet und enthält die Übersetzungs Zeichenfolge, die für die gewählte Nummer gelten soll, wenn eine Übereinstimmung gefunden wird.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedMCUData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des MCU enthält. Hierbei handelt es sich um ein Single-Value-Attribut. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedProxyData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des Servers enthält, auf dem Proxy Server ausgeführt wird. Dieses Attribut ist ein Single-Wert. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServerData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Dieses Attribut ist ein Single-Value-Attribut, das den FQDN eines vertrauenswürdigen Servers darstellt.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServerVersion</p></td>
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
<td><p>Attribut msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Dieses Attribut definiert die Optionen, die für den vertrauenswürdigen Dienst aktiviert sind.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, beispielsweise einen Media Relay-Authentifizierungsdienst. Ein Media Relay-Authentifizierungsdienst (physisch auf dem Edgeserver mit dem A/V-Konferenzdienst) muss einem Pool zugeordnet sein, um audioszenarien für Remotebenutzer zu unterstützen.</p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedServicePort</p></td>
<td><p>Dieses Attribut ist eine ganze Zahl, die die Portnummer definiert, die zum Herstellen der Verbindung mit diesem GRUU-Dienst verwendet wird.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedServiceType</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den Typ des GRUU-Diensts definiert, den er darstellt.</p>
<p>Die gültigen GRUU-Diensttypen lauten wie folgt:</p>
<ul>
<li><p>„MediationServer“</p></li>
<li><p>Gateway</p></li>
<li><p>Media Relay-Authentifizierungsdienst (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>Attribut msRTCSIP-UserExtension</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des IIS mit lync Server-Webdiensten enthält. Hierbei handelt es sich um ein Single-Value-Attribut. Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UCFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert verschiedene UC-Optionen, die für alle Benutzer-oder Kontaktobjekte global aktiviert sind. Dieses Attribut ist ein Bitmaskenwert vom Typ "ganze Zahl". Jede Option wird durch das vorhanden sein eines Bits dargestellt.</p>
<p>Der mögliche gültige Wert (und die zugehörige Bit-Position) lautet wie folgt:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (Bit-Position 2)</p></li>
</ul>
<p>Wenn dieses Bit festgelegt ist, wird die UC-Richtlinie pro Benutzerdefiniert.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-UCPolicy (veraltet)</p></td>
<td><p>Dieses Attribut mit einem Wert enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator für diesen Benutzer zugewiesen hat.</p></td>
<td><p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UserDomainList (veraltet)</p></td>
<td><p>Dieses Attribut enthält eine Liste aller Domänen in einer Gesamtstruktur, die SIP-fähige Benutzer hosten. Der Standardwert ist eine leere Liste, die angibt, dass alle Domänen in der Gesamtstruktur SIP-fähig sind.</p>
<p>Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen einzelner Domänen darstellen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-UserEnabled</p></td>
<td><p>Dieses Attribut bestimmt, ob der Benutzer derzeit für lync Server aktiviert ist.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UserExtension</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste von Name-Wert-Paaren im Format &quot;von Name = Wert. &quot; Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-UserLocationProfile</p></td>
<td><p>Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt verweist.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UserPolicies</p></td>
<td><p>Dieses Attribut speichert Name-Wert-Paare für Benutzerrichtlinien.</p></td>
<td><p>Neu in lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-UserPolicy</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste von Distinguished Names mit Binär (DN_WITH_BINARY) enthält, die auf globale Benutzerrichtlinien unterschiedlicher Typen verweisen. Der binäre Teil gibt den Typ der Richtlinie an, auf die der DN-Anteil verweist.</p>
<p>Die gültigen binären Werte lauten wie folgt:</p>
<ul>
<li><p>0x00000001: Besprechungsrichtlinie</p></li>
<li><p>0x00000002: UC-Richtlinie</p></li>
<li><p>0x00000005: Anwesenheitsrichtlinie</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Hierbei handelt es sich um die SIP-Routinggruppen-ID. Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.</p></td>
<td><p>Neu in lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-WebComponentsData</p></td>
<td><p>Hierbei handelt es sich um ein mehrwertiges Attribut. Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Dieses Attribut mit einem Wert verweist auf den Pool oder den Standard Edition-Server, zu dem die Webkomponenten gehören.</p>
<p>Link weiterleiten: <strong>Link-ID 11028</strong></p>
<p>Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>Attribut msRTCSIP-WebComponentsServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste mit definierten Namen. Dieses Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</p>
<p>Link zurück: <strong>Link-ID 11029</strong></p>
<p>Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>Attribut msRTCSIP-WMIInstanceId (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003.</p>
<p>Veraltet in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Dieses vorhandene Active Directory-Attribut wird von der Telefonie verwendet, um die Liste der alternativen TCP/IP-Adressen für ein Telefon festzulegen.</p></td>
<td><p>Neu im Windows Server 2008-Betriebssystem.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Dieses vorhandene Active Directory-Attribut wird von den VoIP-Komponenten in lync Server für nur-Kontaktobjekte verwendet, um Anrufe an die automatische Telefonzentrale und die Teilnehmerzugriffsnummern von Unified Messaging weiterzuleiten. Die bedingungslose Anruf Weiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert. Dieses Konto wird für den spezifischen Zweck der automatischen Telefonzentrale und des Abonnenten Zugriffs erstellt. Die Attribute dieses Kontos sollten nicht von Administratoren geändert werden.</p></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Dieses vorhandene Active Directory-mehrwertige Attribut ist Teil des Active Directory-Basisschemas, das in Windows 2000 eingeführt wurde. Dieses Attribut enthält die verschiedenen X400-, x500-und SMTP-Adressen der e-Mail-Adresse des Benutzers. In Live Communications Server 2003 und höher wird der SIP-URI des Benutzers mithilfe des &quot;SIP:&quot; -Tags zu dieser Liste hinzugefügt.</p>
<p>Die folgenden Anwendungen durchsuchen den SIP-URI des Benutzers anhand dieses Attributs:</p>
<ul>
<li><p>Microsoft Office Outlook 2003-Messaging-und Zusammenarbeitsclient</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Dieses vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</p></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

