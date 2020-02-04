---
title: 'Lync Server 2013: Konferenzen'
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
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Konferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Mit Unified Conferencing in lync Server 2013 können Benutzer zusammenarbeiten, Informationen austauschen und ihre Bemühungen in Echtzeit koordinieren. Alle Ihre Benutzer können die gesamte Bandbreite an spontaner Zusammenarbeit, geplanten Besprechungen und Besprechungstools verwenden. Funktionen für Sprach-und Videokonferenzen können von jedem Ort mit einer Internet Verbindung verwendet werden, und Benutzer, die sich nicht an einem Computer befinden, können an Audiokonferenzen teilnehmen, indem Sie sich mit einem PSTN-Telefon (Public Switched Telephone Network) einwählen.

In Outlook integrierte Besprechungstools ermöglichen es den Organisatoren, eine Besprechung zu planen oder eine spontane Konferenz mit nur einem Mausklick zu starten, und es ist auch für Teilnehmer genauso einfach, teilzunehmen. Ein WebClient erweitert Rich-Konferenzfeatures auf Teilnehmer, die nicht die Desktop Version von lync ausführen.

<div>

## <a name="audio-and-video-conferencing"></a>Audio- und Videokonferenzen

Lync Server bietet eine Benutzeroberfläche, die für die Benutzer herkömmlicher Audio Bridge-Dienste wie PSTN-Einwahldienste mit Befehlen zur Anrufsteuerung mit Tonwahl vertraut ist. Gleichzeitig beinhaltet Sie leistungsfähige Planungs-, Verbindungs-und Verwaltungsfunktionen, die nur mit einer integrierten Unified Communications-Plattform zur Verfügung stehen.

Mit nur einem Mausklick können Benutzer eine Besprechung aus Outlook planen. Details wie Besprechungszeit, Ort und Teilnehmer folgen der vertrauten Outlook-Vorlage. Darüber hinaus werden Konferenzanruf spezifische Informationen wie Einwahlnummer, Besprechungs-IDs und PIN-Erinnerung (persönliche Identifikationsnummer) automatisch ausgefüllt.

Um sicherzustellen, dass nur autorisierte Personen an einem Anruf teilnehmen, bietet lync Server mehrere Authentifizierungsstufen für Teilnehmer. Benutzer, die mit lync teilnehmen, werden bereits von den Active Directory-Domänendiensten authentifiziert und müssen keine PIN, keinen Passcode oder keine Besprechungs-ID eingeben.

Lync vereinfacht die Videokonferenz-Benutzererfahrung, indem es Video in den Unified Client einbindet, damit die Planung einer Besprechung mit Video oder die spontane Weiterleitung an Videos nahtlos und einfach ist.

Mit lync Server ist es einfach, mit nur einem Mausklick Video zu einem Standard-Telefonanruf hinzuzufügen. Wenn in einem Videoanruf oder einer Konferenz mehrere Teilnehmer vorhanden sind, kann jeder Benutzer Video von bis zu fünf anderen Benutzern gleichzeitig sehen, oder ein Referent kann nur eine Videoquelle auswählen, die nur von jedem angezeigt werden soll.

HD-Video (Auflösung 1270 x 720; Seitenverhältnis 16:9) und VGA-Video (Auflösung 640 x 480; Seitenverhältnis 4:3) werden für Peer-to-Peer-Anrufe zwischen Benutzern unterstützt, die lync auf Highend-Computern ausführen. Die Auflösung, die von jedem Teilnehmer in einer einzelnen Unterhaltung angezeigt wird, kann je nach den Videofunktionen der jeweiligen Hardware des Benutzers unterschiedlich sein.

IT-Administratoren können abhängig von der Computerfunktion, der Netzwerkbandbreite und dem vorhanden sein einer Kamera, die die erforderliche Auflösung liefern kann, Richtlinien festlegen, um HD-oder VGA-Video auf Clients zu beschränken oder zu deaktivieren. Diese Richtlinien werden durch die in-Band-Bereitstellung erzwungen.

</div>

<div>

## <a name="web-conferencing"></a>Webkonferenzen

Lync Server integriert Konferenz Freigabefeatures wie Desktop, Anwendung, Anlage, Whiteboard, Poll und PowerPoint in die optimierte lync-Version. In Kombination mit Audio-oder Videokonferenzen entsteht eine äußerst immersive und kollaborative Sitzung, die einfach zu vereinfachen ist.

Zur Verbesserung der allgemeinen Benutzerfreundlichkeit von Benutzern, die PowerPoint-Präsentationen präsentieren oder anzeigen, verwendet lync Server 2013 Office Web Apps zur Behandlung von PowerPoint-Präsentationen. Benutzer können ein Bild freigeben oder Text mithilfe eines Whiteboards in der lync-Besprechung kopieren und einfügen. Referenten können Umfragen in der lync-Besprechung durchführen, um Feedback von den Teilnehmern anzufordern.

Die Desktopfreigabe ermöglicht es Referenten, visuelle Elemente, Anwendungen, Webseiten, Dokumente, Software oder einen Teil Ihrer Desktops an Remote-Teilnehmer in Echtzeit zu übertragen, direkt von lync aus. Teilnehmer können mit Mausbewegungen und Tastatureingaben folgen. Referenten können auswählen, ob Sie den gesamten Bildschirm oder nur einen Teil freigeben möchten. Durch die Freigabe Ihrer Desktops können Referenten in interaktiven Produkt-oder Software-Demos von jedem Ort aus mit Ihren Zielgruppen kommunizieren.

Die Anwendungsfreigabe ermöglicht es Referenten, die Steuerung von Software auf ihren Desktops freizugeben, ohne das Feedback von Teilnehmern oder Text Fragen aus den Augen zu verlieren. Referenten können die Steuerung der Anwendung auch an Besprechungsteilnehmer delegieren.

</div>

<div>

## <a name="dial-in-conferencing"></a>Einwahlkonferenzen

Für Benutzer, die keinen Personal Computer verwenden, stehen verschiedene Methoden für die Teilnahme an einem lync Server-Konferenzanruf zur Verfügung. Ein PSTN-Benutzer kann eine Zugriffsnummer wählen, auf die Besprechungs Brücke zugreifen und dann die Besprechungs-ID eingeben. Für sicherere Besprechungen kann der Benutzer auch dazu aufgefordert werden, seine PIN einzugeben, um sich bei Active Directory zu authentifizieren. Lync Server unterstützt auch lync Phone Edition-Geräte, bei denen es sich um eigenständige IP-Telefongeräte handelt, die von Microsoft-Partnern bereitgestellt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

