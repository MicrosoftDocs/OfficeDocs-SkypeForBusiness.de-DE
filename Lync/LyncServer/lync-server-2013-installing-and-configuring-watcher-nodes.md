---
title: 'Lync Server 2013: Installieren und Konfigurieren von Watcher-Knoten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

*Watcher-Knoten* sind Computer, die synthetische lync Server-Transaktionen in regelmäßigen Abständen ausführen. *Synthetische Transaktionen* sind Windows PowerShell-Cmdlets, mit denen sichergestellt wird, dass wichtige Endbenutzerszenarien wie die Möglichkeit zur Anmeldung beim System oder die Möglichkeit zum Austauschen von Sofortnachrichten wie erwartet funktionieren. Bei lync Server 2013 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle aufgeführt sind. Es gibt drei verschiedene synthetische Transaktionstypen, die in der Tabelle angezeigt werden:

  - **Standard**. Hierbei handelt es sich um die synthetischen Transaktionen, die von einem Watcher-Knoten standardmäßig ausgeführt werden. Wenn Sie einen neuen Watcher-Knoten erstellen, haben Sie die Möglichkeit, die synthetischen Transaktionen anzugeben, die der Knoten ausführen soll. (Dies ist der Zweck des Parameters Tests, der vom Cmdlet **New-CsWatcherNodeConfiguration** verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden automatisch alle synthetischen Standardtransaktionen ausgeführt, und es werden keine der nicht standardmäßigen synthetischen Transaktionen ausgeführt. Das bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert ist, dass er den Test-CsAddressBookService-Test ausführt, aber nicht für die Ausführung des Test-CsExumConnectivity-Tests konfiguriert ist.

  - **Nicht Standard**. Wie der Name schon andeutet, werden nicht standardmäßige synthetische Transaktionen getestet, dass Watcher-Knoten nicht standardmäßig ausgeführt werden. Allerdings kann der Watcher-Knoten aktiviert werden, um eine der nicht standardmäßigen synthetischen Transaktionen auszuführen. Sie können dies tun, wenn Sie den Watcher-Knoten erstellen (mithilfe des Cmdlets **New-CsWatcherNodeConfiguration** ) oder zu einem beliebigen Zeitpunkt danach. Für viele der nicht standardmäßigen synthetischen Transaktionen sind zusätzliche Setupschritte erforderlich. Ausführliche Informationen finden Sie unter [spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Verlängert**. Erweiterte Tests sind eine spezielle Art von nicht standardmäßigen synthetischen Transaktionen. Im Gegensatz zu anderen synthetischen Transaktionen können erweiterte Tests während der einzelnen Durchlaufzeiten mehrmals ausgeführt werden. Dies kann sich als hilfreich erweisen, wenn Sie Verhaltensweisen wie mehrere PSTN-VoIP-Routen (Public Switched Telephone Network) für einen Pool überprüfen. Dies kann einfach durch Hinzufügen mehrerer Instanzen eines erweiterten Tests zu einem Watcher-Knoten konfiguriert werden.

Details zum Verfahren zum Hinzufügen weiterer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Verwalten von Watcher-Knoten in lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Sie können die lync Server-Verwaltungsshell verwenden, um synthetische Transaktionen von einem Watcher-Knoten zu entfernen.

Folgende synthetische Transaktionen sind für Monitorknoten verfügbar:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name des Cmdlets (Name des Tests)</th>
<th>Beschreibung</th>
<th>Synthetischer Transaktionstyp</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Bestätigt, dass Benutzer nach Benutzern suchen können, die nicht in Ihrer Kontaktliste enthalten sind.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Bestätigt, dass Benutzer nach Benutzern suchen können, die sich nicht in Ihrer Kontaktliste befinden, über http.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (im)</p></td>
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
<td><p>Bestätigt, dass Benutzer sich bei lync anmelden können.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Nicht in Verbindung mit der lokalen Version von lync Server 2013</p></td>
<td><p>Erweiterten</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Anrufe von Personen außerhalb des Unternehmens (PSTN-Nummern) entgegenzunehmen oder diese anzurufen.</p></td>
<td><p>Nicht Standard, erweitert</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, eine Audio-/Videokonferenz zu erstellen und daran teilzunehmen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Bestätigt, dass die A/V-Edgeserver Verbindungen für Peer-to-Peer-Anrufe und Konferenzanrufe akzeptieren können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Bestätigt, dass Benutzer an einer Daten Zusammenarbeits Konferenz teilnehmen können, einer Onlinebesprechung, die Aktivitäten wie Whiteboards und Umfragen umfasst.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, in Konferenzen Chatnachrichten zu senden und an Chatnachrichtenunterhaltungen mit drei oder mehr Personen teilzunehmen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Bestätigt, dass Benutzer in der Lage sind, geplante Besprechungen über einen Webadressen Link zu erstellen und daran teilzunehmen.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Chatnachrichten zu senden.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Überprüft, ob Benutzer über den Dienst für beständigen Chat Sprachnachrichten austauschen können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der Unified Contact Store bietet Benutzern eine Möglichkeit zum Verwalten einer einzelnen Gruppe von Kontakten, auf die mithilfe von lync 2013, Outlook und/oder Outlook Web Access zugegriffen werden kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Bestätigt, dass eine Sofortnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
</tbody>
</table>


Sie müssen Watcher-Knoten nicht installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie weiterhin in Echtzeit Benachrichtigungen über lync Server 2013-Komponenten erhalten, wenn ein Problem auftritt. (Das Komponenten-und Benutzer Verwaltungspaket verwendet keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien überwachen möchten, indem Sie das aktive Überwachungs Management Pack verwenden.

<div>


> [!NOTE]  
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne Operations Manager verwenden oder installieren zu müssen. Ausführliche Informationen zu den verschiedenen Cmdlets für das Test-CS finden Sie im <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">lync Server 2013</A>-Cmdlets-Index.



</div>

Abhängig von der Größe Ihrer Bereitstellung verwenden synthetische Transaktionen möglicherweise eine große Menge an Computerspeicher und Prozessorzeit. Aus diesem Grund empfehlen wir, einen dedizierten Computer als Watcher-Knoten zu verwenden. So sollten Sie beispielsweise einen Front-End-Server nicht so konfigurieren, dass er als Watcher-Knoten fungiert. Watcher-Knoten sollten die folgenden Hardwarespezifikationen erfüllen:

<div>


> [!NOTE]  
> Ein älterer Microsoft lync Server 2010 Watcher-Knoten kann nicht auf demselben Computer mit einem lync Server 2013 Watcher-Knoten angeordnet werden. Dies liegt daran, dass die Hauptsystem Dateien für lync Server 2010 und lync Server 2013 nicht auf demselben Computer installiert werden können.<BR>Lync Server 2013 Watcher-Knoten können jedoch sowohl lync Server 2013 als auch lync Server 2010 gleichzeitig überwachen. Die standardmäßigen synthetischen Transaktionen werden in beiden Produktversionen unterstützt.



</div>

Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:

  - <span></span>  
    Konnektivität zu Pools für Benutzer innerhalb des Unternehmens

  - <span></span>  
    Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten.

  - <span></span>  
    Konnektivität zu Branch Office Appliances

  - <span></span>  
    Konnektivität mit lync Server 2010 innerhalb des Unternehmens und über Umkreisnetzwerke.

Für innerhalb und außerhalb des Unternehmens stehen unterschiedliche Authentifizierungsoptionen zur Vereinfachung der Verwaltung zur Verfügung. Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Wenn Sie einen Computer als Watcher-Knoten konfigurieren möchten, müssen Sie die folgenden Schritte ausführen, nachdem Sie System Center Operations Manager installiert und die lync Server 2013-Verwaltungspakete importiert haben.

Bevor Sie die lync Server 2013-Core-Dateien und die System Center-Agent-Dateien installieren, sollten Sie auch sicherstellen, dass der Watcher-Knoten Computer alle Voraussetzungen für die Installation von lync Server 2013 erfüllt. Darüber hinaus sollte auf dem Watcher-Knoten Computer auch die folgenden Elemente installiert sein:


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
<li><p>64-Bit-Prozessor, Vierkern, mindestens 2,33 GHz</p></li>
<li><p>64-Bit-2-Wege-Prozessor, Doppelkern, mindestens 2,33 GHz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkbetriebssystem</p></td>
<td><ul>
<li><p>1 Netzwerkadapter 1 Gbit/s</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 oder</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Die Vollversion von .NET Framework 4,5.

  - Windows Identity Foundation.

  - Windows PowerShell 3,0.

Sobald alle diese Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten folgendermaßen konfigurieren:

  - Installieren der lync Server 2013-Core-Dateien auf dem Watcher-Knoten Computer.

  - Installieren des System Center Operations Manager-Agents auf dem Watcher-Knoten Computer.

  - Ausführen der ausführbaren Datei Watchernode. msi

  - Verwenden Sie die **CsWatcherNodeConfiguration** -Cmdlets, um Testbenutzer so zu konfigurieren, dass Sie vom Watcher-Knoten verwendet werden.

</div>

<span> </span>

</div>

</div>

</div>

