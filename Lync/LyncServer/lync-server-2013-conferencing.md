---
title: Lync Server 2013 Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb39a741ac26fc6edad6362ad10f2a6c244c64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Mit einheitlichen Konferenzen in lync Server 2013 können Benutzer zusammenarbeiten, Informationen austauschen und ihre Bemühungen in Echtzeit koordinieren. Alle Benutzer können die vollständige Bandbreite der Funktionen zur spontanen Zusammenarbeit und zu geplanten Besprechungen sowie die Besprechungstools nutzen. VoIP- und Videokonferenzfunktionen können an jedem Ort mit Internetverbindung eingesetzt werden, und Benutzer, denen kein Computer zur Verfügung steht, können durch Einwahl über ein Festnetztelefon (PSTN) an Audiokonferenzen teilnehmen.

In Outlook integrierte Besprechungstools ermöglichen Organisatoren das Planen einer Besprechung oder das Starten einer spontanen Konferenz mit einem einzigen Mausklick und machen es den Teilnehmern ebenso leicht, sich anzuschließen. Ein WebClient erweitert umfangreiche Konferenzfunktionen auf Teilnehmer, die nicht die Desktop Version von lync betreiben.

<div>

## <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Lync Server bietet eine Benutzeroberfläche, die Benutzern herkömmlicher Audio Bridge-Dienste vertraut ist, einschließlich PSTN-Einwahl Diensten mit Tonwahlbefehlen für die Anrufsteuerung. Gleichzeitig sind leistungsfähige Planungs-, Teilnahme- und Verwaltungsfunktionen integriert, die nur mit einer integrierten Unified Communications-Plattform verfügbar sind.

Mit einem einzigen Mausklick können Benutzer eine Besprechung in Outlook planen. Details wie Besprechungszeit, Ort und Teilnehmer befolge die vertraute Outlook-Vorlage. Außerdem werden zum Konferenzanruf gehörende Informationen (z. B. die Einwahlnummer, Besprechungs-IDs und PIN-Erinnerungen (Personal Identification Number)) automatisch mit Daten aufgefüllt.

Um sicherzustellen, dass nur die autorisierten Personen an einem Anruf teilnehmen, bietet lync Server mehrere Authentifizierungsstufen für Teilnehmer an. Benutzer, die sich mit lync anmelden, werden bereits vom Active Directory-Domänendienste authentifiziert und müssen keine PIN, keinen Passcode oder keine Besprechungs-ID eingeben.

Lync vereinfacht die Benutzeroberfläche für Videokonferenzen, indem Video in den Unified Client integriert wird, sodass das Planen einer Besprechung mit Video oder die spontane Weiterleitung an Video nahtlos und einfach ist.

Lync Server vereinfacht das Hinzufügen von Videos zu einem Standardtelefon Anruf mit nur einem Mausklick. Wenn es mehrere Teilnehmer bei einem Videoanruf oder einer Videokonferenz gibt, kann jeder Benutzer bis zu fünf andere Teilnehmer sehen, oder ein Referent legt eine einzige Videoquelle fest, die allen anderen Teilnehmern eingeblendet werden soll.

High-Definition-Video (Auflösung 1270 x 720; Seitenverhältnis 16:9) und VGA-Video (Auflösung 640 x 480; Seitenverhältnis 4:3) werden für Peer-zu-Peer-Anrufe zwischen Benutzern unterstützt, die lync auf High-End-Computern betreiben. Jedem Teilnehmer kann das Bild in einer anderen Auflösung angezeigt werden, je nach der Leistungsfähigkeit seiner Videohardware.

IT-Administratoren können Richtlinien festlegen, um High-Definition- oder VGA-Video auf Clients einzuschränken und zu deaktivieren. Dabei spielen die Computerfunktionen, die Netzwerkbandbreite und das Vorhandensein einer Kamera, die die gewünschte Auflösung bieten kann, eine Rolle. Diese Richtlinien werden durch eine In-Band-Bereitstellung durchgesetzt.

</div>

<div>

## <a name="web-conferencing"></a>Webkonferenzen

Lync Server integriert Features für die Konferenz Freigabe wie Desktop, Anwendung, Anlage, Whiteboard, Poll und PowerPoint in das optimierte lync. Zusammen mit Audio- und Videokonferenzfunktionen bietet dies Möglichkeiten zu einer optimalen Zusammenarbeit.

Um die Gesamterfahrung von Benutzern zu verbessern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office-Webanwendungen zur Behandlung von PowerPoint-Präsentationen. Benutzer können ein Bild freigeben oder Text mithilfe eines Whiteboards in der lync-Besprechung kopieren und einfügen. Referenten können Umfragen in der lync-Besprechung durchführen, um Feedback von den Teilnehmern anzufordern.

Mit der Desktopfreigabe können Referenten beliebige Grafiken, Anwendungen, Webseiten, Dokumente, Software oder einen Teil Ihrer Desktops an Remote-Teilnehmer in Echtzeit direkt von lync aus übertragen. Die Zuschauer können die Mausbewegungen und Tastatureingaben verfolgen. Referenten können ihren gesamten Bildschirm oder nur einen Teilbereich freigeben. Durch Freigabe ihres Desktops können Referenten ihren Zuhörern interaktive Produkt- oder Softwaredemos von jedem beliebigen Ort aus vorführen.

Mit der Anwendungsfreigabe können Referenten die Steuerung von Software auf ihrem Desktop freigeben, ohne das Feedback oder Textfragen von Teilnehmern aus dem Blick zu verlieren. Referenten können die Steuerung der Anwendung auch an Besprechungsteilnehmer übertragen.

</div>

<div>

## <a name="dial-in-conferencing"></a>Einwahlkonferenzen

Für Benutzer, die keinen Personal Computer verwenden, stehen verschiedene Methoden für die Teilnahme an einer lync Server-Telefonkonferenz zur Verfügung. Ein PSTN-Benutzer kann eine Zugriffsnummer wählen, auf die Besprechungs Brücke zugreifen und dann die Besprechungs-ID eingeben. Für sicherere Besprechungen kann der Benutzer auch aufgefordert werden, seine PIN zur Authentifizierung bei Active Directory einzugeben. Lync Server unterstützt auch lync Phone Edition-Geräte, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

