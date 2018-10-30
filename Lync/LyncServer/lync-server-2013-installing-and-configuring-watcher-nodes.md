---
title: Installieren und Konfigurieren von Watcher-Knoten
TOCTitle: Installieren und Konfigurieren von Watcher-Knoten
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204943(v=OCS.15)
ms:contentKeyID: 49294185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren und Konfigurieren von Watcher-Knoten

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

*Watcher-Knoten* sind Computer, die in regelmäßigen Abständen synthetische Lync Server-Transaktionen ausführen. *Synthetische Transaktionen* sind Windows PowerShell-Cmdlets, die überprüfen, ob wichtige Endbenutzerszenarien (wie die Fähigkeit zur Anmeldung beim System oder zum Austausch von Chatnachrichten) ordnungsgemäß funktionieren. Für Lync Server 2013 kann der System Center Operations Manager die in der folgenden Tabelle aufgeführten synthetischen Transaktionen ausführen, von denen es drei verschiedene Typen gibt:

  - **Standard**. Das sind die synthetischen Transaktionen, die von einem Watcher-Knoten standardmäßig ausgeführt werden. Beim Erstellen eines neuen Watcher-Knotens können Sie (mit dem vom **New-CsWatcherNodeConfiguration**-Cmdlet verwendeten Tests-Parameter) angeben, welche synthetischen Transaktionen dieser Knoten ausführen soll. Wenn Sie den Parameter "Tests" beim Erstellen des Knotens nicht verwenden, wird der Knoten automatisch alle synthetischen Transaktionen vom Typ "Standard" und keine der Transaktionen vom Typ "Nicht Standard" ausführen. Das würde zum Beispiel bedeuten, dass der Watcher-Knoten so konfiguriert wird, dass er den Test-CsAddressBookService-Test, nicht jedoch den Test-CsExumConnectivity-Test ausführt.

  - **Nicht Standard**. Wie es der Name schon sagt, handelt es sich bei synthetischen Transaktionen dieses Typs um Tests, die vom Watcher-Knoten nicht standardmäßig durchgeführt werden. Der Knoten kann jedoch zum Ausführen von nicht standardmäßigen synthetischen Transaktionen aktiviert werden. Dies können Sie beim Erstellen des Watcher-Knotens (mithilfe des **New-CsWatcherNodeConfiguration**-Cmdlets) oder jederzeit später vornehmen. Für viele der nicht standardmäßigen synthetischen Transaktionen sind zusätzliche Einrichtungsschritte erforderlich. Einzelheiten dazu finden Sie unter [Besondere Anweisungen zum Einrichten von synthetischen Transaktionen](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Erweitert**. Erweiterte Tests sind ein spezieller Typ von nicht standardmäßigen synthetischen Transaktionen. Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden. Dies kann nützlich sein, wenn bestimmte Verhaltensweisen – wie zum Beispiel mehrere PSTN-VoIP-Routen für einen Pool – überprüft werden sollen. Zur Konfiguration werden einem Watcher-Knoten einfach mehrere Instanzen eines erweiterten Tests hinzugefügt.

Nähere Informationen über die Vorgehensweise zum Hinzufügen anderer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Verwalten von Watcher-Knoten](lync-server-2013-managing-watcher-nodes.md). Zum Entfernen synthetischer Transaktionen von einem Watcher-Knoten können Sie die Lync Server-Verwaltungsshell verwenden.

Zu den für Watcher-Knoten verfügbaren synthetischen Transaktionen gehören:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet-Name (Test-Name)</th>
<th>Beschreibung</th>
<th>Typ von synthetischer Transaktion</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, HTTP Benutzer nachzuschlagen, die nicht in ihrer Kontaktliste stehen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (Chat)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Chatnachrichten zu senden.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Audioanrufe zu tätigen (nur Signal).</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Anwesenheit)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, die Anwesenheit anderer Benutzer zu erkennen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registrierung)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, sich bei Lync anzumelden.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Wird bei der lokalen Version von Lync Server 2013 nicht verwendet</p></td>
<td><p>Erweitert</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.</p></td>
<td><p>Nicht Standard, Erweitert</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Online-Besprechung, zu der Aktivitäten wie Whiteboards und Abstimmungen gehören) teilnehmen können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Überprüft, ob ein Benutzer eine Verbindung zu Exchange Unified Messaging (UM) herstellen kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, in Konferenzen Chatnachrichten zu senden und an Chatnachrichtenunterhaltungen mit drei oder mehr Personen teilzunehmen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, geplante Besprechungen zu erstellen und an geplanten Besprechungen über einen Weblink teilzunehmen.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Chatnachrichten zu senden.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Überprüft, ob Benutzer mithilfe des Beständiger Chat-Diensts Nachrichten austauschen können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der einheitliche Kontaktspeicher bietet Benutzern die Möglichkeit, ihre Kontakte an einer zentralen Stelle zu pflegen, wo sie per Lync 2013, Outlook und/oder Outlook Web Access erreichbar sind.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Überprüft, ob eine Chatnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
</tbody>
</table>


