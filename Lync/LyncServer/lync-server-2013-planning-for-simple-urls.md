---
title: 'Lync Server 2013: Planung für einfache URLs'
TOCTitle: Planung für einfache URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398287(v=OCS.15)
ms:contentKeyID: 49293403
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planung für einfache URLs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-12-11_

Einfache URLs vereinfachen den Benutzerbeitritt zu Besprechungen und erleichtern Administratoren den Zugriff auf die Lync Server-Verwaltungstools.

Lync Server unterstützt drei einfache URLs:

  - **Meet** - Dient als Basis-URL für alle Konferenzen, die am Standort oder in der Organisation abgehalten werden. Ein Beispiel für eine einfache Meet-URL ist "https://meet.contoso.com". Ein konkreter Besprechungs-URL könnte "https://meet.contoso.com/ *Benutzername* /7322994" lauten.
    
    Mit der einfachen Meet-URL sind Links für den Besprechungsbeitritt einfach zu verstehen, leicht zu kommunizieren und zu verteilen.

  - **Dialin** - Ermöglicht den Zugriff auf die Webseite mit den Einstellungen für eine Einwahlkonferenz. Auf dieser Seite werden die Konferenzeinwahlnummern mit den verfügbaren Sprachen, zugewiesene Konferenzinformationen (d. h. für Besprechungen, die nicht geplant werden müssen) und die in einer Konferenz verfügbare DTMF-Steuerelemente angezeigt. Darüber hinaus können Benutzer auf dieser Seite ihre persönliche Identifikationsnummer (PIN) sowie zugewiesene Konferenzinformationen verwalten. Die einfache URL für die Einwahl ist in allen Besprechungseinladungen enthalten, sodass Benutzer Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. Ein Beispiel für eine einfache URL für die Einwahl lautet "https://dialin.contoso.com".

  - **Admin** - Bietet schnellen Zugriff auf die Lync Server-Systemsteuerung. Ein Administrator kann von einem beliebigen Computer innerhalb der Unternehmensfirewall aus die Lync Server-Systemsteuerung öffnen, indem er die einfache Admin-URL in einen Browser eingibt. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. Ein Beispiel für eine einfache Admin-URL lautet "https://admin.contoso.com".

## Bereich einer einfachen URL

Sie können Ihre einfachen URLs auf globaler Ebene konfigurieren oder unterschiedliche einfache URLs für jeden zentralen Standort in Ihrer Organisation angeben. Wenn sowohl eine globale einfache URL als auch eine einfache URL für einen Standort angegeben wird, hat die einfache URL für den Standort Vorrang.

In den meisten Fällen wird empfohlen, einfache URLs nur auf globaler Ebene festzulegen, sodass sich die einfache URL für Besprechungen nicht ändert, wenn ein Benutzer von einem Standort an einen anderen wechselt. Eine Ausnahme stellen Organisationen dar, die unterschiedliche Telefonnummern für Einwahlbenutzer an unterschiedlichen Standorten verwenden. Beachten Sie Folgendes: Wenn Sie eine einfache URL (beispielsweise die einfache URL für die Einwahl) als einfache URL auf Standortebene festlegen, müssen Sie auch die weiteren einfachen URLs für diesen Standort auf Standortebene konfigurieren.

Sie können globale einfache URLs im Topologie-Generator festlegen. Zum Festlegen einer einfachen URL auf Standortebene müssen Sie das Cmdlet "Set-CsSimpleURLConfiguration" verwenden.

## Benennen von einfachen URLs

Es gibt drei empfohlene Optionen für die Benennung einfacher URLs. Die Auswahl der Benennungsoption hat Auswirkungen darauf, wie Sie Ihre DNS-A-Einträge und Zertifikate zur Unterstützung einfacher URLs einrichten. Bei jeder Option müssen Sie eine einfache URL für Besprechungen (Meet) für jede SIP-Domäne in Ihrer Organisation konfigurieren. Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL - unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Sie benötigen innerhalb der Organisation immer nur eine einfache URL für die Einwahl (Dial) und eine einfache Admin-URL - unabhängig davon, wie viele SIP-Domänen Sie verwenden.

