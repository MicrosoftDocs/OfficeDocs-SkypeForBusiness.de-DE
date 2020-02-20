---
title: 'Lync Server 2013: Installieren und Konfigurieren von Watcher-Knoten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

*Watcher-Knoten* sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden. *Synthetische Transaktionen* sind Windows PowerShell-Cmdlets, mit denen sichergestellt wird, dass wichtige Endbenutzerszenarien wie die Möglichkeit zum Anmelden am System oder die Möglichkeit zum Austauschen von Sofortnachrichten wie erwartet funktionieren. Für lync Server 2013 kann System Center Operations Manager die synthetischen Transaktionen ausführen, die in der folgenden Tabelle aufgeführt sind. In der Tabelle sind drei verschiedene synthetische Transaktionstypen aufgeführt:

  - **Standard**. Hierbei handelt es sich um die synthetischen Transaktionen, die standardmäßig ein Watcher-Knoten ausgeführt wird. Wenn Sie einen neuen Watcher-Knoten erstellen, haben Sie die Möglichkeit, anzugeben, welche synthetischen Transaktionen dieser Knoten ausführen soll. (Dies ist der Zweck des Parameters "Tests", der vom Cmdlet " **New-CsWatcherNodeConfiguration** " verwendet wird.) Wenn Sie den Parameter Tests nicht verwenden, wenn der Watcher-Knoten erstellt wird, werden alle synthetischen Standardtransaktionen automatisch ausgeführt, und es werden keine synthetischen, nicht standardmäßigen Transaktionen ausgeführt. Das bedeutet beispielsweise, dass der Watcher-Knoten so konfiguriert wird, dass der Test-CsAddressBookService-Test ausgeführt wird, aber nicht für die Ausführung des Test-csexumconnectivity "-Tests konfiguriert ist.

  - **Nicht Standard**. Wie es der Name schon sagt, handelt es sich bei synthetischen Transaktionen dieses Typs um Tests, die vom Watcher-Knoten nicht standardmäßig durchgeführt werden. Der Knoten kann jedoch zum Ausführen von nicht standardmäßigen synthetischen Transaktionen aktiviert werden. Dies können Sie beim Erstellen des Watcher-Knotens (mithilfe des **New-CsWatcherNodeConfiguration**-Cmdlets) oder jederzeit später vornehmen. Für viele der nicht standardmäßigen synthetischen Transaktionen sind zusätzliche Einrichtungsschritte erforderlich. Ausführliche Informationen finden Sie unter [spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Erweitert**. Erweiterte Tests sind ein spezieller Typ von nicht standardmäßigen synthetischen Transaktionen. Im Unterschied zu anderen synthetischen Transaktionen können sie bei jedem Durchgang mehrere Male ausgeführt werden. Dies kann nützlich sein, wenn bestimmte Verhaltensweisen – wie zum Beispiel mehrere PSTN-VoIP-Routen für einen Pool – überprüft werden sollen. Zur Konfiguration werden einem Watcher-Knoten einfach mehrere Instanzen eines erweiterten Tests hinzugefügt.

Ausführliche Informationen zum Prozess des Hinzufügens weiterer synthetischer Transaktionen zu einem Watcher-Knoten finden Sie unter [Managing Watcher Nodes in lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Sie können die lync Server-Verwaltungsshell verwenden, um synthetische Transaktionen aus einem Watcher-Knoten zu entfernen.

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
<td><p>Test-CsIM (IM)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, Peer-zu-Peer-Sofortnachrichten zu senden.</p></td>
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
<td><p>Wird nicht mit der lokalen Version von lync Server 2013 verwendet</p></td>
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
<td><p>Test-csavedgeconnectivity "(AVEdgeConnectivity)</p></td>
<td><p>Überprüft, ob die Audio-/Video-Edgeserver in der Lage sind, Verbindungen für Peer-zu-Peer-Anrufe und Konferenzanrufe entgegenzunehmen.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-csdataconference "(dataconference)</p></td>
<td><p>Überprüft, ob Benutzer an einer Datenzusammenarbeitskonferenz (eine Online-Besprechung, zu der Aktivitäten wie Whiteboards und Abstimmungen gehören) teilnehmen können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-csexumconnectivity "(ExumConnectivity)</p></td>
<td><p>Bestätigt, dass ein Benutzer eine Verbindung mit Exchange Unified Messaging (um) herstellen kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, in Konferenzen Sofortnachrichten zu senden und an Sofortnachrichtengesprächen mit drei oder mehr Personen teilzunehmen.</p></td>
<td><p>Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Überprüft, ob Benutzer in der Lage sind, geplante Besprechungen zu erstellen und an geplanten Besprechungen über einen Weblink teilzunehmen.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Überprüft, ob Benutzer mit Mobilgeräten in der Lage sind, sich zu registrieren und Sofortnachrichten zu senden.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-cspersistentchatmessage "(PersistentChatMessage)</p></td>
<td><p>Bestätigt, dass Benutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Überprüft, ob die Kontakte eines Benutzers über den einheitlichen Kontaktspeicher zugänglich sind. Der einheitliche Kontaktspeicher bietet Benutzern eine Möglichkeit, eine einzelne Gruppe von Kontakten zu verwalten, auf die mithilfe von lync 2013, Outlook und/oder Outlook Web Access zugegriffen werden kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
<tr class="even">
<td><p>Test-csxmppim "(XmppIM)</p></td>
<td><p>Überprüft, ob eine Sofortnachricht über das XMPP-Gateway (Extensible Messaging and Presence Protocol) gesendet werden kann.</p></td>
<td><p>Nicht Standard</p></td>
</tr>
</tbody>
</table>


Sie müssen keine Watcher-Knoten installieren, um System Center Operations Manager verwenden zu können. Wenn Sie diese Knoten nicht installieren, können Sie weiterhin Echtzeitwarnungen von lync Server 2013 Komponenten erhalten, wenn ein Problem auftritt. (Die Komponente und das Benutzer Management Pack verwenden keine Watcher-Knoten.) Watcher-Knoten sind jedoch erforderlich, wenn Sie End-to-End-Szenarien mithilfe des Active Monitoring Management Packs überwachen möchten.

<div>


> [!NOTE]  
> Administratoren können synthetische Transaktionen auch manuell ausführen, ohne dass dazu der Operations Manager installiert oder verwendet werden muss. Ausführliche Informationen zu den verschiedenen Cmdlets für Test-CS finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">lync Server 2013 Cmdlets-Index</A>.



</div>

Je nach der Größe Ihrer Bereitstellung können synthetische Transaktionen einen großen Teil Ihrer Arbeitsspeicher- und Prozessorressourcen in Anspruch nehmen. Aus diesem Grund wird empfohlen, als Watcher-Knoten einen dedizierten Computer zu verwenden. Beispielsweise sollten Sie keine Front-End-Server konfigurieren, die als Watcher-Knoten fungieren soll. Watcher-Knoten sollten die folgenden Hardwarespezifikationen erfüllen:

<div>


> [!NOTE]  
> Ein Legacy Microsoft lync Server 2010 Watcher-Knoten kann nicht mit einem lync Server 2013 Watcher-Knoten auf demselben Computer zusammengefasst werden. Dies liegt daran, dass die Hauptsystem Dateien für lync Server 2010 und lync Server 2013 nicht auf demselben Computer installiert werden können.<BR>Lync Server 2013 Watcher-Knoten können jedoch gleichzeitig sowohl lync Server 2013 als auch lync Server 2010 überwachen. Die synthetischen Transaktionen vom Typ "Standard" werden in beiden Produktversionen unterstützt.



</div>

Lync Server 2013 Watcher-Knoten können innerhalb oder außerhalb eines Unternehmens bereitgestellt werden, um Folgendes zu überprüfen:

  - <span></span>  
    Konnektivität zu Pools für Benutzer innerhalb des Unternehmens

  - <span></span>  
    Konnektivität über Umkreisnetzwerke für Remotebenutzer, die außerhalb des Unternehmens arbeiten

  - <span></span>  
    Konnektivität zu Branch Office Appliances

  - <span></span>  
    Konnektivität mit lync Server 2010 innerhalb des Unternehmens und über Umkreisnetzwerke.

Zur leichteren Verwaltung stehen unterschiedliche Authentifizierungsoptionen für innerhalb oder außerhalb des Unternehmens zur Verfügung. Ausführliche Informationen finden Sie unter [Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Wenn Sie einen Computer als Watcher-Knoten konfigurieren möchten, müssen Sie die folgenden Schritte ausführen, nachdem Sie System Center Operations Manager installiert und die lync Server 2013 Management Packs importiert haben.

Bevor Sie die lync Server 2013 Kerndateien und die System Center-Agentdateien installieren, sollten Sie auch sicherstellen, dass der Watcher-Knoten Computer alle Voraussetzungen für die Installation von lync Server 2013 erfüllt. Außerdem sollten auf dem Watcher-Computer auch die folgenden Komponenten installiert sein:


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
<li><p>64-Bit-Prozessor, Quad-Core, 2,33 GHz oder höher</p></li>
<li><p>64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkbetriebs System</p></td>
<td><ul>
<li><p>1 Netzwerkadapter 1 Gbit/s</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 oder</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Die Vollversion von .NET Framework 4.5.

  - Windows Identity Foundation.

  - Windows PowerShell 3.0.

Sobald alle Voraussetzungen erfüllt sind, können Sie den Watcher-Knoten wie folgt installieren:

  - Installieren der lync Server 2013 Kerndateien auf dem Watcher-Knoten Computer.

  - Installieren von System Center Operations Manager-Agent auf dem Monitor Knoten Computer.

  - Ausführen der Datei WATCHERNODE.MSI

  - Konfigurieren von Testbenutzern für den Watcher-Knoten mithilfe des **CsWatcherNodeConfiguration**-Cmdlets

</div>

<span> </span>

</div>

</div>

</div>