Sie brauchen keine Watcher-Knoten zu installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie bei Problemen trotzdem noch Echtzeitalarme von Lync Server 2013-Komponenten erhalten. (Das Komponenten- und Benutzerverwaltungspaket macht keinen Gebrauch von Watcher-Knoten.) Allerdings sind Watcher-Knoten erforderlich, wenn Sie mithilfe des Pakets für die aktive Überwachungsverwaltung End-to-End-Szenarien überwachen möchten.


> [!NOTE]
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne dass dazu der Operations Manager installiert oder verwendet werden muss. Einzelheiten zu den verschiedenen Test-Cs-Cmdlets finden Sie im <A href="https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps">Index der Lync Server&nbsp;2013-Cmdlets</A>.



Je nach der Größe Ihrer Bereitstellung können synthetische Transaktionen einen großen Teil Ihrer Arbeitsspeicher- und Prozessorressourcen in Anspruch nehmen. Aus diesem Grund wird empfohlen, als Watcher-Knoten einen dedizierten Computer zu verwenden. So sollten Sie zum Beispiel keinen Front-End-Server als Watcher-Knoten konfigurieren. Watcher-Knoten sollten folgenden Hardwarespezifikationen erfüllen:


> [!NOTE]
> Ein älterer Microsoft Lync Server 2010-Watcher-Knoten kann nicht zusammen mit einem Lync Server 2013-Watcher-Knoten auf dem gleichen Computer untergebracht werden, da die wichtigsten Systemdateien für Lync Server 2010 und Lync Server 2013 nicht auf dem gleichen Computer installiert werden können.<BR>Allerdings können Lync Server 2013-Watcher-Knoten sowohl Lync Server 2013 als auch Lync Server 2010 gleichzeitig überwachen. Die synthetischen Transaktionen vom Typ "Standard" werden in beiden Produktversionen unterstützt.



Lync Server 2013-Watcher-Knoten können innerhalb oder außerhalb des Unternehmens bereitgestellt werden, um bei der Überprüfung der folgenden Punkte zu helfen:

  - Konnektivität zu Pools für Benutzer innerhalb des Unternehmens

  - Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten

  - Konnektivität zu Branch Office Appliances

  - Konnektivität zu Lync Server 2010 innerhalb des Unternehmens und über Umkreisnetzwerke

Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens zur Verfügung. Weitere Informationen dazu finden Sie unter [Konfigurieren eines Watcher-Knotens für die Ausführung von synthetischen Transaktionen](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Wenn Sie einen Computer so konfigurieren möchten, dass er als Watcher-Knoten fungiert, müssen Sie die folgenden Schritte durchführen, nachdem Sie System Center Operations Manager installiert und die Lync Server 2013-Verwaltungspakete importiert haben.

Vor dem Installieren der Hauptdateien von Lync Server 2013 und der System Center-Agentendateien sollten Sie auch sicherstellen, dass der Computer für den Watcher-Knoten alle erforderlichen Voraussetzungen für die Installation von Lync Server 2013 erfüllt. Außerdem sollten auf dem Watcher-Computer auch die folgenden Komponenten installiert sein:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Mindestanforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Eine der folgenden Optionen:</p>
<ul>
<li><p>64-Bit-Prozessor, Vierkern, mindestens 2.33 GHz</p></li>
<li><p>64-Bit-2-Wege-Prozessor, Doppelkern, mindestens 2.33 GHz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkbetriebssystem</p></td>
<td><ul>
<li><p>1 Netzwerkadapter, 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 oder</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Die Vollversion von .NET Framework 4.5.

  - Windows Identity Foundation

  - Windows PowerShell 3.0

Sobald alle Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten wie folgt installieren:

  - Installieren der Hauptdateien von Lync Server 2013 auf dem Watcher-Knoten-Computer

  - Installieren des System Center Operations Manager-Agents auf dem Watcher-Knoten-Computer

  - Ausführen der Datei WATCHERNODE.MSI

  - Konfigurieren von Testbenutzern für den Watcher-Knoten mithilfe des **CsWatcherNodeConfiguration**-Cmdlets