Ausführliche Informationen zu den erforderlichen DNS-A-Einträgen und Zertifikaten finden Sie unter [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) und [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Bei Option 1 erstellen Sie einen neue SIP-Domänennamen für jede einfache URL.

Wenn Sie sich für diese Option entscheiden, benötigen Sie einen separaten DNS-A-Eintrag für jede einfache URL, und jeder einfache Meet-URL muss in Ihren Zertifikaten benannt sein.

### Benennung einfacher URLs - Option 1

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
<td><p>Meet</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com usw. (eine URL für jede SIP-Domäne in Ihrer Organisation)</p></td>
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


Bei Option 2 basieren die einfachen URLs auf dem Domänennamen "lync.contoso.com". Daher benötigen Sie nur einen DNS-A-Eintrag, der alle drei Arten von einfachen URLs unterstützt. Dieser DNS-A-Eintrag referenziert "lync.contoso.com". Zusätzlich benötigen Sie weiterhin separate DNS-A-Einträge für weitere SIP-Domänen in Ihrer Organisation.

### Benennung einfacher URLs - Option 2

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
<td><p>Meet</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet usw. (eine URL für jede SIP-Domäne in Ihrer Organisation)</p></td>
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


Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs für Besprechungen (Meet) zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten.

### Benennung einfacher URLs - Option 3

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
<td><p>Meet</p></td>
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


## Benennung einfacher URLs und Überprüfungsregeln

Der Topologie-Generator und die Lync Server-Verwaltungsshell-Cmdlets erzwingen verschiedene Überprüfungsregeln für Ihre einfachen URLs. Sie müssen einfache URLs für Besprechungen und Einwahl angeben, die Festlegung einer einfachen Admin-URL ist jedoch optional. Jede SIP-Domäne muss über eine separate einfache URL für Besprechungen (Meet) verfügen, Sie benötigen jedoch nur eine einfache URL für die Einwahl (Dialin) und eine einfache Admin-URL für die gesamte Organisation.

Jede einfache URL in Ihrer Organisation muss einen eindeutigen Namen aufweisen und darf kein Präfix einer anderen einfachen URL sein (beispielsweise können Sie nicht "lync.contoso.com/Meet" als einfache Meet-URL und "lync/contoso.com/Meet/Dialin" als einfache URL für die Einwahl verwenden). Die Namen einfacher URLs dürfen weder den FQDN eines Pools noch Portinformationen enthalten (beispielsweise ist "https://FQDN:88/meet" unzulässig). Alle einfachen URLs müssen mit dem Präfix "https://" beginnen.

Einfache URLs können ausschließlich alphanumerische Zeichen enthalten - a-z, A-Z, 0-9 und Punkt (.). Wenn Sie andere Zeichen verwenden, funktioniert die einfache URL möglicherweise nicht wie erwartet.

## Ändern von einfachen URLs nach der Bereitstellung

Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge und Zertifikate für einfache URLs bewusst sein. Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Beispielsweise führt eine Änderung von "https://lync.contoso.com/Meet" in "https://meet.contoso.com" zu einer Änderung der Basis-URL von "lync.contoso.com" in "meet.contoso.com", sodass auch die DNS-Einträge und Zertifikate zum Verweis auf "meet.contoso.com" geändert werden müssen. Wenn Sie die einfache URL von "https://lync.contoso.com/Meet" in "https://lync.contoso.com/Meetings" ändern, ändert sich die Basis-URL "lync.contoso.com" nicht, und eine Änderung der DNS-Einträge und Zertifikate ist nicht erforderlich.

Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet **Enable-CsComputer** auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## Siehe auch

#### Konzepte

[DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

