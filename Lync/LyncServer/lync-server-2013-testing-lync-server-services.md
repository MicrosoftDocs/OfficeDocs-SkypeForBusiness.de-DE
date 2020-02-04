---
title: 'Lync Server 2013: Testen der lync Server-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Testen der lync Server-Dienste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Täglich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsComputer-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsComputer überprüft den Status aller lync Server 2013-Dienste, die auf dem lokalen Computer ausgeführt werden. (Test-CsComputer kann nur lokal ausgeführt werden, kann nicht von einer Remoteinstanz von Windows PowerShell ausgeführt werden.) Das Cmdlet überprüft auch, ob die entsprechenden Firewall-Ports auf dem Computer geöffnet sind, und bestimmt, ob die Active Directory-Gruppen, die bei der Installation von lync Server 2013 erstellt wurden, den entsprechenden lokalen Gruppen hinzugefügt wurden. Beispielsweise überprüft Test-CsComputer, ob die Active Directory-Gruppe RTCUniversalUserAdmins der Gruppe Administratoren hinzugefügt wurde.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsComputer" kann nur auf dem lokalen Computer ausgeführt werden, Sie können Test-CsComputer nicht aus einer Remoteinstanz von Windows PowerShell aufrufen. Standardmäßig werden in Test-CsComputer nur sehr wenige Ausgaben auf dem Bildschirm angezeigt, stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben. Aus diesem Grund empfehlen wir, dass Sie den Verbose-Parameter und den Berichtsparameter jederzeit einfügen, wenn Sie Test-CsComputer ausführen. Der Verbose-Parameter bietet eine etwas detailliertere Ausgabe auf dem Bildschirm, während das Cmdlet ausgeführt wird. Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsComputer generierte HTML-Datei angeben. Wenn Sie den Berichtsparameter nicht angeben, wird die HTML-Datei automatisch in Ihrem Benutzerordner gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-AD34-c54ff3ed361f. html.

Der folgende Beispielbefehl führt Test-CsComputer aus und speichert die Ausgabe in einer Datei mit dem Namen C\\:\\Logs ComputerTest. html:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Aufgrund der Anzahl der Überprüfungs Prüfungen, die durchgeführt werden, wird in Test-CsComputer kein einfaches ja zurückgemeldet, **der Test war erfolgreich** oder **Nein, der Test ist fehlgeschlagen**. Stattdessen müssen Sie die generierte HTML-Datei anzeigen, indem Sie Internet Explorer verwenden, um den Erfolg oder Misserfolg jedes Tests zu ermitteln.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsComputer möglicherweise fehlschlägt:

  - Der Testcomputer ist möglicherweise nicht für die Verwendung mit lync Server aktiviert. Dies kann auftreten, wenn sich die lync Server-Dienste oder Serverrollen auf dem Computer geändert haben und das Cmdlet Enable-CsComputer nicht ausgeführt wurde. Führen Sie den folgenden Befehl aus, um dieses Problem zu beheben:
    
        Enable-CsComputer

  - Die Replikation ist auf dem Testcomputer möglicherweise nicht auf dem neuesten Stand. Sie können den aktuellen Replikationsstatus für einen Computer überprüfen, indem Sie das Cmdlet "Get-CsManagementStoreReplicationStatus" ausführen:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Wenn der Replikationsstatus nicht auf dem neuesten Stand ist, können Sie die Replikation manuell erzwingen, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Möglicherweise muss die Topologie aktiviert sein. Wenn Sie die lync Server-Topologie ändern (Änderungen, die sich auf den lokalen Computer auswirken könnten), müssen Sie die neue Topologie aktivieren. Sie können die Topologie jederzeit aktivieren, indem Sie den folgenden Befehl ausführen:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

