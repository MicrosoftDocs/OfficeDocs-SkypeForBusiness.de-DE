---
title: 'Lync Server 2013: Testen von Administratorberechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Testen von Administratorberechtigungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Nach der ersten lync Server-Bereitstellung. Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsOUPermission-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Wenn Sie lync Server 2013 1 der Aufgaben installieren, die vom Setup-Programm durchgeführt wurden, erhält die RTCUniversalUserAdmins-Gruppe die Active Directory-Berechtigungen, die für die Verwaltung von Benutzern, Computern, Kontakten, Anwendungs Kontakten und inetOrgPerson Personen erforderlich sind. Wenn Sie die Berechtigungsvererbung in Active Directory deaktiviert haben, können diese Berechtigungen nicht zugewiesen werden. Aus diesem Grund können Mitglieder der RTCUniversalUserAdmins-Gruppe keine lync Server-Entitäten verwalten. Diese Verwaltungsprivilegien stehen nur Domänenadministratoren zur Verfügung.

Das Cmdlet Test-CsOUPermission überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory-Container festzulegen sind. Wenn diese Berechtigungen nicht gesetzt sind, können Sie dieses Problem beheben, indem Sie das Cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) ausführen.

Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der RTCUniversalUserAdmins-Gruppe Berechtigungen zuweisen kann. Sie können dieses Cmdlet nicht verwenden, um einem beliebigen Benutzer oder einer Gruppe Berechtigungen zu erteilen. Wenn Sie möchten, dass ein anderer Benutzer oder eine andere Gruppe Benutzer Verwaltungsberechtigungen hat, sollten Sie diesen Benutzer (oder die Gruppe) zur Gruppe RTCUniversalUserAdmins hinzufügen.

Weitere Informationen zu ou-Berechtigungen finden Sie im Artikel die [Vererbung von Berechtigungen ist auf Computern, Benutzern oder inetOrgPerson-Containern in lync Server 2013 deaktiviert](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festzulegen sind, führen Sie das Cmdlet Test-CsOUPermission gefolgt vom Distinguished Name des Containers und dem Typ der zu überprüfenden Berechtigungen aus. Mit diesem Befehl wird beispielsweise überprüft, ob die Benutzerberechtigungen für die OU ou = Redmond, DC = "litwareinc, DC = com festgesetzt sind:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Wenn Sie mehrere Berechtigungen mithilfe eines einzelnen Befehls überprüfen möchten, schließen Sie die einzelnen in Anführungszeichen eingeschlossenen Berechtigungstypen ein, und trennen Sie diese Typen dann durch Kommas. Mit diesem einen Befehl werden beispielsweise Benutzer-, Computer-und Kontakt Berechtigungen überprüft:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die erforderlichen Berechtigungen bereits gesetzt sind, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:

True

Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert false zurück. Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden. Sie wird in der Regel in mehrere begleitende Warnungen eingebettet. Beispiel:

Warnung: Zugriffssteuerungseintrag (ACE) ATL-CS-001\\RTCUniversalUserReadOnlyGroup hinzugefügt; ermöglichen ReadProperty ContainerInherit Nachfolger bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "ou = Northamerica, DC = ATL-CS-001\\DC =" litwareinc, DC = com "sind nicht bereit.

Falsch

Warnung: die Verarbeitung von "Test-CsOUPermission" wurde mit Warnungen abgeschlossen. "2"-Warnungen wurden während dieser Ausführung aufgezeichnet.

Warnung: detaillierte Ergebnisse finden Sie unter "C\\: Benutzer\\Administrator\\APPDATA\\local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsOUPermission fehlschlägt, bedeutet dies normalerweise, dass die angegebene Berechtigung nicht der RTCUniversalUserAdmins-Gruppe zugewiesen wurde. Mithilfe des Cmdlets Grant-CsOUPermission können Sie dieses Problem beheben und die erforderlichen Berechtigungen zuweisen. Dieser Befehl gibt beispielsweise ou-Berechtigungen für Benutzer, Kontakte und InetOrgPersons an die RTCUniversalUserAdmins-Gruppe:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

