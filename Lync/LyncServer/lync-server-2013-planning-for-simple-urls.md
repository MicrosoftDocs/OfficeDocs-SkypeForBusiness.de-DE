---
title: 'Lync Server 2013: Planung für einfache URLs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>Planung für einfache URLs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-12-11_

Durch einfache URLs können Sie Ihren Benutzern die Teilnahme an Besprechungen erleichtern und die Verwaltung von lync Server-Verwaltungstools für Ihre Administratoren vereinfachen.

Lync Server unterstützt drei einfache URLs:

  - **Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet. Ein Beispiel für eine einfache URL für Besprechungen ist https://meet.contoso.com. Eine URL für eine bestimmte Besprechung kann https://meet.contoso.com/ *username*/7322994 sein.
    
    Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen.

  - **Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen. Auf dieser Seite werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen angezeigt, Konferenz Informationen zugewiesen (für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung der persönlichen Identifikationsnummer ( PIN) und zugewiesene Konferenz Informationen. Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können. Ein Beispiel für die einfache Dial-in-URL https://dialin.contoso.comist.

  - Der **Administrator** ermöglicht den schnellen Zugriff auf die lync Server-Systemsteuerung. Von einem beliebigen Computer innerhalb der Firewalls Ihrer Organisation kann ein Administrator die lync Server-Systemsteuerung öffnen, indem er die einfache Administrator-URL in einen Browser eingibt. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. Ein Beispiel für die einfache Administrator-URL isthttps://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>Einfacher URL-Bereich

Sie können Ihre einfachen URLs so konfigurieren, dass Sie einen globalen Bereich aufweisen, oder Sie können für jede zentrale Website in Ihrer Organisation unterschiedliche einfache URLs angeben. Wenn sowohl eine einfache URL für einen globalen Bereich als auch eine einfache URL für einen Website Bereich angegeben wird, hat die einfache URL des Websitebereichs Vorrang.

In den meisten Fällen empfiehlt es sich, einfache URLs nur auf globaler Ebene festzulegen, damit die einfache URL des Benutzers nicht geändert wird, wenn Sie von einer Website zu einer anderen wechseln. Ausnahmen sind Organisationen, die unterschiedliche Telefonnummern für Einwahlbenutzer an verschiedenen Standorten verwenden müssen. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die Einwahl einfache URL) auf einer Website als einfache URL auf Websiteebene festzulegen, müssen Sie auch die anderen einfachen URLs auf dieser Website auf Websiteebene festzulegen.

<div>


> [!NOTE]  
> Wenn Sie sich für die Verwendung von einfachen URLs mit Website Bereich entscheiden, können Ihre Benutzer nicht zwischen Front-End-Pools an verschiedenen Standorten wechseln, ohne dass die Benutzer alle geplanten Besprechungen erneut planen, da sich die einfachen URLs der Besprechung zwischen Websites unterscheiden. Dazu gehören Failover-Szenarien, in denen sich Pools in Sicherungsbeziehungen auf separaten Websites befinden. Wenn Sie ein Failover zwischen Websites durchführen müssen, bei denen einfache URLs mit Website Bereich bereitgestellt werden, können Benutzer aufgrund des Bereichs für URL nicht an Ihren Besprechungen teilnehmen. Weitere Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.



</div>

Sie können globale einfache URLs im Topologie-Generator einrichten. Um eine einfache URL auf Websiteebene einzurichten, müssen Sie das Cmdlet "Satz-CsSimpleURLConfiguration" verwenden.

</div>

<div>

## <a name="naming-your-simple-urls"></a>Benennen Ihrer einfachen URLs

Es gibt drei Empfohlene Optionen für das Benennen von einfachen URLs. Welche Option Sie auswählen, hat Auswirkungen auf die Art und Weise, wie Sie Ihre DNS A-Einträge und Zertifikate einrichten, die einfache URLs unterstützen. Bei jeder Option müssen Sie eine einfache URL für jede SIP-Domäne in Ihrer Organisation konfigurieren.

Sie benötigen immer nur eine einfache URL in ihrer gesamten Organisation für die Einwahl und eine für Administratoren, unabhängig davon, wie viele SIP-Domänen Sie besitzen.

Details zu den erforderlichen DNS-A-Einträgen und-Zertifikaten finden Sie unter [DNS-Anforderungen für einfache URLs in lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) und [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

In Option 1 erstellen Sie für jede einfache URL einen neuen SIP-Domänennamen.

Wenn Sie diese Option verwenden, benötigen Sie einen separaten DNS-a-Eintrag für jede einfache URL, und jede einfache URL muss in ihren Zertifikaten benannt sein.

### <a name="simple-url-naming-option-1"></a>Einfache URL-Benennungs Option 1

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
<td><p>Treffen</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.comusw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Bei Option 2 basieren einfache URLs auf dem Domänennamen lync.contoso.com. Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs aktiviert. Dieser DNS-A-Eintrag verweist auf lync.contoso.com. Darüber hinaus benötigen Sie für andere SIP-Domänen in Ihrer Organisation weiterhin getrennte DNS-A-Einträge.

### <a name="simple-url-naming-option-2"></a>Einfache URL-Benennungs Option 2

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
<td><p>Treffen</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meetusw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


Option 3 ist am nützlichsten, wenn Sie über viele SIP-Domänen verfügen und diese getrennte einfache URLs erfüllen sollen, aber den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.

### <a name="simple-url-naming-option-3"></a>Einfache URL-Benennungs Option 3

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
<td><p>Treffen</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>Einfache URL-Benennungs-und Gültigkeitsprüfungsregeln

Der Topologie-Generator und die lync Server-Verwaltungsshell erzwingen mehrere Gültigkeitsprüfungsregeln für ihre einfachen URLs. Sie müssen einfache URLs für Meet und Dialin festlegen, die Einstellung für "Administrator" ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL-Adresse verfügen, Sie benötigen jedoch nur eine einfache Wähl-URL und eine einfache Administrator-URL für Ihre gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen haben und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie lync.contoso.com/Meet nicht als ihre einfache URL und lync.contoso.com/Meet/Dialin als Ihre Einwahl einfache URL festlegen). Einfache URL-Namen dürfen den FQDN eines Pools oder keine Portinformationen (beispielsweise https://FQDN:88/meet nicht zulässig) enthalten. Alle einfachen URLs müssen mit dem https://-Präfix beginnen.

Einfache URLs können nur alphanumerische Zeichen enthalten (also a-z, a-z, 0-9 und der Punkt (.). Wenn Sie andere Zeichen verwenden, funktionieren die einfachen URLs möglicherweise nicht erwartungsgemäß.

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>Ändern einfacher URLs nach der Bereitstellung

Wenn Sie nach der anfänglichen Bereitstellung eine einfache URL ändern, müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn sich die Basis einer einfachen URL ändert, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Wenn Sie beispielsweise https://lync.contoso.com/Meet https://meet.contoso.com die Basis-URL von lync.contoso.com in Meet.contoso.com ändern, müssen Sie die DNS-Einträge und Zertifikate so ändern, dass Sie auf Meet.contoso.com verweisen. Wenn Sie die einfache URL von https://lync.contoso.com/Meet in https://lync.contoso.com/Meetingsgeändert haben, bleibt die Basis-URL von lync.contoso.com unverändert, sodass keine DNS-oder Zertifikat Änderungen erforderlich sind.

Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie **enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

