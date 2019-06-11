---
title: Lync Server 2013-Unterstützung für öffentliche Instant Messenger-Konnektivität
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Unterstützung für die öffentliche Instant Messenger-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Unterstützung für öffentliche Instant Messenger-Konnektivität

Dieser Artikel enthält Informationen zur Unterstützung öffentlicher Chat Verbindungen (PIC). PIC ist eine Funktion von Microsoft lync, die es Organisationen ermöglicht, ihren lync-Benutzern die Verbindung mit Benutzern bestimmter öffentlicher Instant Messaging-Dienste (im) über Ihre lync-Clients und-Identitäten zu ermöglichen.

Endbenutzer profitieren von der Möglichkeit, mit Kunden, Partnern und Anbietern zu ihren Konditionen in Verbindung zu treten. Sie profitiert von der Unterstützung eines einzelnen Echt Zeit Kommunikations Clients unter Beibehaltung der Kontroll-, Compliance-und Archivierungsfunktionen von lync. Lync – Skype-Konnektivität, [öffentlich verfügbar im Mai 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), basiert auf dem Vermächtnis, das lync/Office Communications Server (OCS)/Live Communications Server (LCS) erstmals mit PIC bei der Verbindung zu MSN/Windows Live, AOL und Yahoo eingerichtet hat.Weitere Informationen zur lync-Skype-Konnektivität finden Sie in der [lync-Skype-Konnektivität](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx). Föderation mit Windows Live, AOL und Yahoo sind jeweils auf einem Weg zum Ende des Lebenszyklus.Auf dieser Seite wird der Status der einzelnen Dienste dokumentiert.

Um PIC verwenden zu können, mussten Kunden den Dienst für jeden öffentlichen Chatdienst Anbieter aktivieren. Die Voraussetzungen und Einzelheiten dazu hängen vom Chatdienst Anbieter und dem zugrunde liegenden Lizenzierungsprogramm des Kunden ab.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft hat Windows Live Messenger und Skype zusammengebracht. Im April 2013 wurden Messenger-Benutzer bei der Anmeldung zu Skype migriert. Lync-Kunden, die sich auf den Verbund mit Messenger verlassen, können weiterhin mit Ihren Messenger-Kontakten kommunizieren, auch wenn diese Kontakte auf Skype aktualisiert haben. Es gibt nichts, was lync-Administratoren oder lync-Endbenutzer tun müssen, um die Kontinuität des Diensts zu gewährleisten, und die Verwaltung dieser Funktion in lync bleibt die gleiche wie für die Kommunikation mit Messenger. 

Wenn Messenger-Nutzer sich bei Skype mit Ihren Microsoft-Konten (also den gleichen Anmeldeinformationen, die für Messenger verwendet werden) anmelden, führen Sie alle Ihre Messenger-Kontakte, einschließlich der Partner von lync-Kontakten, in Skype. Anwesenheits Freigabe und Instant Messaging zwischen Skype und lync sind für diese Kontakte verfügbar. 

Lync – Skype-Konnektivität – Kontakt hinzufügen, Anwesenheits Freigabe, Sofortnachrichten und Audioanrufe zwischen lync-und Skype-Benutzern – steht nun auch allen lync-Kunden zur Verfügung.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! und AOL-Chatnachrichten

Föderation mit Yahoo\! und AOL sind sowohl auf dem Weg zum Ende der Zeit für Kunden von lync (und Office Communications Server). Die Möglichkeit von Microsoft, diese Dienste bereitzustellen, wurde von Yahoo unterstützt.\! und AOL, und die zugrunde liegenden Vereinbarungen dieser beiden werden abgewickelt. Für Yahoo\! und AOL wird der Service bis Juni 2014 fortgesetzt.

  - **Yahoo** -Service wird bis Juni 2014 fortgesetzt, und Kunden müssen weiterhin mit der Microsoft lync Public Chat-Benutzerabonnementlizenz ("PIC USL") lizenziert werden.Ab dem 1. September steht 2012, die PIC USL, nicht mehr zum Kauf für neue oder erneuernde Vereinbarungen zur Verfügung.Kunden mit Lizenzen, die vor diesem Datum erworben wurden, können weiterhin mit Yahoo zusammenarbeiten.\! bis zum vorherigen Datum des Diensts oder nach Ablauf der Lizenz.Lesen Sie [die Ankündigung](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) im lync-Teamblog.Kunden, die über PIC-Lizenzen für Vereinbarungen verfügen, die sich über die letzten 30. Juni-2014 erstrecken, erhalten ein Guthaben im Verhältnis zur Höhe der Zahlungen, die den Zeitraum nach dem 30. Juni 2014 betragen.

  - **AOL** – am 30. Juni 2014 steht lyncs Chat-Konnektivität ("PIC") nicht mehr zur Verfügung.Um die Kunden-Unterbrechung zu begrenzen, wenn der Service endet, haben wir die Bereitstellung zusätzlicher Kunden Domänen eingestellt. Bis zum 30. Juni 2014 müssen Kunden nichts Unternehmen, um die Föderations Kommunikation mit AIM weiter zu unterstützen. Über diesen Termin hinaus (oder für Kunden, die in der Zwischenzeit zusätzliche Domänen bereitstellen möchten), steht ein Ersatzdienst direkt bei AOL zur Verfügung. Weitere Informationen zum neuen Dienst von AOL finden Sie unter [Einrichten der direkten Föderation mit AIM](http://aimenterprise.aol.com/pic.php)  (öffnet eine neue Seite auf AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Zusammenfassung des öffentlichen Chat-Anbieters

Die folgende Tabelle enthält eine Zusammenfassung der öffentlichen Chat Dienstanbieter, der Verbundfunktionen mit lync und den Lizenzierungsanforderungen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Öffentlicher Chatdienst Anbieter</th>
<th>Verbundfunktionen</th>
<th>Lizenzierungsanforderungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Chat, Anwesenheit, Audio</p></td>
<td><p>Lync Server-Client Zugriffs Lizenzen, lync Online Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Chat, Anwesenheit, Audio/Video</p></td>
<td><p>Lync Server-Client Zugriffs Lizenzen (unterstützt, solange WLM im Markt ist)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Chat, Anwesenheitsstatus</p></td>
<td><p>Lync Server-Client Zugriffs Lizenzen; wird bis Juni 2014 für bestehende Kunden unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Chat, Anwesenheitsstatus</p></td>
<td><p>Erfordert zusätzlich zu den lync Server-Client Zugriffs Lizenzen zusätzliche Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL"). Ab der 2012-Preisliste vom September steht die PIC-USL nicht mehr zum Kauf zur Verfügung. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum am 30. Juni 2014 beendet hat.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

