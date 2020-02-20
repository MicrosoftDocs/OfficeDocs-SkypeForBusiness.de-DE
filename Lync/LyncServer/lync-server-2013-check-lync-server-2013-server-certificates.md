---
title: 'Lync Server 2013: Überprüfen der lync Server 2013-Server Zertifikate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Überprüfen lync Server 2013 Server Zertifikaten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Monatlich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Get-CsCertificate verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Get-CsCertificate können Sie Informationen zu jedem ihrer lync Server Zertifikate abrufen. Dies ist besonders wichtig, da Zertifikate ein integriertes Ablaufdatum aufweisen. Beispielsweise laufen privat ausgestellte Zertifikate in der Regel nach 12 Monaten ab. Wenn eines ihrer lync Server Zertifikate abläuft, verlieren Sie die zugehörige Funktionalität, bis das Zertifikat erneuert oder ersetzt wird.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Wenn Sie Informationen zu den einzelnen lync Server Zertifikaten zurückgeben möchten, führen Sie den folgenden Befehl aus:

`Get-CsCertificate`

Sie können auch die Informationen zum Rückgabe Zertifikat basierend auf dem Ablaufdatum filtern. Beispielsweise schränkt dieser Befehl die zurückgegebenen Daten auf Zertifikate ein, die ablaufen (können nicht verwendet werden nach) Juni 1, 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Get-CsCertificate.

Beachten Sie, dass das Cmdlet Test-CsCertificateConfiguration zwar vorhanden ist, für Administratoren jedoch nicht besonders hilfreich ist. (Stattdessen wird das Cmdlet in erster Linie vom Zertifikat-Assistenten verwendet.) Obwohl das Cmdlet funktioniert, sind die zurückgegebenen Informationen von Minimalwert, wie im folgenden Ausgabebeispiel gezeigt:

Verwendung des Fingerabdrucks

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 Standard

</div>

<div>

## <a name="reviewing-the-output"></a>Überprüfen der Ausgabe

Das Cmdlet Get-CsCertificate gibt für jedes Ihrer lync Server-Zertifikate Informationen zurück, die den folgenden ähneln:

Aussteller: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 Uhr

NotBefore: 1/2/2014 12:49:37 Uhr

Seriennummer: 611BB01200000000000C

Betreff: CN = LYNC-SE.fabrikam.com

AlternativeNames: {SIP.fabrikam.com, LYNC-SE.fabrikam.com,

Meet.fabrikam.com, admin.fabrikam.com...}

Fingerabdruck: A9D51A2911C74FABFF7F2A8A994B20857D399107

Verwendung: Standard

In der Regel beinhalten die häufigsten Probleme bei lync Server Zertifikaten Daten und Uhrzeiten, beispielsweise wenn Zertifikate wirksam werden (NotBefore) oder wenn Sie ablaufen (NotAfter). Da diese Datums-und Uhrzeitangaben so wichtig sind, können Sie die zurückgegebenen Daten auf Informationen wie die Verwendung des Zertifikats, die Seriennummer des Zertifikats und das Ablaufdatum des Zertifikats beschränken. Anschließend können Sie schnell alle Zertifikate überprüfen und ablaufen. Um nur diese Informationen zurückzugeben, verwenden Sie den Befehl zusammen mit den Optionen wie dargestellt:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Dieser Befehl gibt Daten ähnlich der folgenden zurück, wobei die Zertifikate in der Reihenfolgeihres Ablaufdatums sortiert sind:

Seriennummer NotAfter verwenden

\--- ------------ --------

Standard 611BB01200000000000C 12/28/2015 3:35:41 Uhr

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 Uhr

"Webservicesexternal" 0451B012003872651A0C 02/20/2016 7:11:58 Uhr

Wenn Sie über Zertifikatprobleme verfügen, sollten Sie die für ein Zertifikat konfigurierten AlternativeNames möglicherweise überprüfen. Auf den ersten Blick scheint dies ein Problem zu sein. In Abhängigkeit von der Größe des Konsolenfensters kann Get-CsCertificate standardmäßig nicht alle Namen anzeigen:

AlternativeNames: {SIP.fabrikam.com, LYNC.fabrikam.com,

Meet.fabrikam.com, admin. Fabrika...}

Wenn Sie alle alternativen Namen anzeigen möchten, die einem Zertifikat zugewiesen sind, verwenden Sie einen Befehl wie den folgenden:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Dadurch sollten alle alternativen Namen im Zertifikat angezeigt werden:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

