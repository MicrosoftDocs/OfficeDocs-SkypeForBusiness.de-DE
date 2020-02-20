---
title: Lync Server 2013 Unterstützung für die Verbindung mit öffentlichen Instant Messaging-Diensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c6f21e6a58b9130ab93f827f14aad4bd09cbb33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Unterstützung für die Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Unterstützung für die Verbindung mit öffentlichen Instant Messaging-Diensten

Dieser Artikel enthält Informationen zur Unterstützung von öffentlichen Instant Messaging-Verbindungen (PIC). PIC ist ein Feature von Microsoft lync, mit dem Organisationen ihre lync-Benutzer über Ihre lync-Clients und-Identitäten mit Benutzern bestimmter öffentlicher Chat Dienste (Instant Messaging) verbinden können.

Endbenutzer profitieren davon, dass Sie mit ihren Geschäftsbedingungen eine Verbindung mit Kunden, Partnern und Anbietern herstellen können. Es profitiert von der Unterstützung eines einzelnen Echt Zeit Kommunikations Clients bei gleichzeitiger Beibehaltung der Steuerungs-, Compliance-und Archivierungsfunktionen von lync. Die lync-Skype-Konnektivität, die [im Mai 2013 öffentlich verfügbar](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)ist, beruht auf dem Vermächtnis, das lync/Office Communications Server (OCS)/Live Communications Server (LCS) zunächst mit pic in Verbindung mit MSN/Windows Live, AOL und Yahoo eingerichtet hat.Weitere Informationen zur lync-Skype-Konnektivität finden Sie in der [lync-Skype-Konnektivität](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx). Partnerverbund mit Windows Live, AOL und Yahoo sind jeweils auf einem Pfad zum Ende der Lebensdauer.Auf dieser Seite wird der Status der einzelnen Dienste dokumentiert.

Für die Verwendung von PIC mussten Kunden den Dienst für jeden öffentlichen Sofortnachrichten-Dienstanbieter aktivieren. Die Anforderungen und Details für die Vorgehensweise hängen vom Chat Dienstanbieter und dem zugrunde liegenden Lizenzierungsprogramm des Kunden ab.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft hat Windows Live Messenger und Skype zusammengebracht. Im April 2013 wurden Messenger-Benutzer bei der Anmeldung zu Skype migriert. Lync-Kunden, die sich auf den Partnerverbund mit Messenger verlassen, können weiterhin mit Ihren Messenger-Kontakten kommunizieren, auch wenn diese Kontakte mit Skype aktualisiert werden. Es gibt nichts, was lync-Administratoren oder lync-Endbenutzer tun müssen, um die Kontinuität des Diensts aufrechtzuerhalten, und die Verwaltung dieser Funktion in lync bleibt dieselbe wie bei der Kommunikation mit Messenger. 

Wenn sich Messenger-Benutzer bei Skype mit Ihren Microsoft-Konten (d. h. denselben Anmeldeinformationen für Messenger) anmelden, werden Sie von allen Messenger-Kontakten – einschließlich der Partnerverbund-lync-Kontakte – in Skype eingebaut. Anwesenheits Freigabe und Chatnachrichten zwischen Skype und lync für diese Kontakte sind verfügbar. 

Lync-Skype Connectivity – Kontakt hinzufügen, Anwesenheits Freigabe, Sofortnachrichten und Audioanrufe zwischen lync-und Skype-Benutzern – steht nun auch allen lync-Kunden zur Verfügung.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! und AOL Instant Messenger

Partnerverbund mit Yahoo\! und AOL sind sowohl auf dem Weg zum End-of-Life für Kunden von lync (und Office Communications Server). Die Fähigkeit von Microsoft, jeden dieser Dienste bereitzustellen, wurde von der Unterstützung durch Yahoo abhängig gemacht.\! und AOL, und die zugrunde liegenden Vereinbarungen dieser werden abgewickelt. Für Yahoo\! und AOL wird der Dienst bis Juni 2014 fortgesetzt.

  - **Yahoo** -Service wird bis Juni 2014 fortgesetzt, und Kunden müssen weiterhin mit der Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") lizenziert werden.Seit dem 1. September 2012 ist die PIC-USL für neue oder erneuerte Verträge nicht mehr zum Kauf verfügbar.Kunden mit Lizenzen, die vor diesem Datum erworben wurden, können weiterhin mit Yahoo verbünden.\! bis zum vorherigen Datum des Dienstes oder zum Herunterfahren ihres Lizenz Ablaufs.Lesen Sie [die Ankündigung](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) im Team-Blog von lync.Kunden mit PIC-Lizenzen für Vereinbarungen, die über 30. Juni hinausgehen, 2014 erhalten einen Kredit im Verhältnis zur Höhe der Zahlungen, die den Zeitraum nach dem 30. Juni 2014 umfassen.

  - **AOL** -am 30. Juni 2014 wird der lync-Chat-Connectivity-Dienst ("PIC") nicht mehr zur Verfügung stehen.Um die Kunden Unterbrechungen zu begrenzen, wenn der Dienst beendet wird, haben wir die Einrichtung zusätzlicher Kunden Domänen eingestellt. Bis zum 30. Juni 2014 müssen Kunden nichts Unternehmen, um die Verbundkommunikation mit AIM weiter zu unterstützen. Außerhalb dieses Datums (oder für Kunden, die in der Zwischenzeit zusätzliche Domänen bereitstellen möchten), steht ein Ersatzdienst direkt in AOL zur Verfügung. Weitere Informationen zum neuen Dienst von AOL finden Sie unter [Einrichten des direkten Verbunds mit AIM](http://aimenterprise.aol.com/pic.php)  (öffnet eine neue Seite auf AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Zusammenfassung von öffentlichen Chat-Anbietern

Die folgende Tabelle enthält eine Zusammenfassung der öffentlichen Sofortnachrichten-Dienstanbieter, der Verbundfunktionen mit lync und der Lizenzierungsanforderungen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Öffentlicher Sofortnachrichten-Dienstanbieter</th>
<th>Verbundfunktionen</th>
<th>Lizenzierungsanforderungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Chat, Anwesenheit, Audio</p></td>
<td><p>Lync Server Client Zugriffs Lizenzen lync Online Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Chat, Anwesenheit, Audio/Video</p></td>
<td><p>Lync Server Client Zugriffs Lizenzen (unterstützt, solange WLM im Markt ist)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Chat, Anwesenheit</p></td>
<td><p>Lync Server Client Zugriffs Lizenzen; wird bis Juni 2014 für vorhandene Kunden unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Chat, Anwesenheit</p></td>
<td><p>Erfordert zusätzlich zu lync Server Client Zugriffs Lizenzen zusätzliche Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL"). Ab der Preisliste von September 2012 steht die PIC-USL nicht mehr zum Kauf zur Verfügung. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum am 30. Juni 2014 heruntergefahren hat.</p></td>
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

