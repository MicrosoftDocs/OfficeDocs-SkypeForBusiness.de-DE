---
title: Verwenden von Echtzeit-Telemetrie zur Problembehandlung bei schlechter Besprechungsqualität
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Verwenden Sie Echtzeit-Telemetrie mit Details zu Geräten, Netzwerken und Konnektivität, um Benutzerprobleme bei Microsoft Teams Besprechungen zu beheben.
ms.openlocfilehash: 09c31b7734a849740cf1b0ff5749e4d82c667faf
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518727"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Verwenden von Echtzeit-Telemetrie zur Problembehandlung bei schlechter Besprechungsqualität

In diesem Artikel wird erläutert, wie Sie Real-Time Analytics (RTA) verwenden, um Probleme mit Microsoft Teams Besprechungsqualität für einzelne Benutzer zu beheben. Sie können auf ihre Real-Time zugreifen, wenn Sie über eine der folgenden Rollen verfügen:

- Teams-Administrator
- Supportfachmann für die Teams-Kommunikation
- Teams-Kommunikationssupporttechniker

Weitere Informationen zu Teams Administratorrollen finden Sie unter Verwenden [Microsoft Teams zum Verwalten von Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Mit Real-Time Analytics können IT-Administratoren die geplanten Besprechungen ihrer wichtigen Benutzer sowie Audio-, Video-, Inhaltsfreigabe- und netzwerkbezogene Probleme anzeigen. Als Administrator können Sie diese Telemetrie verwenden, um diese Probleme während Besprechungen zu untersuchen und die Problembehandlung in Echtzeit zu führen.

## <a name="what-is-real-time-analytics"></a>Was ist Real-Time Analyse?

Heute steht ihnen die Problembehandlung einzelner Besprechungen Teams Anrufanalyse [nach dem](use-call-analytics-to-troubleshoot-poor-call-quality.md) Ende der Besprechung zur Verfügung. Real-Time Analytics ermöglicht Administratoren die Problembehandlung bei geplanten Besprechungen, während sie in Bearbeitung sind.

Real-Time Analyse zeigt detaillierte Informationen zu Teams Besprechungen für jeden Benutzer in Ihrem Office 365-Konto an, die in Echtzeit aktualisiert werden. Sie enthält Informationen zu Geräten, Netzwerk, Konnektivität, Audio-, Video- und Inhaltsfreigabeproblemen, die Administratoren dabei unterstützen, Probleme mit der Anrufqualität effektiver zu behandeln.

Als Teams erhalten Sie Vollzugriff auf alle Echtzeit-Telemetriedaten für jeden Benutzer. Darüber hinaus können Sie den Mitarbeitern Azure Active Directory Rollen zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter [Erteilen von Berechtigungen für Supportmitarbeiter und Helpdesk-Mitarbeiter](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Wo finde ich Echtzeit-Problembehandlung für Telemetriedaten pro Benutzer?

Um alle Besprechungsinformationen und Daten für einen Benutzer zu sehen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen **Sie unter** >  **Benutzermanage users** einen Benutzer aus, **und** öffnen Sie die Registerkarte & Besprechungen und Anrufe auf der Profilseite des Benutzers. Unter **Aktuelle Besprechungen** wird eine Liste der Besprechungen angezeigt, an denen der Benutzer innerhalb der letzten 24 Stunden teilgenommen hat, für die *Echtzeit-Telemetrie* zur Verfügung steht, einschließlich aller in Bearbeitung waren. Wenn die Besprechung noch nicht läuft oder keine Echtzeit-Telemetriedaten enthält, werden diese in vergangenen **Besprechungen angezeigt**.

:::image type="content" alt-text="Screenshot der Tabelle für kürzliche Besprechungen" source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Um zusätzliche Informationen zu den Teilnehmern einer aktuellen Besprechung zu erhalten, einschließlich Geräte-, Netzwerk- und Audiostatistiken, suchen Sie die **Besprechung unter Aktuelle** Besprechungen, und wählen Sie den Link unter der Spalte **Teilnehmer** aus.

:::image type="content" alt-text="Screenshot der Tabelle "Teilnehmerdetails"." source="media/participant-details.png" lightbox="media/participant-details.png":::

Wählen Sie die Besprechungs-ID aus, um die Telemetrie eines bestimmten Benutzers für eine in Bearbeitung ausgeführte Besprechung zu betrachten, einschließlich Informationen zu Gerät, Netzwerk, Audio, Video und Inhaltsfreigabe.

:::image type="content" alt-text="Screenshot der Benutzersitzungsdaten der Anrufanalyse" source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>In der Analyse Real-Time Measures verfügbar

### <a name="audio"></a>Audio
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Jitter |Millisekunden |Weniger als 30 ms |Jitter ist ein Maß für die Variation der Paketverzögerung für einen Datenstrom. Wenn dies zu hoch ist, kann das Audio abgehackt werden. | 
|Paketverlust |Prozent |Weniger als 5 % |Paketverluste treten auf, wenn Datenpakete ihr Ziel nicht erreichen. Der Prozentsatz der verlorenen Pakete basiert auf der Gesamtzahl der gesendeten Pakete. |
|Round Trip Time |Millisekunden |Weniger als 500 ms |Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierüber ist, dass zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt miteinander sprechen. |
|Bitrate |Kilobit pro Sekunde (KBit/s) |Größer als 24 KBit/s |Durchsatz des Audiodatenstroms, der in Kilobit pro Sekunde ausgedrückt wurde. |


### <a name="video"></a>Video
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Round Trip Time |Millisekunden |Weniger als 500 ms |Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierüber ist, dass zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt miteinander sprechen. |
|Bitrate |Megabit pro Sekunde (MBit/s) | Nur Informationen |Durchsatz des Videodatenstroms, der in Megabit pro Sekunde ausgedrückt wurde. |
|Framerate (Video) |Frames pro Sekunde |360p oder mehr: 25-30 BILDER/Sekunde <br/> 270p oder niedriger: 7-15 BILDER/Sekunde |Bei ausgehenden Videostreams ist die Framerate (Framerate, FPS) die Anzahl der Frames pro Sekunde des Vom Client gesendeten Videos. Hier können niedrigere als die erwarteten Werte Systemressourcenbeschränkungen, unzureichende Netzwerkbandbreite oder falsch zu verhaltende Videoaufzeichnungsgeräte vorschlagen. Unterschiedliche Auflösungen haben unterschiedliche zulässige FPS-Bereiche. |
|Codec |String | Nur Informationen |Zeigt den Videocodec und Rendermodus des ausgehenden Videostreams an. (Beispiel: H264 SW HW gibt einen H264-Videostream mit Software- und Hardwarerendering an.)|
|Lösung |Pixel | Nur Informationen |Die Auflösung des gesendeten Videos. Die ausgehende Videoauflösung ist dynamisch, basierend auf der höchsten Anforderung von einem Endpunkt in der Besprechung. Ein Client mit Video der Größe 1920 x 1080 sendet nur 640 x 360 Video, wenn keine Clients das Video des Benutzers in einem Frame größer als 640 x 360 anzeigen. |


### <a name="application-sharing-vbss"></a>Anwendungsfreigabe (VBSS)
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Paketverlust |Prozent |Weniger als 5 % |Paketverluste treten auf, wenn Datenpakete ihr Ziel nicht erreichen. Der Prozentsatz der verlorenen Pakete basiert auf der Gesamtzahl der gesendeten Pakete. |
|Round Trip Time |Millisekunden |Weniger als 500 ms |Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierüber ist, dass zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt miteinander sprechen. |
|Bitrate |Megabit pro Sekunde (MBit/s) | Nur Informationen |Durchsatz des VBSS-Datenstroms, der in Megabit pro Sekunde ausgedrückt wurde. |
|Framerate |Frames pro Sekunde (FPS) | Nur Informationen |Bei VBSS ist die Framerate inhaltsbewusst, um sicherzustellen, dass so viele Frames wie nötig gesendet werden, um eine gute Benutzererfahrung sicherzustellen und das Senden von Frames zu vermeiden, wenn sie nicht benötigt werden. Das Freigeben eines Textdokuments auf dem Bildschirm erfordert z. B. nur einen Frame pro Sekunde, um eine gute Erfahrung zu erzeugen, während das Teilen eines Videos oder Inhalts mit mehr Aktivität die Frames pro Sekunde auf maximal 30 Bilder/Sekunde erhöht, um eine reibungslosere Benutzererfahrung zu ermöglichen. |
|Codec |String | Nur Informationen |Zeigt den Codec und Rendermodus des VBSS-Datenstroms an. (Beispiel: H264 SW HW gibt einen H264 VBSS-Stream mit Software- und Hardwarerendering an.)|
|Lösung |Pixel | Nur Informationen |Die Auflösung des gesendeten und empfangenen VBSS-Datenstroms. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Für Echtzeit-Telemetrie unterstützte Clientplattformen

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams Webclient (einschließlich VDI) unterstützt nicht die Übermittlung von Telemetrie in Echtzeit.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams-Geräten mit Unterstützung für Echtzeit-Telemetrie

- MTR - Surface Hub
- MTR – Teams Display
- MTR – Zusammenarbeitsleiste
- IP Telefon Geräte

> [!NOTE]
> Geräte, die mit CVI-Lösungen (Cloud Video Interop) an der Besprechung Real-Time werden.


## <a name="limitations"></a>Einschränkungen

- Echtzeit-Telemetrie ist nur für geplante Besprechungen verfügbar. Für Ad-hoc-Besprechungen wie "Jetztbesprechung", "PSTN", 1:1-Anrufe und Gruppenanrufe steht keine Echtzeit-Telemetrie zur Verfügung.
- Echtzeit-Telemetrie ist nur für  Moderatoren eines geplanten Live-Ereignisses verfügbar. Es steht derzeit für Teilnehmer an Live-Veranstaltungen nicht zur Verfügung.
- Echtzeit-Telemetriedaten stehen für eine Besprechung unter Letzte Besprechungen für 24 Stunden nach Dem Ende der Besprechung zur Verfügung. Nach 24 Stunden können Sie nicht mehr auf die Daten zugreifen, und die Besprechung wird zu **vergangenen Besprechungen bewegt**. Wenn eine Besprechung länger als 3 Stunden dauert, ist Echtzeit-Telemetrie nur für die letzten *3 Stunden verfügbar*.
- Telemetrie ist in Echtzeit nicht verfügbar, wenn Sie ältere Versionen von Teams. Wenn keine Telemetrie verfügbar ist, versuchen Sie, Ihren Client zu aktualisieren.
- Wenn externe Teilnehmer oder anonyme Benutzer an einer Besprechung teilnehmen, wird der Anzeigename  als nicht verfügbar angezeigt, um die Mandantenübergreifende Privatsphäre zu bewahren.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

[Verwenden Microsoft Teams Administratorrollen zum Verwalten von Teams](/MicrosoftTeams/using-admin-roles).
