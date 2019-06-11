---
title: 'Lync Server 2013: Überprüfen der lync Server 2013-Serverzertifikate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Überprüfen der lync Server 2013-Serverzertifikate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-01_


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
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Get-CsCertificate verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Get-CsCertificate können Sie Informationen zu jedem ihrer lync Server-Zertifikate abrufen. Dies ist besonders wichtig, da Zertifikate ein integriertes Ablaufdatum aufweisen. So verfallen in der Regel privat ausgestellte Zertifikate nach 12 Monaten. Wenn eines ihrer lync Server-Zertifikate abläuft, gehen die zugehörigen Funktionen verloren, bis das Zertifikat erneuert oder ersetzt wurde.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Wenn Sie Informationen zu den einzelnen lync Server-Zertifikaten zurückgeben möchten, führen Sie einfach den folgenden Befehl aus:

`Get-CsCertificate`

Alternativ können Sie die Rückgabe Zertifikatinformationen auf Grundlage des Ablaufdatums filtern. Mit diesem Befehl werden beispielsweise die zurückgegebenen Daten auf Zertifikate begrenzt, die ablaufen (können nach) 1. Juni 2014 nicht verwendet werden:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Weitere Informationen finden Sie in der Hilfedokumentation für das Cmdlet Get-CsCertificate.

Beachten Sie, dass das Cmdlet Test-CsCertificateConfiguration zwar vorhanden ist, aber für Administratoren nicht sehr hilfreich ist. (Stattdessen wird dieses Cmdlet in erster Linie vom Zertifikat-Assistenten verwendet.) Obwohl das Cmdlet funktioniert, sind die zurückgegebenen Informationen von minimalem Wert, wie im folgenden Ausgabebeispiel gezeigt:

Fingerabdruck Verwendung

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107-Standard

</div>

<div>

## <a name="reviewing-the-output"></a>Überprüfen der Ausgabe

Das Cmdlet "Get-CsCertificate" gibt für jedes Ihrer lync Server-Zertifikate Informationen ähnlich der folgenden zurück:

Emittent: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 Uhr

NotBefore: 1/2/2014 12:49:37 pm

Seriennummer: 611BB01200000000000C

Betreff: CN = LYNC-SE.fabrikam.com

AlternativeNames: {SIP.fabrikam.com, LYNC-SE.fabrikam.com,

Meet.fabrikam.com, admin.fabrikam.com...}

Daumenabdruck: A9D51A2911C74FABFF7F2A8A994B20857D399107

Verwendung: Standard

In der Regel beziehen sich die wichtigsten Probleme im Zusammenhang mit lync Server-Zertifikaten auf Datums-und Uhrzeitangaben, beispielsweise wenn Zertifikate wirksam werden (NotBefore) oder wenn Sie ablaufen (NotAfter). Da diese Datums-und Uhrzeitangaben so wichtig sind, möchten Sie möglicherweise die zurückgegebenen Daten auf Informationen wie die Zertifikatverwendung, die Seriennummer des Zertifikats und das Ablaufdatum des Zertifikats einschränken. Anschließend können Sie alle Zertifikate schnell überprüfen und ablaufen. Wenn Sie nur diese Informationen zurückgeben möchten, verwenden Sie den Befehl zusammen mit den folgenden Optionen:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Dieser Befehl gibt Daten ähnlich der folgenden zurück, wobei die Zertifikate in der Reihenfolgeihres Ablaufdatums sortiert sind:

Verwenden von Seriennummer NotAfter

\--- ------------ --------

Standard 611BB01200000000000C 12/28/2015 3:35:41 pm

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 pm

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 Uhr

Wenn Sie Probleme mit dem Zertifikat haben, empfiehlt es sich, die für ein Zertifikat konfigurierte AlternativeNames zu überprüfen. Auf den ersten Blick scheint das ein Problem zu sein. In Abhängigkeit von der Größe des Konsolenfensters können von Get-CsCertificate möglicherweise nicht alle Namen angezeigt werden:

AlternativeNames: {SIP.fabrikam.com, LYNC.fabrikam.com,

Meet.fabrikam.com, admin. Fabrika...}

Wenn Sie alle alternativen Namen anzeigen möchten, die einem Zertifikat zugewiesen sind, verwenden Sie einen Befehl ähnlich dem folgenden:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Damit sollten alle alternativen Namen auf dem Zertifikat angezeigt werden:

sip.fabrikam.com

LYNC.fabrikam.com

Meet.fabrikam.com

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

