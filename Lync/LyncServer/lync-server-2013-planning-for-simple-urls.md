---
title: 'Lync Server 2013: Planen für einfache URLs'
description: 'Lync Server 2013: Planen für einfache URLs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a7f2aaf85dafe5facba7cfd2509cfcc8812d67
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558401"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planen von einfachen URLs in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-12-11_

Einfache URLs erleichtern die Teilnahme an Besprechungen für Ihre Benutzer und erleichtern Ihnen die Verwaltung von lync Server Verwaltungstools.

Lync Server unterstützt drei einfache URLs:

  - **Meet**: Dient als Basis-URL für alle Konferenzen, die am Standort oder in der Organisation abgehalten werden. Ein Beispiel für eine einfache Meet-URL ist https://meet.contoso.com . Eine URL für eine bestimmte Besprechung ist möglicherweise https://meet.contoso.com/ *username*/7322994.
    
    Mit der einfachen Meet-URL sind Links für den Besprechungsbeitritt einfach zu verstehen, leicht zu kommunizieren und zu verteilen.

  - **Dial-in**: Ermöglicht den Zugriff auf die Webseite mit den Einstellungen für eine Einwahlkonferenz. Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (also für Besprechungen, die nicht geplant werden müssen) und DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung von persönlicher Identifikationsnummer (PIN) und zugewiesener Konferenz Informationen. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für die einfache Einwahl-URL ist https://dialin.contoso.com .

  - Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung. Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die lync Server-Systemsteuerung öffnen, indem er die einfache admin-URL in einen Browser eingibt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für die einfache admin-URL ist https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Bereich einer einfachen URL

Sie können Ihre einfachen URLs auf globaler Ebene konfigurieren oder unterschiedliche einfache URLs für jeden zentralen Standort in Ihrer Organisation angeben. Wenn sowohl eine einfache URL des globalen Bereichs als auch eine einfache URL für den Website Bereich angegeben wird, hat die einfache URL des Websitebereichs Vorrang.

In den meisten Fällen wird empfohlen, einfache URLs nur auf globaler Ebene festzulegen, sodass sich die einfache URL für Besprechungen nicht ändert, wenn ein Benutzer von einem Standort an einen anderen wechselt. Eine Ausnahme stellen Organisationen dar, die unterschiedliche Telefonnummern für Einwahlbenutzer an unterschiedlichen Standorten verwenden. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die einfache URL für die Einwahl) als einfache URL auf Standortebene festlegen, müssen Sie auch die weiteren einfachen URLs für diesen Standort auf Standortebene konfigurieren.

<div>


> [!NOTE]  
> Wenn Sie einfache URLs mit Website Bereich verwenden, können Ihre Benutzer nicht zwischen Front-End Pools an unterschiedlichen Standorten navigieren, ohne dass Benutzer alle geplanten Besprechungen Umplanen, da sich die einfachen URLs der Besprechung zwischen Websites unterscheiden. Dies umfasst Failover-Szenarien, in denen sich Pools in Sicherungsbeziehungen an unterschiedlichen Standorten befinden. Wenn Sie ein Failover zwischen Websites durchführen müssen, bei denen einfache URLs auf Websiteebene bereitgestellt werden, können Benutzer aufgrund des Bereichs für die URL nicht an Ihren Besprechungen teilnehmen. Weitere Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Sie können globale einfache URLs im Topologie-Generator festlegen. Zum Festlegen einer einfachen URL auf Standortebene müssen Sie das Cmdlet "Set-CsSimpleURLConfiguration" verwenden.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Benennen von einfachen URLs

Es gibt drei empfohlene Optionen für die Benennung einfacher URLs. Die Auswahl der Benennungsoption hat Auswirkungen darauf, wie Sie Ihre DNS-A-Einträge und Zertifikate zur Unterstützung einfacher URLs einrichten. Bei jeder Option müssen Sie eine einfache URL für Besprechungen (Meet) für jede SIP-Domäne in Ihrer Organisation konfigurieren. Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL – unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Ausführliche Informationen zu den erforderlichen DNS-A-Einträgen und-Zertifikaten finden Sie unter [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) und [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Bei Option 1 erstellen Sie einen neue SIP-Domänennamen für jede einfache URL.

Wenn Sie sich für diese Option entscheiden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL muss in Ihren Zertifikaten benannt sein.

### <a name="simple-url-naming-option-1"></a>Benennung einfacher URLs – Option 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Erfüllen</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com usw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Administrator</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Bei Option 2 basieren die einfachen URLs auf dem Domänennamen "lync.contoso.com". Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs unterstützt. Dieser DNS-A-Eintrag referenziert "lync.contoso.com". Zusätzlich benötigen Sie weiterhin separate DNS-A-Einträge für weitere SIP-Domänen in Ihrer Organisation.

### <a name="simple-url-naming-option-2"></a>Benennung einfacher URLs – Option 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Erfüllen</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet usw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrator</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs für Besprechungen (Meet) zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.

### <a name="simple-url-naming-option-3"></a>Benennung einfacher URLs – Option 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Erfüllen</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Administrator</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Benennung einfacher URLs und Überprüfungsregeln

Der Topologie-Generator und die lync Server-Verwaltungsshell-Cmdlets erzwingen mehrere Validierungsregeln für ihre einfachen URLs. Sie müssen einfache URLs für Besprechungen und Einwahl angeben, die Festlegung einer einfachen Admin-URL ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL für Besprechungen (Meet) verfügen, Sie benötigen jedoch nur eine einfache URL für die Einwahl (Dialin) und eine einfache Admin-URL für die gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen aufweisen und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie nicht "lync.contoso.com/Meet" als einfache Meet-URL und "lync/contoso.com/Meet/Dialin" als einfache URL für die Einwahl verwenden). Einfache URL-Namen dürfen nicht den FQDN eines Pools oder Portinformationen enthalten (beispielsweise https://FQDN:88/meet nicht zulässig). Alle einfachen URLs müssen mit dem Präfix "https://" beginnen.

Einfache URLs können ausschließlich alphanumerische Zeichen enthalten – a-z, A-Z, 0-9 und Punkt (.). Wenn Sie andere Zeichen verwenden, funktioniert die einfache URL möglicherweise nicht wie erwartet.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Ändern von einfachen URLs nach der Bereitstellung

Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge und Zertifikate für einfache URLs bewusst sein. Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Wenn beispielsweise von in geändert wird, wird https://lync.contoso.com/Meet https://meet.contoso.com die Basis-URL von lync.contoso.com in Meet.contoso.com geändert, sodass Sie die DNS-Einträge und Zertifikate für den Verweis auf Meet.contoso.com ändern müssen. Wenn Sie die einfache URL von in geändert haben https://lync.contoso.com/Meet https://lync.contoso.com/Meetings , bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.

Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

