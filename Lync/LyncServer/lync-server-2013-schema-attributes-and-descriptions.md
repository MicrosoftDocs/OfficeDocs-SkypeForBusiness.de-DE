---
title: Schemaattribute und Beschreibungen in Lync Server 2013
TOCTitle: Schemaattribute und Beschreibungen in Lync Server 2013
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412841(v=OCS.15)
ms:contentKeyID: 49295100
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schemaattribute und Beschreibungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden alle Schemaattribute beschrieben, die von Lync Server 2013 verwendet werden. Informationen zu den Klassen, denen diese Attribute zugeordnet sind, finden Sie unter [Schemaattribute nach Klasse in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Eine Liste der Klassen und Attribute, die neu in Lync Server 2013 sind, finden Sie unter [Schemaänderungen in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Attribute, bei denen es sich um verknüpfte Paare handelt, werden als Forward- bzw. Backwardlinks angegeben. Ein Attribut, das auf ein anderes Objekt verweist, wird als Forwardlink bezeichnet. Das Attribut dieses anderen Objekts, das zurück auf das erste Objekt verweist, ist ein Backwardlink. Forwardlinks können aktualisiert werden, Backwardlinks dagegen sind schreibgeschützt.

Einige Attribute weisen eine Bitmaskenwert auf. Bei diesen Attributen wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert steht für die Bitposition. Die erste Bitposition ist Bit 0. Beispiel: Für 1 (binär) ist Bit 0 festgelegt, und für 10000 (binär) ist Bit 4 festgelegt. Jedes Bit stellt eine Eigenschaft dar. Im Folgenden finden Sie einige Beispiele:

  - 10000 (binär) hat den Dezimalwert 16 (Bit 4 ist festgelegt)

  - 100000000 (binär) hat den Dezimalwert 256 (Bit 8 ist festgelegt)

  - 1100 (binär) hat den Dezimalwert 12 (die Bits 2 und 3 sind festgelegt; durch die beiden Bits dargestellte Eigenschaften sind aktiviert)

  - 1111000001 (binär) hat den Dezimalwert 961 (die Bits 0, 6, 7, 8 und 9 sind festgelegt; Eigenschaften für diese Bits sind aktiviert)

### Schemaattribute für Lync Server 2013

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
<td><p>dnsHostName</p></td>
<td><p>Ein in Active Directory-Domänendienste vorhandenes Attribut, das nun den Klassen <strong>msRTCSIP-Pool</strong> und <strong>msRTCSIP-MonitoringServer</strong> zugeordnet ist. Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Monitoring-Servers an.</p>
<p>Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, das diesem Objekt entspricht. Das Attribut wird für die Verteilergruppenerweiterung und die automatische Anwesenheit verwendet. Es ist im Active Directory-Standardschema für Windows Server 2003 R2 definiert.</p>
<p>Damit die AD DS nicht auf Windows Server 2003 R2 aktualisiert werden müssen, erweitert die Active Directory-Schemavorbereitung das Windows Server 2003-Schema um diese Attributdefinition.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Dieses mehrwertige Attribut enthält Voicemaileinstellungen. Es wird gemeinsam mit Exchange Unified Messaging (UM) verwendet.</p></td>
<td><p>Neu in Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Dieses Attribut mit mehreren Werten enthält IDs für Halterichtlinien, die für den Benutzer gelten. Halterichtlinien halten Posteingangselemente für den Benutzer für die Dauer des Haltens aufrecht. Dieses Attribut wird gemeinsam mit Exchange 2013 verwendet.</p></td>
<td><p>Neues in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Dieses Attribut speichert Audiokonferenzanbieterinformationen für einen Benutzer.</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Dieses Attribut zeigt auf den vertrauenswürdigen Diensteintrag für den Anwendungskontakt.</p></td>
<td><p>Neu in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Dieses Attribut enthält eine Liste von gehosteten Anwendungen auf dem Anwendungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Dieses Attribut gibt die Optionen für den Anwendungskontakt an.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Dieses Attribut enthält die primäre Sprache für den Anwendungskontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Dieses mehrwertige Attribut enthält die sekundären Sprachen für den Anwendungskontakt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Das Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören. Der entsprechende Forwardlink zu diesem Backwardlinkattribut lautet <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Dieses Attribut zeigt auf den Pool, zu dem dieser Anwendungsserver gehört. Dies ist der Forwardlink. Der entsprechende Backwardlink lautet <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
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
<td><p>Dieses Attribut gibt die globale Standardeinstellung innerhalb der Grenzen der Gesamtstruktur an, die für die Archivierung der Kommunikation aller Benutzer gilt. Wird auf Ebene des Archivierungs-Agents erzwungen. Der Bereich mit gültigen Werten für dieses Attribut lautet:</p>
<ul>
<li><p><strong>TRUE</strong>: Alle Benutzer archivieren</p></li>
<li><p><strong>FALSE</strong>: Nicht alle Benutzer archivieren</p></li>
</ul>
<p>Das Attribut steuert innerhalb der Grenzen der Gesamtstruktur global, auf welche Weise die Kommunikation von Benutzern in einem internen Netzwerk archiviert wird.</p>
<p><strong>Verhalten von Live Communications Server 2005 (veraltet)</strong></p>
<p>Der Bereich mit gültigen Werten für dieses Attribut lautet:</p>
<ul>
<li><p>0: Nachrichtentext archivieren [Bit 0]</p></li>
<li><p>1: Nachrichtentext nicht archivieren [Bit 0]</p></li>
</ul>
<p><strong>Verhalten von Office Communications Server 2007</strong></p>
<p>Der Bereich mit gültigen Werten für dieses Attribut lautet:</p>
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
<p>In Lync Server 2010 veraltet.</p></td>
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
<td><p>Das Attribut enthält einen ganzzahligen als Bitfeld verwendeten Wert, mit dem die Archivierung der Kommunikation eines einzelnen Benutzers gesteuert wird. Diese Steuerung wird auf Ebene des Archivierungs-Agents erzwungen. Gekennzeichnet für die Replikation mit dem globalen Katalog.</p>
<p>Das Attribut ist jeweils nur für einen bestimmten Benutzer oder Kontakt gültig. Die in Lync Server gültigen Werte (und zugeordneten Bitpositionen) lauten wie folgt:</p>
<ul>
<li><p>0: Nicht archivieren (kein Bit ist festgelegt)</p></li>
<li><p>1: Veraltet (Bitposition 0)</p></li>
<li><p>2: Veraltet (Bitposition 1)</p></li>
<li><p>4: Interne Kommunikation archivieren (Bitposition 2)</p></li>
<li><p>8: Partnerverbundkommunikation archivieren (Bitposition 3)</p></li>
</ul>
<p>Die in Live Communications Server 2005 gültigen früheren Werte lauten wie folgt:</p>
<ul>
<li><p>0: Verwenden Sie den von <strong>msRTCSIP-ArchiveDefault</strong> und <strong>msRTCSIP-ArchiveFederation</strong> definierten Standardwert entsprechend dieser Rangfolge:</p>
<ul>
<li><p>1: Archivieren</p></li>
<li><p>2: Nicht archivieren</p></li>
<li><p>3: Ohne Nachrichtentext archivieren</p></li>
</ul></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (veraltet)</p></td>
<td><p>Dieses Attribut definiert die Version des Archivierungsdiensts. Bei diesem Attribut handelt es sich um einen monoton ansteigenden Ganzzahlwert, der sich mit jeder offiziellen Produktversion erhöht. Folgende Werte sind zulässig:</p>
<ul>
<li><p>Nicht definiert: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Dieses Attribut gibt den FQDN des Back-End-Servers im Pool an. Da pro Pool nur ein einziger Back-End-Server vorhanden sein kann, ist dies ein einwertiges Attribut.</p>
<p>Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Dieses Attribut enthält die ID des Pools, der das Konferenzverzeichnis hostet.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Dieses Attribut enthält die ID eines Konferenzverzeichnisses.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Dieses Attribut enthält die ID des Pools, in die das Konferenzverzeichnis verschoben wird.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Default</p></td>
<td><p>Dieses boolesche Attribut gibt an, ob die Telefonverwendung zur Standardverwendung gehört. Wenn dieses Attribut auf <strong>TRUE</strong> festgelegt ist, ist die Telefonverwendung eine Standardverwendung, die vom Administrator nicht gelöscht werden kann. Wenn dieses Attribut auf <strong>FALSE</strong> festgelegt ist, kann die Verwendung gelöscht werden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich außerhalb der Organisation befinden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich innerhalb der Organisation befinden.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält den Distinguished Name (DN) eines Standortprofil-Klassenobjekts, das dem Attribut zugewiesen ist.</p>
<p>Forwardlink: <strong>Link ID 11036</strong></p>
<p>Der entsprechende Backwardlink lautet <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (veraltet)</p></td>
<td><p>Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt. Wenn der Wert <strong>TRUE</strong> lautet, wird die Richtlinie als Standardrichtlinie behandelt.</p></td>
<td><p>Neu in Office Communications Server 2007</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</p></td>
<td><p>Dieses Attribut spezifiziert den FQDN des Edgeservers, der den Zugriffs-Edgedienst ausführt, wenn auf diesen direkt zugegriffen werden kann, oder des Hardwaregeräts zum Lastenausgleich für einen Serverpool, in dem der Zugriffs-Edgedienst ausgeführt wird. Wenn auf die Server, die den Zugriffs-Edgedienst ausführen, nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und (optional) die Portnummer des Directors bzw. des Hardwaregeräts zum Lastenausgleich für einen Director-Pool an.</p>
<p>Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</p></td>
<td><p>Dieses Attribut stellt die Portnummer da, die zum Herstellen einer Verbindung zum Server verwendet werden sollte, auf dem der Zugriffs-Edgedienst ausgeführt wird.</p>
<p>Zulässig sind ganzzahlige Werte, die den zu verwendenden Port angeben. Der Standardwert lautet 5061.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Standardtimeoutwert für Anwesenheitsabonnements dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (verwaltet)</p></td>
<td><p>Dieses Attribut stellt den Standardtimeoutwert für Registrierungen dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Standardtimeoutwert für Roamingdatenabonnements dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Dieses Attribut wird in einer Topologie mit getrennten Domänen verwendet und enthält einen vollqualifizierten Domänennamen Fully Qualified Domain Name, FQDN).</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut enthält eine benutzerfreundliche Beschreibung der betreffenden Telefonroute oder Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Dieses Attribut stellt eine für die Registrierung konfigurierte Domäne dar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Dieses Attribut gibt den FQDN des Servers an, auf dem der Zugriffs-Edgedienst ausgeführt wird.</p>
<p>Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (veraltet)</p></td>
<td><p>Dieses Attribut steuert, ob ein Server als Antwort auf die SUBSCRIBE-Anforderung eines Clients eine BENOTIFY-Anforderung (Best Effort NOTIFY) anstelle einer NOTIFY-Anforderung generiert. BENOTIFY ist eine leistungsoptimierende Erweiterung des Subscribe-Notification-Handshakes, bei der der Server BENOTIFY-Anforderungen anstelle normaler NOTIFY-Anforderungen generiert. Die verbesserte Leistung ist darauf zurückzuführen, dass für eine BENOTIFY-Anforderung keine 200 OK-Antwort vom Client erforderlich ist, wie dies bei NOTIFY-Anforderungen der Fall ist.</p>
<p>Gültige Werte sind <strong>TRUE</strong> oder <strong>FALSE</strong>.</p>
<div>

> [!NOTE]
> Live Communications Server 2003 unterstützt keine BENOTIFY-Anforderungen. Zur Interoperabilität mit Serveranwendungen, die mit der Live Communications Server 2003-Server-API geschrieben wurden und auf Live Communications Server 2005 oder auf Servern von Drittanbietern ausgeführt werden, können BENOTIFY-Anforderungen deaktiviert werden, indem dieser Wert auf <STRONG>FALSE</STRONG> festgelegt wird. BENOTIFY ist derzeit kein Bestandteil des SIP-Standardisierungsprozesses der IETF (Internet Engineering Task Force).


</div></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (veraltet)</p></td>
<td><p>Dieses Attribut ist ein globaler Schalter, mit dem IT-Administratoren konfigurieren können, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen. Mit diesem Attribut kann ein Administrator das <strong>FederationEnabled</strong>-Attribut für einzelne Benutzer überschreiben. Dies kann insbesondere dann hilfreich sein, wenn das interne Netzwerk vor Angriffen aus dem Internet geschützt werden soll, beispielsweise vor Würmern, Viren oder gezielten Angriffen auf das Unternehmen.</p>
<p>Folgende Werte (und die zugeordneten Bitpositionen) sind gültig:</p>
<ul>
<li><p>1: Für die Verbindung mit öffentlichen Sofortnachrichtendiensten aktiviert (Bitposition 0)</p></li>
<li><p>2: Reserviert (Bitposition 1)</p></li>
<li><p>4: Reserviert (Bitposition 2)</p></li>
<li><p>8: Reserviert (Bitposition 3)</p></li>
<li><p>16: Remoteanrufsteuerung aktiviert [Telefonie] (Bitposition 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (Benutzer können anonyme Benutzer zu Besprechungen einladen) (Bitposition 6)</p></li>
<li><p>128: UCEnabled (Unified Communications für Benutzer aktivieren) (Bitposition 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Verbindung mit öffentlichen Sofortnachrichtendiensten für Benutzer aktivieren) (Bitposition 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bitposition 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Dieses Attribut gibt an, ob die Enterprise Services auf dem betreffenden Server geladen werden.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Dieses Attribut enthält die Einwahlnummer für den externen Zugriff.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Dieses Attribut steuert, ob ein bestimmter Benutzer für den Partnerverbund aktiviert ist. Wird auf Enterprise Services-Ebene erzwungen. Gekennzeichnet für die Replikation mit dem globalen Katalog.</p>
<p>Gültige Werte sind <strong>TRUE</strong> oder <strong>FALSE</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</p>
<p>Backwardlink: <strong>Link ID 11023</strong></p>
<p>Der entsprechende Forwardlink zu diesem Backwardlink lautet <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (veraltet)</p></td>
<td><p>Dieses mehrwertige Zeichenfolgenattribut enthält eine Liste mit Gateways und Ports (pro Gateway).</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (veraltet)</p></td>
<td><p>Dieses Attribut speichert Name/Wert-Paare. Das bereits definierte Name/Wert-Paar wird für die Einstellung der <strong>Anwesenheitsabfrage</strong> verwendet.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Dieses Attribut ist eine eindeutige ID einer Gruppe und wird zum Gruppieren von Adressbucheinträgen verwendet.</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (veraltet)</p></td>
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
<td><p>msRTCSIP-HomeUsers (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003 (nicht verwendet).</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Dieses Attribut steuert, ob der externe Benutzerzugriff für einen bestimmten Benutzer aktiviert ist. Wird auf Enterprise Services-Ebene erzwungen. Gekennzeichnet für die Replikation mit dem globalen Katalog.</p>
<p>Gültige Werte sind <strong>TRUE</strong> oder <strong>FALSE</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (veraltet)</p></td>
<td><p>-</p></td>
<td><p>Neu in Live Communications Server 2003</p>
<p>In Live Communications Server 2005 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Line</p></td>
<td><p>Dieses einwertige Attribut enthält die Geräte-ID (entweder den SIP-URI oder den TEL-URI des dem Benutzer zugeordneten Telefons), die von Lync für die Telefonie verwendet wird. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet und wird indiziert. Es speichert die normalisierte E.164-Version der Rufnummer des Benutzers, sofern für den Benutzer Enterprise-VoIP aktiviert ist.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Dieses einwertige Attribut enthält den SIP-URI des CSTA-SIP-Gatewayservers. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet, wird jedoch nicht indiziert.</p></td>
<td><p>Neu in Microsoft Office Live Communications Server 2005 mit SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der Distinguished Names (DN) der lokalen Normalisierung, die diesem Standortprofil zugeordnet sind. Das Attribut ist vom Typ DN mit Binärwert. Zwischen Standortprofil und lokalen Normalisierungsregeln besteht eine 1:n-Beziehung. Die Sortierung der Liste mit DNs der lokalen Normalisierung muss der vom Administrator festgelegten Sortierreihenfolge entsprechen. Die Sortierreihenfolge wird durch den Binärteil des DN mit Binärwert festgelegt, der den Sortierindex angibt.</p>
<p>Forwardlink: <strong>Link ID 11034</strong></p>
<p>Der entsprechende Backwardlink für dieses Forwardlinkattribut lautet <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Dieses Attribut enthält eine Liste der Optionen für die Normalisierungsregel.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält einen Anzeigenamen für das Standortprofil. Dieser Name liefert Informationen zum Standort, den das Profil darstellt. Da mehrere Standortprofile vorhanden sein können, muss der Administrator eine Möglichkeit haben, zwischen verschiedenen Profilen zu unterscheiden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names für Standortprofile. Das Attribut gibt den Backwardlink zu einem oder mehreren Standortprofilen an.</p>
<p>Backwardlink: <strong>Link ID 11035</strong></p>
<p>Dieses Attribut stellt das Gegenstück zum Forwardlink <strong>msRTCSIP-LocalNormalizationLinks</strong> dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Dieses Attribut enthält die Optionen für das Standortprofil.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der Anwendungskontakte.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der Standortprofile.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</p></td>
<td><p>Dieses Attribut stellt die Maximalzahl ausstehender Suchanforderungen pro Server dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</p></td>
<td><p>Dieses Attribut stellt die Maximalzahl von Abonnements pro Benutzer dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Maximalwert für das Abonnementtimeout dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Maximalwert für das Registrierungstimeout dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Maximalwert für das Timeout für Roamingdatenabonnements dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Dieses Attribut ist ein Dienststeuerungspunkt-Attribut unterhalb der Computerklasse, das einen Backwardlink zu der MCU-Factory (Multipoint Control Unit) angibt, zu der es gehört. Der Dienststeuerungspunkt und das Attribut werden für jede Microsoft-MCU erstellt. Jede Microsoft-MCU muss den Back-End-Server des übergeordneten Pools ermitteln können, um Einstellungen auf Poolebene von diesem Server abzurufen.</p>
<p>Der Wert dieses Attributs ist der Distinguished Name (DN) der MCU-Factory. Es handelt sich um ein einwertiges Attribut, das für die Replikation mit dem globalen Katalog gekennzeichnet ist.</p>
<p>Forwardlink: <strong>Link ID 11026</strong></p>
<p>Der entsprechende Backwardlink zu diesem Forwardlinkattribut lautet <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Dies ist ein reserviertes Attribut mit mehrteiliger Zeichenfolge. Die in diesem Attribut gespeicherten Einstellungen werden als Name/Wert-Paare dargestellt. Folgende Name/Wert-Paare sind derzeit definiert:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Dieses einwertige Attribut enthält den Distinguished Name (DN) einer einzelnen MCU-Factory, die einem Pool zugeordnet ist.</p>
<p>Forwardlink: <strong>Link ID 11024</strong></p>
<p>Der entsprechende Backwardlink zu diesem Forwardlinkattribut lautet <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Dieses Attribut mit einem einzelnen Zeichenfolgenwert gibt die GUID des MCU-Factory-Anbieters an. Ausgehend vom GUID-Wert ermittelt der MCU-Factory-Prozess, ob dieser MCU-Typ für die Verarbeitung akzeptiert wird. Wenn der GUID-Wert <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong> lautet, wird der MCU-Typ vom MCU-Factory-Prozess (in Lync Server standardmäßig vorhanden) verarbeitet. Bei allen anderen GUID-Werten wird der MCU-Typ vom MCU-Factory-Prozess nicht akzeptiert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Dieses mehrwertige Attribut ist eine Liste mit Distinguished Names (DN). Das Attribut enthält eine Liste aller MCU-Server desselben Typs und Herstellers, die dieser MCU-Factory zugeordnet sind. Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p>
<p>Backwardlink: Link ID 11027</p>
<p>Der entsprechende Forwardlink zu diesem Backwardlink lautet <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Dieses Attribut mit einem einzelnen Zeichenfolgenwert gibt das Medium an, das die MCU verarbeiten kann.</p>
<p>Folgende Typen werden unterstützt:</p>
<ul>
<li><p>meeting</p></li>
<li><p>audio-video</p></li>
<li><p>chat</p></li>
<li><p>phone-conf</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Dieses Attribut mit einem einzelnen Zeichenfolgenwert gibt den Namen des MCU-Herstellers an. Bei allen Microsoft-MCUs wird dieses Attribut auf den Wert <strong>Microsoft Corporation</strong> festgelegt.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert verschiedene Besprechungsoptionen, die global für alle Benutzer- oder Kontaktobjekte aktiviert sind. Das Attribut stellt eine Bitmaske vom Typ Integer dar.</p>
<p>Folgende Werte (und die zugeordneten Bitpositionen) sind gültig:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants lautet None (Benutzer können keine anonymen Benutzer zu Besprechungen einladen) (keine Bits festgelegt)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants lautet Everyone (alle Benutzer können anonyme Benutzer zu Besprechungen einladen) (Bitposition 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants lautet UsePerUserSetting (Benutzer können anonyme Benutzer je nach Benutzereinstellung zu Besprechungen einladen) (Bitposition 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (Besprechungsrichtlinie wird pro Benutzer definiert) (Bitposition 4)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (veraltet)</p></td>
<td><p>Dieses einwertige Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator diesem Benutzer zugewiesen hat.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Mindesttimeoutwert für Anwesenheitsabonnements dar.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Mindesttimeoutwert für Registrierungen dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</p></td>
<td><p>Dieses Attribut stellt den Mindesttimeoutwert für Roamingdatenabonnements dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Dieses Attribut wird zum Speichern des gespiegelten SQL Server-Back-Ends verwendet, das von Front-End-Pool verwendet wird.</p></td>
<td><p>Neues in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags zur Definition der Mobilitätseinstellungen.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein Mobilitätsrichtlinienobjekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (veraltet)</p></td>
<td><p>Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen sich ein Benutzer für die SIP-Kommunikation registrieren und seine Anwesenheit anmelden darf.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Dieses Attribut gibt die Optionen an, die für das Benutzer- oder Kontaktobjekt aktiviert sind. Das Attribut stellt eine Bitmaske vom Typ Integer dar. Jede Option wird durch ein Bit angegeben. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet.</p>
<p>Folgende Werte (und die zugeordneten Bitpositionen) sind gültig:</p>
<ul>
<li><p>1: Für die Verbindung mit öffentlichen Sofortnachrichtendiensten aktiviert (Bitposition 0)</p></li>
<li><p>2: Reserviert (Bitposition 1)</p></li>
<li><p>4: Reserviert (Bitposition 2)</p></li>
<li><p>8: Reserviert (Bitposition 3)</p></li>
<li><p>16: Remoteanrufsteuerung aktiviert [Telefonie] (Bitposition 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (Benutzer können anonyme Benutzer zu Besprechungen einladen) (Bitposition 6)</p></li>
<li><p>128: UCEnabled (Benutzer für Unified Communications aktivieren) (Bitposition 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (Verbindung mit öffentlichen Sofortnachrichtendiensten für Benutzer aktivieren) (Bitposition 8)</p></li>
<li><p>512: RemoteCallControlDualMode (Bitposition 9)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Dieses Attribut wird in Ressourcen- und zentralen Gesamtstrukturtopologien verwendet, um die einmalige Anmeldung zu aktivieren, wenn die Objekt-SID eines Benutzers aus dem Windows NT Server-Prinzipalkonto in dieses Attribut im entsprechenden Benutzer- oder Kontaktobjekt in der Ressourcen- oder zentralen Gesamtstruktur kopiert wird. Communicator Web Access verwendet für die Suche nach einem Benutzer in AD DS dieses Attribut oder die Objekt-SID des Benutzers. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Dieses Attribut ist der Uniform Resource Name (URN) des Besitzers für einen Anwendungskontakt.</p></td>
<td><p>Neu in Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (veraltet)</p></td>
<td><p>Dieses Attribut mit einem einzelnen Zeichenfolgenwert enthält ein Muster, das für den Abgleich von Rufnummern mit dem E.164-Format verwendet wird. Wenn die Rufnummer diesem Muster entspricht, wird die Übersetzung auf die gewählte Nummer angewendet.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN) für Telefonrouten. Das Attribut gibt den Backwardlink zu einer oder mehreren Telefonrouten an.</p>
<p>Backwardlink: <strong>Link ID 11033</strong></p>
<p>Dieses Attribut stellt das Gegenstück zum Forwardlink <strong>msRTCSIP-RouteUsageLinks</strong> dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass der Administrator leichter auf die Route verweisen kann.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (veraltet)</p></td>
<td><p>Dieses Attribut ist eine einwertige Unicode-Zeichenfolge. Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format. Die XML-Schemadefinition wird von den verschiedenen Richtlinientypen gemeinsam verwendet, lediglich die Einstellungen für jeden Richtlinientyp unterscheiden sich.</p>
<p>Die XML-Schemadefinition (XSD) ist folgendermaßen definiert:</p>
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
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (veraltet)</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (veraltet)</p></td>
<td><p>Dieses einwertige Unicode-Zeichenfolgenattribut enthält den Richtlinientyp. Folgende Richtlinientypen sind zulässig:</p>
<ul>
<li><p>meeting</p></li>
<li><p>telephony</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Dieses Attribut gibt einen Backwardlink zu dem Pool an, zu dem ein Computer gehört. Das Attribut ist immer festgelegt, unabhängig davon, ob auf dem Computer die Standard Edition oder die Enterprise Edition von Lync Server ausgeführt wird. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet.</p>
<p>Gültiger Wert ist der Domänenname des Pools.</p>
<p>Forwardlink: <strong>Link ID 11022</strong></p>
<p>Der entsprechende Backwardlink zu diesem Forwardlinkattribut lautet <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste der Distinguished Names (DN) von Pools, die der MCU-Factory zugeordnet sind.</p>
<p>Backwardlink: <strong>Link ID 11025</strong></p>
<p>Der entsprechende Forwardlink zu diesem Backwardlink lautet <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Dieses Attribut gibt einen frei wählbaren Namen für einen Pool an, der in der Verwaltungskonsole angezeigt wird. Dieser Name kann vom Administrator geändert werden.</p>
<p>Gültiger Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Dieses Attribut ist ein einzelner Zeichenfolgenwert. Der Wert dieses Attributs stellt, sofern vorhanden, den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools dar, wenn der Administrator einen Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory-Domänenstruktur entspricht, in welcher der Front-End-Pool erstellt wird (z. B. ein vom DNS-Namespace getrennter SIP-Namespace).</p>
<p>Es wird empfohlen, den FQDN der Front-End-Pool-Domäne entsprechend dem Domänenteil des Namens der Active Directory-Domäne festzulegen, in der sich der Pool befindet. So wird – wenn in diesem Attribut kein Wert angegeben ist – der kein Wert des Front-End-Pools standardmäßig auf die Active Directory-Domänennamenstruktur festgelegt, die im Attribut <strong>dnsHostName</strong> angegeben ist.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Eine mehrwertige Liste der Domänennamen aller Lync Server Enterprise Edition-Server, die einem Pool zugeordnet sind. Dieses Attribut vom Typ Integer definiert, ob der Pool Sofortnachrichten, Anwesenheitsfeatures und Besprechungen unterstützt.</p>
<p>Folgende Werttypen sind zulässig:</p>
<ul>
<li><p>Nicht definiert: Instant Messaging- und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</p></li>
<li><p>1: Instant Messaging- und Anwesenheitsdienst (Lync Server)</p></li>
<li><p>2: Instant Messaging-, Anwesenheits- und Besprechungsdienst (Lync Server)</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Dieses Attribut gibt an, ob in einem Pool Standard Edition-Server oder Enterprise Edition-Server ausgeführt werden. Das Attribut stellt eine Bitmaske vom Typ Integer dar. Jede Option wird durch ein Bit angegeben.</p>
<p>Folgende Werte (und die zugeordneten Bitpositionen) sind gültig:</p>
<ul>
<li><p>1: Standard Edition-Server, hostet Benutzer (Bitposition 0)</p></li>
<li><p>2: Enterprise Edition-Server, hostet Benutzer (Bitposition 1)</p></li>
<li><p>4: Standard Edition-Server, hostet Anwendungen (Bitposition 2)</p></li>
<li><p>8: Enterprise Edition-Server, hostet Anwendungen (Bitposition 3)</p></li>
</ul>
<p>Da Lync Server keine Pools unterstützt, die nur als Host für Anwendungen fungieren, sind nur die folgenden Werte gültig:</p>
<ul>
<li><p>5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bitpositionen 0 und 2)</p></li>
<li><p>10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bitpositionen 1 und 3)</p></li>
</ul></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Dieses Attribut definiert die Poolversion. Es ist vom Typ Integer und wird mit jeder veröffentlichten Hauptversion des Produkts erhöht.</p>
<p>Folgende Werttypen sind zulässig:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Dieses Attribut enthält Optionen und Flags, die die Anwesenheitseinstellungen definieren.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Dieses Attribut enthält den DN für ein Anwesenheitsrichtlinienobjekt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Dieses Attribut aktiviert einen Benutzer bzw. Kontakt für das SIP-Messaging. Es wurde der Kontaktklasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie Kontaktobjekte und nicht Benutzerobjekte SIP-aktiviert sind.</p>
<p>Gültiger Wert ist der DN des Standard Edition-Servers oder des Enterprise Edition-Front-End-Pools des Benutzers.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Dieses Attribut enthält die SIP-Adresse eines bestimmten Benutzers.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Dieses Attribut enthält die Geräte-ID eines Privatleitungsgeräts.</p></td>
<td><p>Neu in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Routable</p></td>
<td><p>Dieses boolesche Attribut gibt an, ob Lync Server autorisiert ist, zum betreffenden Dienst eine Route über die GRUU-Adresse herzustellen. Wenn dieser Wert auf <strong>TRUE</strong> festgelegt ist, ist Lync Server autorisiert, eine Route zum Dienst herzustellen. Wenn dieser Wert auf <strong>FALSE</strong> festgelegt ist, ist Lync Server nicht autorisiert, eine Route zum Dienst herzustellen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut definiert ein Attribut, das eine Telefonroute für die Verwendung qualifiziert. Die Auswahl einer Telefonroute erfolgt ausgehend von zwei Elementen: dem Verwendungsattribut, das der Telefonroute zugewiesen ist, und den Attributen des Anrufers, die die zulässige Richtlinienverwendung festlegen. Es wird die erste Telefonroute mit einem Verwendungsattribut ausgewählt, das einer zulässigen Verwendung des Benutzers entspricht.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN) für die Routenverwendung.</p>
<p>Forwardlink: <strong>Link ID 11032</strong></p>
<p>Das Attribut ist ein Forwardlink zum entsprechenden Backwardlink <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>In Lync Server 2010 veraltet.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Dieses Attribut enthält den DN, der auf den Pool zeigt, über den der gesamte an diese MCU oder diesen vertrauenswürdigen Dienst adressierte SIP-Datenverkehr geleitet werden muss.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (veraltet)</p></td>
<td><p>Dieses einwertige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass ein Administrator leichter auf die Regel verweisen kann.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Dieses Attribut stellt die Schemaversion dar, die derzeit in der Organisation bereitgestellt ist.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (veraltet)</p></td>
<td><p>Dieses Attribut begrenzt die Zahl der Suchergebnisse, die bei einer Verzeichnissuche zurückgegeben werden, wenn ein Benutzer mit Communicator einen Kontakt sucht. Der Wert des Attributs überschreibt den vom Client übergebenen Wert.</p></td>
<td><p>In Lync Server 2010 veraltet.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (veraltet)</p></td>
<td><p>Dieses Attribut beschränkt die Anzahl der zurückgegebenen Suchanforderungen.</p></td>
<td><p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Dieses mehrwertige Attribut stellt einen Backwardlink mit einer Liste von Distinguished Names (DN) für Telefonrouten dar. Diese DNs zeigen auf einen Pool oder ein <strong>TrustedService</strong>-Objekt.</p>
<p>Dieses Attribut stellt das Gegenstück zum Forwardlink <strong>msRTCSIP-TrustedServiceLinks</strong> dar.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (veraltet)</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN). Diese Distinguished Names (DN) stellen Backwardlinks dar, die auf andere Serverobjekte verweisen, denen ein Standardstandortprofil zugewiesen werden kann.</p>
<p>Backwardlink: <strong>Link ID 11037</strong></p>
<p>Der entsprechende Forwardlink zu diesem Backwardlink lautet <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Das Backwardlinkattribut verweist ausschließlich auf Pools und Vermittlungsserver.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Dieses Attribut definiert die Versionsinformationen des Servers. Diese Versionsnummer gilt für alle Serverrollen. Es handelt sich um einen monoton ansteigenden Ganzzahlwert, der mit jeder offiziellen Produktversion erhöht wird.</p>
<p>Folgende Werte sind zulässig:</p>
<ul>
<li><p>Nicht definiert: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 mit SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Dieses einwertige Attribut vom Typ Integer gibt gemäß folgender Definition den Typ des Objekts an, auf das <strong>msDS-SourceObjectDN</strong> zeigt.</p>
<ul>
<li><p>null | 0x00000001: Stellt ein Windows NT Server-Prinzipalbenutzerobjekt aus einer anderen Gesamtstruktur dar.</p></li>
<li><p>Die folgenden Attribute stellen einen Gruppentyp aus einer anderen Gesamtstruktur für die Erweiterung von Verteilergruppen dar:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: Stellt ein Objekt für die automatische Telefonzentrale oder den Teilnehmerzugriff aus derselben oder aus einer anderen Gesamtstruktur dar.</p></li>
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
<td><p>Dieses Attribut ermöglicht das Verschieben eines Benutzers oder Kontaktobjekts von einem Lync Server oder -Pool in einen anderen. Es wird der Kontaktklasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie Kontaktobjekte und nicht Benutzerobjekte SIP-aktiviert sind.</p>
<p>Gültiger Wert ist der DN des Standard Edition-Zielservers bzw. Front-End-Zielpools, in den ein Benutzer verschoben werden soll.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (veraltet)</p></td>
<td><p>Dieses einwertige Zeichenfolgenattribut enthält ein Telefonnummernmuster oder einen Nummernbereich, das bzw. der an die in <strong>msRTCSIP-Gateways</strong> definierten Gateways weitergeleitet werden soll.</p></td>
<td><p>In Lync Server 2010 veraltet.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Dieses Attribut speichert Name/Wert-Paare zur gezielten Zuweisung von Richtlinien zu Lync Server-Benutzern.</p></td>
<td><p>Neu in Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Dieses Attribut speichert die eindeutige ID eines Mandanten.</p></td>
<td><p>Neu in Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (veraltet)</p></td>
<td><p>Dieses Attribut wird von der VoIP-Funktion von Lync Server verwendet und enthält die Übersetzungszeichenfolge, die bei einer gefundenen Übereinstimmung auf die gewählte Nummer angewendet wird.</p></td>
<td><p>Neu in Office Communications Server 2007.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN der MCU enthält. Dies ist ein einwertiges Attribut. Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des Servers enthält, auf dem der Proxyserver ausgeführt wird. Dies ist ein einwertiges Attribut. Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Dieses einwertige Attribut stellt den FQDN eines vertrauenswürdigen Servers dar.</p></td>
<td><p>Neu in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Dieses Attribut gibt die Versionsnummer eines Servers in der Liste der vertrauenswürdigen Server an.</p>
<p>Folgende Werte sind zulässig:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
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
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, z. B. auf einen Mediarelay-Authentifizierungsdienst. Ein Mediarelay-Authentifizierungsdienst (wird auf dem gleichen physischen Edgeserver wie der A/V-Konferenzdienst ausgeführt) muss einem Pool zugeordnet sein, um Remotebenutzern Audiofunktionen zur Verfügung stellen zu können.</p>
<p>Der entsprechende Backwardlink zu diesem Forwardlinkattribut lautet <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Dieses Attribut vom Typ Integer definiert die Portnummer, über die Verbindungen mit diesem GRUU-Dienst hergestellt werden.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den Typ des betreffenden GRUU-Diensts definiert.</p>
<p>Folgende GRUU-Diensttypen sind zulässig:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Mediarelay-Authentifizierungsdienst (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des IIS-Servers enthält, auf dem Lync Server-Webdienste ausgeführt werden. Dies ist ein einwertiges Attribut. Gültiger Wert pro Segment sind 63 Zeichen bzw. für den gesamten FQDN 255 Zeichen.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (veraltet)</p></td>
<td><p>Dieses Attribut definiert verschiedene Unified Communications-Optionen (UC), die global für alle Benutzer- oder Kontaktobjekte aktiviert sind. Das Attribut stellt eine Bitmaske vom Typ Integer dar. Jede Option wird durch Setzen eines Bits angegeben.</p>
<p>Folgender Wert (und die verknüpfte Bitposition) ist gültig:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (Bitposition 2)</p></li>
</ul>
<p>Wenn dieses Bit gesetzt ist, wird die UC-Richtlinie pro Benutzer definiert.</p></td>
<td><p>In Lync Server 2010 veraltet.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (veraltet)</p></td>
<td><p>Dieses einwertige Attribut enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator diesem Benutzer zugewiesen hat.</p></td>
<td><p>In Lync Server 2010 veraltet.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (veraltet)</p></td>
<td><p>Dieses Attribut stellt eine Liste aller Domänen in einer Gesamtstruktur bereit, in der SIP-aktivierte Benutzer gehostet werden. Die Standardeinstellung ist eine leere Liste. Damit wird angegeben, dass alle Gesamtstrukturdomänen SIP-aktiviert sind.</p>
<p>Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen der einzelnen Domänen darstellen.</p></td>
<td><p>Neu in Live Communications Server 2005.</p>
<p>In Lync Server 2010 veraltet.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Dieses Attribut gibt an, ob der Benutzer derzeit für Lync Server aktiviert ist.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Name/Wert-Paaren im Format &quot;Name=Wert&quot;. Das Attribut ist für die Replikation mit dem globalen Katalog gekennzeichnet.</p></td>
<td><p>Neu in Live Communications Server 2005 mit SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt zeigt.</p></td>
<td><p>Neu in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Dieses Attribut speichert Name/Wert-Paare für Benutzerrichtlinien.</p></td>
<td><p>Neu in Lync Server 2010.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN) mit Binärwert (DN_WITH_BINARY), die auf globale Benutzerrichtlinien unterschiedlichen Typs zeigen. Der Binärteil gibt den Typ der Richtlinie an, auf die der DN-Teil zeigt.</p>
<p>Folgende Binärwerte sind zulässig:</p>
<ul>
<li><p>0x00000001: Besprechungsrichtlinie</p></li>
<li><p>0x00000002: UC-Richtlinie (Unified Communications)</p></li>
<li><p>0x00000005: Anwesenheitsrichtlinie</p></li>
</ul></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Hierbei handelt es sich um die SIP Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich am selben Front-End-Server.</p></td>
<td><p>Neues in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Dies ist ein mehrwertiges Attribut. Dieses Attribut ist für die spätere Verwendung reserviert.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Dieses einwertige Attribut zeigt auf den Pool oder Standard Edition-Server, zu dem die Webkomponenten gehören.</p>
<p>Forwardlink: <strong>Link ID 11028</strong></p>
<p>Der entsprechende Backwardlink zu diesem Forwardlinkattribut lautet <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Neu in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Dieses mehrwertige Attribut ist eine Liste mit Distinguished Names (DN). Das Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</p>
<p>Backwardlink: <strong>Link ID 11029</strong></p>
<p>Der entsprechende Forwardlink zu diesem Backwardlink lautet <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
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
<td><p>Dieses bereits vorhandene Active Directory-Attribut wird in Telefoniediensten verwendet, um die Liste alternativer TCP/IP-Adressen für ein Telefon anzugeben.</p></td>
<td><p>Neu im Windows Server 2008-Betriebssystem.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Dieses bereits vorhandene Active Directory-Attribut wird – ausschließlich bei Kontaktobjekten – von den VoIP-Komponenten in Lync Server verwendet, um Anrufe an die automatische Telefonzentrale für Unified Messaging und an die Teilnehmerzugriffsnummern weiterzuleiten. Die uneingeschränkte Anrufweiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert. Dieses Konto wird speziell für die automatische Telefonzentrale und den Teilnehmerzugriff erstellt. Die Attribute dieses Kontos sollten von Administratoren nicht geändert werden.</p></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Dieses bereits vorhandene mehrwertige Active Directory-Attribut ist Teil des Active Directory-Basisschemas, das mit Windows 2000 eingeführt wurde. Es enthält die verschiedenen X400-, X500- und SMTP-Adressen für die E-Mail-Adresse des Benutzers. Ab Live Communications Server 2003 und höher wurde dieser Liste der SIP-URI des Benutzers mit dem Tag &quot;sip:&quot; hinzugefügt.</p>
<p>Folgende Anwendungen suchen nach dem SIP-URI eines Benutzers anhand dieses Attributs:</p>
<ul>
<li><p>Microsoft Office Outlook 2003-Client für Messaging und Collaboration</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Dieses bereits vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</p></td>
<td><p>Neu im Windows 2000-Betriebssystem.</p></td>
</tr>
</tbody>
</table>

