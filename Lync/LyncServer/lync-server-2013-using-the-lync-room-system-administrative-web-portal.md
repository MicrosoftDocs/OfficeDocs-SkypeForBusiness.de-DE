---
title: 'Lync Server 2013: Verwenden des Administrator-Webportals von lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677fdd070994c8cc1f63f775ffb2569642768f0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529942"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Verwenden des Administrator-Webportals von lync Room System in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-10_

Nachdem Sie LRS auf dem Server bereitgestellt haben, können Sie den Status aller LRS-Räume überprüfen, indem Sie sich über einen Browser beim administrativen Webportal für LRS anmelden.

<div>

## <a name="sign-in"></a>Anmelden

1.  Wechseln Sie zur folgenden URL:
    
    https:// \<fe-server\> /LRS

2.  Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe LRSSupportAdminGroup hinzugefügt wurde.

![Anmeldebildschirm des lync Room-System Administrator Portals](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm des lync Room-System Administrator Portals")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Seite "Übersicht über das LRS-Verwaltungsportal"

Die Zusammenfassungsseite enthält die folgenden Informationen zu allen auf dem Server bereitgestellten LRS-Räumen:

  - - **Tag**     Der benutzerdefinierte Name, den der Administrator dem Chatroom übergibt. Das-Tag kann im Portal festgelegt werden, indem auf den Raumnamen geklickt wird.

  - **Integrität**     Der Integritätsstatus des Raums, der vom aggregierten Integritätsstatus des Raums abgeleitet wird, der auf der Seite "Raumeinstellungen" im Abschnitt "Integrität" angezeigt wird.

  - **Nächste Besprechung**     Das Datum und die Uhrzeit, zu denen die nächste Besprechung geplant ist.

  - **LRS-Version, Hersteller, Modell**     Diese Werte sind in LRS voreingestellt. Je nach Hersteller können diese Felder leer bleiben.

  - **Letzte Aktualisierung**     Zeigt an, wann die Webseite zuletzt aktualisiert wurde.

![Zusammenfassung der lync Room System-Administrator Portal-Ansicht](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Zusammenfassung der lync Room System-Administrator Portal-Ansicht")

</div>

<div>

## <a name="lrs-room-information"></a>LRS-Rauminformationen

Im Abschnitt "Rauminformationen" des Portals können Sie einzelne LRS-Räume anzeigen und konfigurieren. Es enthält vier Abschnitte: Einstellungen, Details, Problembehandlung und Integrität.

<div>

## <a name="settings"></a>Einstellungen

Im Abschnitt "Einstellungen" können Sie das Kennwort, das Raum-Tag und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst nach dem Neustart der LRS-Konsole repliziert. Es werden nur System Updateeinstellungen für lync-Raumsysteme angezeigt, die Version 15,12 und höher sind.

![Raum System-Administrator Portal-Einstellungen für lync Room-Systeme](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Raum System-Administrator Portal-Einstellungen für lync Room-Systeme")

</div>

<div>

## <a name="details"></a>Details

Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des LRS-Raums, einschließlich: der Zeitpunkt der letzten Aktualisierung; nächste Besprechung; Letzte Aktualisierungen, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mic und Rufton; Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detail Ansicht des lync Room-System Administrator Portals](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Detail Ansicht des lync Room-System Administrator Portals")

</div>

<div>

## <a name="troubleshooting"></a>Problembehandlung

Der Abschnitt Problembehandlung kann verwendet werden, um Protokolle Remote zu sammeln und Sie an einem angegebenen Speicherort zu speichern. Sie können auch die LRS-Konsole (LRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten. Geben Sie zum Sammeln von Protokollen einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die für das Konto des LRS-Computers erteilt wurden. Wenn die Protokollgröße zu groß ist, kann es bis zu 5 Minuten dauern, bis das Sammeln von Protokollen abgeschlossen ist. Wenn Sie die Seite aktualisieren, erhalten Sie den neuesten Status.

![Protokollierung des Chatroom-Administrator Portals für lync Raumsysteme](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Protokollierung des Chatroom-Administrator Portals für lync Raumsysteme")

</div>

<div>

## <a name="health"></a>Gesundheitswesen

Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf die Integrität der lync Server-Verbindung, des Audiogeräts, des Videogeräts, des Zustands der Ausfallsicherheit und des Bildschirmgeräts.

![Raum System-Administrator Portal für lync Room-Integrität](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Raum System-Administrator Portal für lync Room-Integrität")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Zusätzliche Hinweise zum administrativen Webportal

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Einstellungsänderungen werden nur angewendet, nachdem das LRS-System neu gestartet wurde.</P>
> <LI>
> <P>Wenn das Kennwort für das LRSApp-Konto abgelaufen ist, können Sie den Status der Räume nicht anzeigen. Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder aktualisieren Sie das Kennwort, wenn es sich in der Nähe des Ablaufs befindet.</P>
> <LI>
> <P>Das LRS-Verwaltungsportal wird nur für lokale Bereitstellungen unterstützt.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim administrativen Webportal anmelden?

  - Wenn Sie öffnen https://localhost/lrs , werden Sie die Anmeldeseite sehen können, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden. In diesem Fall müssen Sie sich öffnen, um https://FQDNofFEserver/lrs sich beim administrativen Webportal anzumelden.

  - Wenn sich der Computer, auf dem Sie das administrative Webportal aufrufen, in einer Arbeitsgruppe befindet, funktioniert "http://" nicht. Verwenden Sie stattdessen "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Warum wird LRS nicht im administrativen Webportal angezeigt?

  - Stellen Sie sicher, dass Sie über LRS-Konten in Ihrer Bereitstellung verfügen und dass Sie entsprechend den Bereitstellungsempfehlungen für das LRS-Verwaltungsportal erstellt wurden. Stellen Sie sicher, dass die LRS-Konten mithilfe von enable-csmeetingroom ", not enable-CsUser, auf dem lync-Server bereitgestellt werden.

  - Wenn Sie LRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des lync Server Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren LRS-Support Kontakt.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Warum kann ich den Status von LRS nicht im administrativen Webportal anzeigen?

  - Stellen Sie sicher, dass das LRSApp-Benutzerkonto SIP-aktiviert ist.

  - Wenn Sie weiterhin Probleme haben, sammeln Sie die **Trace. log** -Datei im LRS-System von D: \\ Tracing \\ LRSAdminLogs \\ , und senden Sie Sie dann an Ihren LRS-Support Kontakt.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

