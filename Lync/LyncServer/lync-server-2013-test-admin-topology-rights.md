---
title: 'Lync Server 2013: Testen der Rechte der Administrator Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5aaeef1799ee2e35746f659ce451160854a25d89
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Testen der Rechte der Administrator Topologie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Nach der anfänglichen lync Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsSetupPermission verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Standardmäßig können nur Domänenadministratoren eine lync Server Topologie aktivieren und umfangreiche Änderungen an der lync Server Infrastruktur vornehmen. Dies ist kein Problem, solange die Domänenadministratoren und die lync Server Administratoren identisch sind. In vielen Organisationen lync Server Administratoren keine Administratorrechte für die gesamte Domäne besitzen. Standardmäßig bedeutet dies, dass diese Administratoren (definiert als Mitglieder der Gruppe "RTCUniversalServerAdmins") keine Änderungen an lync Server Topologie vornehmen können. Um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Topologie-Änderungen vorzunehmen, müssen Sie mithilfe des Cmdlets [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) die erforderlichen Active Directory Berechtigungen zuweisen.

Das Cmdlet Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen, die zum Installieren von lync Server oder einer seiner Komponenten erforderlich sind, für den angegebenen Active Directory Container konfiguriert sind. Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Grant-CsSetupPermission-Cmdlet ausführen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, lync Server zu installieren und zu aktivieren.

<div>


> [!NOTE]  
> Eine detaillierte Liste der Berechtigungen, die von Grant-CsSetupPermission zugewiesen wurden, finden Sie im Blogbeitrag <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission und Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Rufen Sie das Cmdlet Test-CsSetupPermission auf, um zu bestimmen, ob Setup Berechtigungen für einen Active Directory Container zugewiesen sind. Geben Sie den Distinguished Name des Containers an, der überprüft werden soll. Mit diesem Befehl werden beispielsweise die Setup Berechtigungen für den Container ou = CsServers, DC = litwareinc, DC = com überprüft:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory Container festgelegt wurden, gibt das Cmdlet den Wert true zurück:

Wahr

Wenn Berechtigungen nicht festgelegt sind, gibt Test-CsSetupPermission den Wert false zurück. Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen wird. Zum Beispiel:

Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL\\-CS-001 RTCUniversalServerAdmins; Ermöglichen ExtendedRight; Keine Keine 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "CN = Computers, DC = litwareinc, DC = com" sind nicht verfügbar.

False

Warnung: "Test-CsSetupPermission"-Verarbeitung wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet.

Warnung: detaillierte Ergebnisse finden Sie unter "C\\: Users\\admin\\APPDATA\\local\\Temp\\Test-CsSetupPermission-1da99ba6-ABE2-45e4-8b16-dfd244763118. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Obwohl es seltene Ausnahmen gibt, wenn Test-CsSetupPermission fehlschlägt, bedeutet dies normalerweise, dass dem angegebenen Active Directory Container keine Setup Berechtigungen zugewiesen sind. Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden. Beispielsweise erteilt dieser Befehl dem Computer Container in der Domäne litwareinc.com Setup Berechtigungen:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

