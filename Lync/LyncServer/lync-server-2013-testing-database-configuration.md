---
title: 'Lync Server 2013: Testen der Datenbankkonfiguration'
description: 'Lync Server 2013: Testen der Datenbankkonfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560681"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>Testen der Datenbankkonfiguration in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-07_


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
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein und über Administrator Rechte für den SQL Server verfügen.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsDatabase</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsDatabase** überprüft die Konnektivität mit einer oder mehreren lync Server 2013 Datenbanken. Bei der Ausführung liest das Cmdlet **Test-CsDatabase** die lync Server Topologie, versucht, eine Verbindung mit relevanten Datenbankenherzustellen, und meldet dann den Erfolg oder das Fehlschlagen der einzelnen Versuche zurück. Wenn eine Verbindung hergestellt werden kann, meldet das Cmdlet auch Informationen wie Datenbankname, SQL Server-Version und den Ort der installierten Spiegeldatenbanken.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Der Befehl im ersten Beispiel dient zum Überprüfen der Konfiguration der zentralen Verwaltungsdatenbank.

    Test-CsDatabase -CentralManagementDatabase

In Beispiel 2 werden alle auf dem Computer ATL-SQL-001.litwareinc.com installierten lync Server Datenbanken überprüft.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

Im dritten Beispiel wird nur die auf dem Computer "atl-sql-001.litwareinc.com" installierte Archivierungsdatenbank überprüft. Beachten Sie, dass der Parameter "SqlInstanceName" verwendet wird, um die SQL Server-Instanz ("Archinst") anzugeben, in der sich die Archivierungsdatenbank befindet.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

Mit dem Befehl in Beispiel 4 werden die auf dem lokalen Computer installierten Datenbanken überprüft.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Datenbankverbindung ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Succeed-Eigenschaft mit **true**gekennzeichnet ist:

Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion

Erfolgreich: true

Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion

Erfolgreich: true

Wenn die Datenbank ordnungsgemäß konfiguriert ist, aber weiterhin verfügbar ist, wird das Feld erfolgreich als **false**angezeigt, und es werden zusätzliche Warnungen und Informationen bereitgestellt:

Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: XDS

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion

Erfolgreich: false

Sqlserverfqdn "nicht: ATL-CS-001.litwareinc.com

SqlInstanceName: RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: Lis

DataSource

SQLServerVersion :

ExpectedVersion: 3.1.1

InstalledVersion

Erfolgreich: false

Warnung: Test-CsDatabase Fehler aufgetreten. Konsultieren Sie die Protokolldatei für einen

detaillierte Analyse und sicherstellen, dass alle Fehler (2) und Warnungen (0) adressiert werden

bevor Sie fortfahren.

Warnung: detaillierte Ergebnisse finden Sie unter

"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsDatabase** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Dieser Befehl schlägt fehl, wenn die Datenbank falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-csdatabasemirrorstate "](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

