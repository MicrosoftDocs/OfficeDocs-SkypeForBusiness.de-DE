---
title: 'Lync Server 2013: Verwenden des Webportals zur Verwaltung des Lync-Raumsystems'
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
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Verwenden des Webportals zur Verwaltung des Lync-Raumsystems in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-10_

Nachdem Sie LRS auf dem Server bereitgestellt haben, können Sie den Status aller LRS-Räume überprüfen, indem Sie sich über einen Browser beim LRS Administrative Web Portal anmelden.

<div>

## <a name="sign-in"></a>Anmelden

1.  Navigieren Sie zu der folgenden URL:
    
    https://\<FE-Server\>/LRS

2.  Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der LRSSupportAdminGroup-Sicherheitsgruppe hinzugefügt wurde.

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Seite mit der Zusammenfassung des LRS Administrative Web Portals

Die Seite "Zusammenfassung" enthält die folgenden Informationen für alle LRS-Räume, die auf dem Server bereitgestellt werden:

  - **Markieren**   Sie den benutzerdefinierten Namen, den der Administrator dem Chatroom übergibt. Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.

  - **Integrität**   der Integritätsstatus des Raums, der vom Aggregat Status des Raums abgeleitet wird, der im Abschnitt "Gesundheit" auf der Seite "Raumeinstellungen" angezeigt wird.

  - **Als nächstes treffen**   Sie das Datum und die Uhrzeit, an dem die nächste Besprechung geplant ist.

  - **LRS-Version, Hersteller, Modell**   diese Werte sind in LRS voreingestellt. Je nach Hersteller können diese Felder auch leer sein.

  - **Letzte Aktualisierung**   zeigt den Zeitpunkt an, zu dem die Webseite zuletzt aktualisiert wurde.

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

<div>

## <a name="lrs-room-information"></a>LRS-Rauminformationen

Im Abschnitt Rauminformationen des Portals können Sie einzelne LRS-Räume anzeigen und konfigurieren. Es enthält vier Abschnitte: Einstellungen, Details, Problembehandlung und Zustand.

<div>

## <a name="settings"></a>Einstellungen

Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die LRS-Konsole neu gestartet haben. Es werden nur die Einstellungen für System Updates für lync Room-Systeme angezeigt, die Version 15,12 und höher sind.

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

<div>

## <a name="details"></a>Details

Der Abschnitt Details enthält eine schreibgeschützte Zusammenfassung der Einstellungen des LRS-Raums, einschließlich: die Uhrzeit der letzten Aktualisierung. nächste Besprechung; Letzte Updates, Wartung und Kalibrierung; Standardeinstellungen für Lautsprecher, Mikrofon und Klingelton Version SIP-URI; Anzahl der Bildschirme und Details zu jedem Bildschirm; Status und Aktivität.

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

<div>

## <a name="troubleshooting"></a>Problembehandlung

Im Abschnitt zur Problembehandlung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können auch die LRS-Konsole (LRS-Benutzeroberfläche) neu starten oder das gesamte System neu starten. Um Protokolle zu sammeln, geben Sie einen Ordnerpfad im angegebenen Format an, und stellen Sie sicher, dass der Ordner über Schreibberechtigungen verfügt, die dem LRS-Computerkonto zugewiesen sind. Bei einer sehr umfangreichen Protokollgröße kann es bis zu 5 Minuten dauern, bis der Vorgang zur Erfassung der Protokolle abgeschlossen ist. Sie erhalten den aktuellen Status, wenn Sie die Seite aktualisieren.

![Protokollierung für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Protokollierung für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

<div>

## <a name="health"></a>Integrität

Der Abschnitt "Integrität" gibt einen visuellen Hinweis auf den Zustand der lync-Server Verbindung, des Audiogeräts, des Videogeräts, des Stabilitäts Status und des Bildschirmgeräts.

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integrität für das Webportal zur Verwaltung des Lync-Raumsystems")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Weitere Hinweise zum Webportal für die Verwaltung

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Einstellungsänderungen werden erst nach einem Neustart des LRS-Systems übernommen.</P>
> <LI>
> <P>Wenn das Kennwort für das LRSApp-Konto abläuft, können Sie den Status der Räume nicht sehen. Konfigurieren Sie das Kennwort für das LRSAppuser-Konto so, dass es nie abläuft, oder achten Sie darauf, das Kennwort zu aktualisieren, wenn es in der Nähe des Ablaufs liegt.</P>
> <LI>
> <P>Das administrative LRS-Webportal wird nur für lokale Bereitstellungen unterstützt.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Warum kann ich mich nicht beim Webportal für die Verwaltung anmelden?

  - Wenn Sie öffnen https://localhost/lrs, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, können Sie sich nicht anmelden. In diesem Fall müssen Sie die Anmeldung https://FQDNofFEserver/lrs beim Administrator-Webportal öffnen.

  - Wenn sich der Computer, von dem aus Sie auf das administrative Webportal zugreifen, in einer Arbeitsgruppe befindet, kann "http://" nicht funktionieren. Verwenden Sie stattdessen "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Warum wird LRS im Administrator-Webportal nicht angezeigt?

  - Stellen Sie sicher, dass Sie über LRS-Konten in Ihrer Bereitstellung verfügen, und dass diese entsprechend den Bereitstellungsempfehlungen des LRS-Administrator Webportals erstellt werden. Stellen Sie sicher, dass die LRS-Konten mithilfe von enable-CsMeetingRoom, nicht enable-CsUser, auf dem lync-Server bereitgestellt werden.

  - Wenn Sie LRS-Konten erstellt haben und die Konten im administrativen Webportal nicht sehen können, sammeln Sie die Serverprotokolle mithilfe des lync Server-Protokollierungstools, wobei die **MeetingPortal** -Komponente ausgewählt ist, und senden Sie Sie dann an Ihren LRS-Support Kontakt.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Warum wird der Status von LRS im Administrator-Webportal nicht angezeigt?

  - Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.

  - Wenn weiterhin Probleme auftreten, sammeln Sie die Datei **Trace. log** im LRS-System von D:\\Tracing\\LRSAdminLogs\\, und senden Sie Sie an Ihren LRS-Support Kontakt.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

