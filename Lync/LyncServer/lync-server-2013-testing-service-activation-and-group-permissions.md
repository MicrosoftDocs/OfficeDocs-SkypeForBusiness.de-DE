---
title: 'Lync Server 2013: Testen der Dienstaktivierung und Gruppen Berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef22928f9506c4ec67acd3de6bad80274f8c0f12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Testen der Dienstaktivierung und Gruppen Berechtigungen in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTopology-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsTopology können Sie überprüfen, ob lync Server 2013 in einem globalen Bereich ordnungsgemäß funktioniert. Standardmäßig überprüft das Cmdlet Ihre gesamte lync Server-Infrastruktur, überprüft, ob die erforderlichen Dienste ausgeführt werden und dass die entsprechenden Berechtigungen für diese Dienste und für die universellen Sicherheitsgruppen festgesetzt werden, die bei der Installation von lync Server erstellt werden. .

Zusätzlich zur Überprüfung der Gültigkeit der lync Server-Installation können Sie mit Test-CsTopology auch die Gültigkeit eines bestimmten Diensts überprüfen. Dieser Befehl überprüft beispielsweise den Zustand des A/V-Konferenzservers im Pool ATL-CS-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Standardmäßig werden in Test-CsTopology nur sehr wenige Ausgaben auf dem Bildschirm angezeigt. Stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben. Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsTopology generierte HTML-Datei angeben. Wenn Sie den Berichtsparameter nicht angeben, wird die HTML-Datei automatisch in Ihrem Benutzerordner gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-AD34-c54ff3ed361f. html.

Der folgende Beispielbefehl führt Test-CsTopology aus und speichert die Ausgabe in einer Datei mit dem Namen C\\:\\Logs ComputerTest. html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Im Gegensatz zu den meisten Test-Cmdlets meldet Test-CsTopology Erfolg oder Fehler zurück. Dies ist teilweise auf die große Anzahl von Verifizierungs Prüfungen zurückzuführen, die das Cmdlet bei jeder Ausführung vornehmen muss. Stattdessen werden Daten in einem HTML-Bericht gespeichert, der dann mithilfe von Internet Explorer angezeigt werden kann.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsTopology möglicherweise fehlschlägt:

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

