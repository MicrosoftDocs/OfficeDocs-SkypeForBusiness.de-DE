---
title: 'Lync Server 2013: Liste der KDS-Ansichten'
description: 'Lync Server 2013: Liste der KDS-Ansichten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550081"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Liste der KDS-Ansichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Ansichten bieten eine einfache Möglichkeit, auf Informationen zu den am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der KDS-Datenbank zuzugreifen. Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt die tatsächlichen KDS-Datenbanktabellen zu verwenden. Das liegt daran, dass die Datenbankansichten eher die Abwärtskompatibilität mit zukünftigen Versionen von lync Server aufrecht erhalten.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sichtname</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Client Versions-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den in einer Kommunikationssitzung verwendeten Clientsoftwareanwendungen/Geräten zurück.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu der Anzahl der von Benutzern in einer Konferenz gesendeten Nachrichten zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Ansicht "Konferenzen" in lync Server 2013</a></p></td>
<td><p>Gibt Konferenzinformationen zurück, einschließlich Startzeit, Endzeit und Konferenzorganisator.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Sitzungsdetails zu allen Konferenzsitzungen zurück, einschließlich Start- und Endzeit, Benutzer-IDs, Antwortcodes und Diagnose-IDs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den in einer Konferenz verwendeten Konferenz-URIs zurück.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">ErrorReport-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Fehlern zurück, die in einer Sitzung aufgetreten sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Filetransfers-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Dateiübertragungssitzungen zurück. Hierzu gehören der Dateiname und Angaben dazu, ob die Übertragung akzeptiert, abgelehnt oder abgebrochen wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt kombinierte Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück (jeder Konferenzbeitritt ist entsprechend mit dem Verlassen einer Konferenz gepaart).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">MCU-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Konferenzservern zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Medienansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den Medientypen zurück, die in Peer-zu-Peer-Kommunikationssitzungen verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">ProgressReport-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu beendeten Konferenzsitzungen zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Registrierungs Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Registrierungen mit lync Server zurück.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Peer-zu-Peer-Sitzungen zurück, einschließlich Telefonanrufen von VoIP zu VoIP, Chatsitzungen mit zwei Teilnehmern oder anderen Peer-zu-Peer-Kommunikationssitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Benutzeransicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu den Benutzern zurück, die an Kommunikationssitzungen teilgenommen haben.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">VoIPDetails-Ansicht in lync Server 2013</a></p></td>
<td><p>Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, an denen mindestens ein VoIP-Benutzer beteiligt war.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

