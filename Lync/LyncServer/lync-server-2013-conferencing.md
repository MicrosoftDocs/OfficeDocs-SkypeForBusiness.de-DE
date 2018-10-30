---
title: 'Lync Server 2013: Konferenzen'
TOCTitle: Konferenzen
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg417161(v=OCS.15)
ms:contentKeyID: 49294171
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Mit den einheitlichen Konferenzfunktionen in Lync Server 2013 können Benutzer zusammenarbeiten, Informationen gemeinsam nutzen und ihre Arbeit in Echtzeit koordinieren. Alle Benutzer können die vollständige Bandbreite der Funktionen zur spontanen Zusammenarbeit und zu geplanten Besprechungen sowie die Besprechungstools nutzen. VoIP- und Videokonferenzfunktionen können an jedem Ort mit Internetverbindung eingesetzt werden, und Benutzer, denen kein Computer zur Verfügung steht, können durch Einwahl über ein Festnetztelefon (PSTN) an Audiokonferenzen teilnehmen.

Die in Outlook integrierten Besprechungstools ermöglichen Besprechungsorganisatoren die Planung von Besprechungen oder das Abhalten spontaner Besprechungen mit nur einem Klick - ebenso wie die Teilnehmer ebenfalls mit nur einem Klick einer Besprechung beitreten können. Ein Webclient dehnt die umfassenden Konferenzfunktionen auf Teilnehmer aus, die nicht die Desktopversion von Lync verwenden.

## Audio- und Videokonferenzen

Lync Server stellt eine Benutzeroberfläche bereit, die den Benutzern herkömmlicher Audiobrückendienste vertraut ist, einschließlich Festnetz-Einwahldienste mit Tonwahl-Anrufsteuerungsbefehlen. Gleichzeitig sind leistungsfähige Planungs-, Teilnahme- und Verwaltungsfunktionen integriert, die nur mit einer integrierten Unified Communications-Plattform verfügbar sind.

Mit nur einem Mausklick können Benutzer eine Besprechung von Outlook aus planen. Details, wie etwa die Besprechungszeit, der Ort und die Teilnehmer liegen in Form der vertrauten Outlook-Vorlage vor. Außerdem werden zum Konferenzanruf gehörende Informationen (z. B. die Einwahlnummer, Besprechungs-IDs und PIN-Erinnerungen (Personal Identification Number)) automatisch mit Daten aufgefüllt.

Damit sichergestellt werden kann, dass nur autorisierte Personen an einem Anruf teilnehmen, stellt Lync Server mehrere Authentifizierungsstufen für Teilnehmer zur Verfügung. Benutzer, die über Lync teilnehmen, sind bereits anhand der Active Directory-Domänendienste authentifiziert und müssen keine PIN, Kennung oder Besprechungs-ID eingeben.

Lync vereinfacht Videokonferenzen für den Benutzer durch die Integration der Videofunktion in den vereinheitlichten Client, sodass das Planen einer Videobesprechung oder das spontane Zuschalten der Videofunktion nahtlos und einfach erfolgen kann.

In Lync Server kann die Videofunktion während eines normalen Telefongesprächs ganz einfach per Mausklick zugeschaltet werden. Wenn es mehrere Teilnehmer bei einem Videoanruf oder einer Videokonferenz gibt, kann jeder Benutzer bis zu fünf andere Teilnehmer sehen, oder ein Referent legt eine einzige Videoquelle fest, die allen anderen Teilnehmern eingeblendet werden soll.

High-Definition-Video (Auflösung 1270 x 720, Seitenverhältnis 16:9) und VGA-Video (Auflösung 640 x 480, Seitenverhältnis 4:3) werden für Peer-zu-Peer-Anrufe zwischen Benutzern mit Lync auf High-End-Computern unterstützt. Jedem Teilnehmer kann das Bild in einer anderen Auflösung angezeigt werden, je nach der Leistungsfähigkeit seiner Videohardware.

IT-Administratoren können Richtlinien festlegen, um High-Definition- oder VGA-Video auf Clients einzuschränken und zu deaktivieren. Dabei spielen die Computerfunktionen, die Netzwerkbandbreite und das Vorhandensein einer Kamera, die die gewünschte Auflösung bieten kann, eine Rolle. Diese Richtlinien werden durch eine In-Band-Bereitstellung durchgesetzt.

## Webkonferenzen

Lync Server integriert Freigabefunktionen für Konferenzen (wie zum Beispiel Desktop, Anwendung, Anhang, Whiteboard, Abstimmung und PowerPoint) im wohldurchdachten Lync. Zusammen mit Audio- und Videokonferenzfunktionen bietet dies Möglichkeiten zu einer optimalen Zusammenarbeit.

Für eine optimale Benutzerfreundlichkeit greift Lync Server 2013 beim Umgang mit PowerPoint-Präsentationen auf Office Web Apps zurück. Benutzer können Bilder freigeben oder Texte über ein Whiteboard in Lync kopieren und einfügen. Referenten können in der Lync-Besprechung Abstimmungen durchführen, um Feedback von den Teilnehmern zu erhalten.

Mit der Desktopfreigabe können Referenten visuelle Informationen, Anwendungen, Webseiten, Dokumente, Software oder Teile ihrer Desktops direkt aus Lync in Echtzeit an Remoteteilnehmer rundum versenden. Die Teilnehmer können die Mausbewegungen und Tastatureingaben direkt verfolgen. Referenten können ihren gesamten Bildschirm oder nur einen Teilbereich freigeben. Durch Freigabe ihres Desktops können Referenten ihren Zuhörern interaktive Produkt- oder Softwaredemos von jedem beliebigen Ort aus vorführen.

Mit der Anwendungsfreigabe können Referenten die Steuerung von Software auf ihrem Desktop freigeben, ohne das Feedback oder Textfragen von Teilnehmern aus dem Blick zu verlieren. Referenten können die Steuerung der Anwendung auch an Besprechungsteilnehmer übertragen.

## Einwahlkonferenzen

Benutzern ohne PC stehen mehrere Möglichkeiten zur Teilnahme an einem Lync Server-basierten Konferenzanruf offen. Ein PSTN-Benutzer kann eine Zugriffsnummer wählen, auf das Konferenzsystem zugreifen und dann die Besprechungs-ID eingeben. Für sicherere Besprechungen muss der Benutzer möglicherweise auch eine PIN eingeben, um sich bei Active Directory zu authentifizieren. Lync Server unterstützt auch Lync Phone Edition-Geräte, d. h. eigenständige IP-Telefongeräte, die von Microsoft-Partnern bereitgestellt werden.

