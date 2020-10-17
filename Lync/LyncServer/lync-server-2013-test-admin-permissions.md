---
title: 'Lync Server 2013: Testen der Administratorberechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1653f2287e06db71f6e971a0a4f483b810734f2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519382"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a>Testen von Administratorberechtigungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsOUPermission-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Wenn Sie lync Server 2013 1 der Aufgaben installieren, die vom Setup Programm ausgeführt wurden, gibt die RTCUniversalUserAdmins-Gruppe die Active Directory Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungs Kontakten und inetOrgPerson Personen erforderlich sind. Wenn Sie die Vererbung von Berechtigungen in Active Directory Setup deaktiviert haben, können diese Berechtigungen nicht zugewiesen werden. Daher können Mitglieder der RTCUniversalUserAdmins-Gruppe lync Server Entitäten nicht verwalten. Diese Verwaltungsprivilegien sind nur für Domänenadministratoren verfügbar.

Das Test-CsOUPermission-Cmdlet überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory Container festgelegt sind. Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Grant-CsOUPermission-](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) Cmdlet ausführen.

Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der Gruppe RTCUniversalUserAdmins Berechtigungen zuweisen können. Dieses Cmdlet kann nicht verwendet werden, um einem beliebigen Benutzer oder einer Gruppe Berechtigungen zu erteilen. Wenn Sie möchten, dass ein anderer Benutzer oder eine andere Gruppe über Benutzer Verwaltungsberechtigungen verfügt, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe RTCUniversalUserAdmins hinzufügen.

Weitere Informationen zu ou-Berechtigungen finden Sie im Artikel die [Vererbung von Berechtigungen ist für Computer, Benutzer oder inetOrgPerson-Container in lync Server 2013 deaktiviert](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das Test-CsOUPermission-Cmdlet gefolgt vom DN (Distinguished Name) des Containers und dem Typ der Berechtigungen aus, die Sie überprüfen. Mit diesem Befehl wird beispielsweise überprüft, ob die Benutzerberechtigungen für die OU ou = Redmond, DC = litwareinc, DC = com festgelegt sind:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Wenn Sie mehrere Berechtigungen mithilfe eines einzelnen Befehls überprüfen möchten, schließen Sie die in Anführungszeichen eingeschlossenen Berechtigungstypen ein, und trennen Sie diese Typen dann durch Kommas. Mit diesem Befehl werden beispielsweise Benutzer-, Computer-und Kontakt Berechtigungen überprüft:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:

Richtig

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert false zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Zum Beispiel:

Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup hinzugefügt; Allow; ReadProperty ContainerInherit Nachfolger bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "ou = Northamerica, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" sind nicht verfügbar.

False

Warnung: "Test-CsOUPermission"-Verarbeitung wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet.

Warnung: detaillierte Ergebnisse finden Sie unter "C: \\ Users \\ Admin \\ AppData \\ local \\ Temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsOUPermission fehlschlägt, bedeutet dies normalerweise, dass die angegebene Berechtigung nicht der Gruppe RTCUniversalUserAdmins zugewiesen wurde. Sie können dieses Problem beheben und die erforderlichen Berechtigungen mithilfe des Grant-CsOUPermission-Cmdlets zuweisen. Mit diesem Befehl erhalten Sie beispielsweise die OU-Berechtigungen für Benutzer, Kontakte und InetOrgPersons für die RTCUniversalUserAdmins-Gruppe:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

