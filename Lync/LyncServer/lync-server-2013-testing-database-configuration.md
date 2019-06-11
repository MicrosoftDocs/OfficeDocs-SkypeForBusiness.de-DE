---
title: 'Lync Server 2013: Testen der Datenbankkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Testen der Datenbankkonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-07-07_


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
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein und über Administrator Rechte für SQL Server verfügen.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsDatabase-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsDatabase** überprüft die Konnektivität mit einer oder mehreren lync Server 2013-Datenbanken. Beim Ausführen liest das Cmdlet **Test-CsDatabase** die lync Server-Topologie, versucht, eine Verbindung mit relevanten Datenbankenherzustellen, und gibt dann den Erfolg oder Misserfolg jedes einzelnen Versuchs zurück. Wenn eine Verbindung hergestellt werden kann, meldet das Cmdlet auch Informationen wie den Datenbanknamen, die SQL Server-Versionsinformationen und den Speicherort aller installierten Spiegeldatenbanken zurück.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Der in Beispiel 1 gezeigte Befehl überprüft die Konfiguration der zentralen Verwaltungsdatenbank.

    Test-CsDatabase -CentralManagementDatabase

Beispiel 2 überprüft alle lync Server-Datenbanken, die auf dem Computer ATL-SQL-001.litwareinc.com installiert sind.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

In Beispiel 3 wird die Überprüfung nur für die auf dem Computer ATL-SQL-001.litwareinc.com installierte Archivierungsdatenbank durchgeführt. Beachten Sie, dass der SqlInstanceName-Parameter enthalten ist, um die SQL Server-Instanz (Archinst) anzugeben, in der sich die Archivierungsdatenbank befindet.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Der in Beispiel 4 angezeigte Befehl überprüft die auf dem lokalen Computer installierten Datenbanken.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die Datenbankverbindung ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft erfolgreich als **wahr**markiert ist:

SqlServerFqdn: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion

Erfolgreich: true

SqlServerFqdn: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion

Erfolgreich: true

Wenn die Datenbank richtig konfiguriert ist, aber weiterhin verfügbar ist, wird das Feld erfolgreich als **falsch**angezeigt, und es werden weitere Warnungen und Informationen bereitgestellt:

SqlServerFqdn: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion

Erfolgreich: falsch

SqlServerFqdn: ATL-CS-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion

Erfolgreich: falsch

Warnung: bei Test-CsDatabase sind Fehler aufgetreten. Konsultieren Sie die Protokolldatei für eine

detaillierte Analyse und um sicherzustellen, dass alle Fehler (2) und Warnungen (0) behandelt werden

bevor Sie fortfahren.

Warnung: detaillierte Ergebnisse finden Sie unter

"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsDatabase** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Dieser Befehl schlägt fehl, wenn die Datenbank falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

