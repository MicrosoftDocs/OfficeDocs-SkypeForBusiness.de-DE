---
title: 'Lync Server 2013: Testen von lync Server Diensten'
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
ms.openlocfilehash: cd9f2924d2f66e27e3893ccca0502915ee8a3e97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Testen von lync Server Diensten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-05_


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
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsComputer verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit Test-CsComputer wird der Status aller auf dem lokalen Computer ausgeführten lync Server 2013 Dienste überprüft. (Test-CsComputer kann nur lokal ausgeführt werden, kann nicht von einer Remoteinstanz von Windows PowerShell ausgeführt werden.) Das Cmdlet prüft außerdem, ob die entsprechenden Firewall-Ports auf dem Computer geöffnet sind, und legt fest, ob die Active Directory Gruppen, die beim Installieren von lync Server 2013 erstellt wurden, zu den entsprechenden lokalen Gruppen hinzugefügt wurden. Beispielsweise prüft Test-CsComputer, ob die Active Directory Gruppe RTCUniversalUserAdmins der Gruppe Administratoren hinzugefügt wurde.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsComputer kann nur auf dem lokalen Computer ausgeführt werden, und Sie können Test-CsComputer nicht von einer Remoteinstanz von Windows PowerShell aus aufrufen. Standardmäßig zeigt Test-CsComputer sehr wenig Ausgabe auf dem Bildschirm an, stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben. Aus diesem Grund wird empfohlen, dass Sie den Verbose-Parameter und den Report-Parameter immer dann einbeziehen, wenn Sie Test-CsComputer ausführen. Der Verbose-Parameter stellt eine etwas detailliertere Ausgabe auf dem Bildschirm bereit, während das Cmdlet ausgeführt wird. Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsComputer generierte HTML-Datei angeben. Wenn Sie den Parameter "Report" nicht angeben, wird die HTML-Datei automatisch im Ordner "Users" gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-AD34-c54ff3ed361f. html.

Im folgenden Beispielbefehl wird Test-CsComputer ausgeführt, und die Ausgabe wird in einer Datei mit dem Namen\\C\\: Logs ComputerTest. html gespeichert:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Aufgrund der Anzahl der Überprüfungs Prüfungen, die durchgeführt werden, meldet Test-CsComputer nicht wieder ein einfaches **Ja, der Test ist erfolgreich** oder **Nein, der Test ist fehlgeschlagen**. Stattdessen müssen Sie die generierte HTML-Datei anzeigen, indem Sie Internet Explorer verwenden, um den Erfolg oder Misserfolg jedes Tests zu bestimmen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsComputer möglicherweise fehlschlägt:

  - Der Testcomputer ist möglicherweise nicht für die Verwendung mit lync Server aktiviert. Dies kann vorkommen, wenn sich die lync Server-Dienste oder-Server Rollen auf dem Computer geändert haben und das Cmdlet Enable-CsComputer nicht ausgeführt wurde. Führen Sie zum Beheben des Problems den folgenden Befehl aus:
    
        Enable-CsComputer

  - Die Replikation ist auf dem Testcomputer möglicherweise nicht auf dem neuesten Stand. Sie können den aktuellen Replikationsstatus für einen Computer überprüfen, indem Sie das Cmdlet Get-CsManagementStoreReplicationStatus ausführen:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Wenn der Replikationsstatus nicht auf dem neuesten Stand ist, können Sie die Replikation manuell erzwingen, indem Sie einen Befehl wie den folgenden verwenden:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Möglicherweise muss die Topologie aktiviert sein. Wenn Sie die lync Server Topologie ändern (Änderungen, die sich auf den lokalen Computer auswirken könnten), müssen Sie die neue Topologie aktivieren. Sie können die Topologie jederzeit aktivieren, indem Sie den folgenden Befehl ausführen:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

