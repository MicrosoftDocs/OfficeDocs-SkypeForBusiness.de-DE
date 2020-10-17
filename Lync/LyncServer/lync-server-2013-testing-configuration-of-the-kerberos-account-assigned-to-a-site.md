---
title: Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos
description: Testen der Konfiguration des Kerberos-Kontos, das einem Standort zugewiesen ist.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560691"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Testen der Konfiguration des einem Standort zugewiesenen Kerberos-Kontos in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsKerberosAccountAssignment-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsKerberosAccountAssignment-Cmdlet können Sie sicherstellen, dass einem bestimmten Standort ein Kerberos-Konto zugeordnet ist, dass dieses Konto ordnungsgemäß konfiguriert ist und dass das Konto wie erwartet funktioniert. Bei Kerberos-Konten handelt es sich um Computerkonten, die als Authentifizierungs Prinzipal für alle Computer an einem Standort dienen können, auf dem Internet Information Server (IIS) verwendet wird. Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden die Konten als Kerberos-Konten bezeichnet, und der neue Authentifizierungsprozess wird als Kerberos-Webauthentifizierung bezeichnet. Auf diese Weise können Sie alle IIS-Server mithilfe eines einzigen Kontos verwalten.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Standardmäßig zeigt Test-CsKerberosAccountAssignment nur sehr wenig Ausgabe auf dem Bildschirm an. Stattdessen werden vom Cmdlet zurückgegebene Informationen in eine HTML-Datei geschrieben. Aus diesem Grund wird empfohlen, dass Sie den Verbose-Parameter und den Report-Parameter immer dann einbeziehen, wenn Sie Test-CsKerberosAccountAssignment ausführen. Der Verbose-Parameter stellt eine etwas detailliertere Ausgabe auf dem Bildschirm bereit, während das Cmdlet ausgeführt wird. Mit dem Parameter Report können Sie einen Dateipfad und einen Dateinamen für die von Test-CsKerberosAccountAssignment generierte HTML-Datei angeben. Wenn Sie den Parameter "Report" nicht angeben, wird die HTML-Datei automatisch im Ordner "Users" gespeichert und erhält einen ähnlichen Namen wie den folgenden: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

Sie müssen auch eine Websiteidentität angeben, wenn Sie Test-CsKerberosAccountAssignment ausführen. Kerberos-Konten werden auf Standortebene zugewiesen.

Der folgende Befehl führt Test-CsKerberosAccountAssignment aus und speichert die Ausgabe in einer Datei mit dem Namen C: \\ Logs \\KerberosTest.html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Das Test-CsKerberosAccountAssignment-Cmdlet gibt keinen einfachen Hinweis auf Erfolg oder Fehler zurück. Stattdessen müssen Sie die generierte HTML-Datei mit Internet Explorer anzeigen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsKerberosAccountAssignment Fehler auftreten können:

  - Möglicherweise haben Sie eine falsche Websiteidentität angegeben. Verwenden Sie diesen Befehl, um eine Liste gültiger Websiteidentität zurückzugeben:
    
        Get-CsSite | Select-Identity Identity
    
    Eine Websiteidentität sieht normalerweise folgendermaßen aus:
    
    Website: Redmond

  - Der angegebenen Website ist möglicherweise kein Kerberos-Konto zugewiesen. Sie können ermitteln, ob einem Standort ein Kerberos-Konto zugewiesen ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Ihr Kerberos-Konto verfügt möglicherweise über ein gültiges Kennwort. Wenn die folgende Fehlermeldung in Report angezeigt wird, müssen Sie wahrscheinlich das Kennwort für das Kerberos-Konto zurücksetzen:
    
    InvalidKerberosConfiguration: die Kerberos-Konfiguration ist ungültig.
    
    InvalidKerberosConfiguration: die Kerberos-Konfiguration auf ATL-cs001.litwareinc.com ist ungültig. Das erwartete zugewiesene Konto ist litwareinc \\ kerberostest. Stellen Sie sicher, dass das Konto nicht abgelaufen ist und dass das konfigurierte Kennwort auf dem Computer mit dem Active Directory Kennwort des Kontos übereinstimmt.
    
    Sie können das Kennwort mit dem Cmdlet " [CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) " festlegen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

