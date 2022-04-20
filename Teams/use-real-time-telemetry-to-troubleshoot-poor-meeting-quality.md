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
description: Verwenden Sie Telemetrie in Echtzeit mit Details zu Geräten, Netzwerken und Konnektivität, um Benutzerprobleme bei Microsoft Teams geplanten Besprechungen zu beheben.
ms.openlocfilehash: 09c31b7734a849740cf1b0ff5749e4d82c667faf
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2022
ms.locfileid: "62518727"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Verwenden von Echtzeit-Telemetrie zur Problembehandlung bei schlechter Besprechungsqualität

In diesem Artikel wird erläutert, wie Sie Real-Time Analytics (RTA) verwenden, um probleme mit schlechter Microsoft Teams Besprechungsqualität für einzelne Benutzer zu beheben. Sie können auf Real-Time Analytics zugreifen, wenn Sie über eine der folgenden Rollen verfügen:

- Teams-Administrator
- Supportfachmann für die Teams-Kommunikation
- Teams-Kommunikationssupporttechniker

Weitere Informationen zu Teams Administratorrollen finden [Sie unter Verwenden Microsoft Teams Administratorrollen zum Verwalten von Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics ermöglicht ES IT-Administratoren, sich die geplanten Besprechungen ihrer wichtigen Benutzer anzusehen und Audio-, Video-, Inhaltsfreigabe- und Netzwerkprobleme anzuzeigen. Als Administrator können Sie diese Telemetrie verwenden, um diese Probleme während Besprechungen zu untersuchen und Probleme in Echtzeit zu beheben.

## <a name="what-is-real-time-analytics"></a>Was ist Real-Time Analytics?

Heute ist die Problembehandlung für einzelne Besprechungen für Teams Administratoren über [die Anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) nach Ablauf der Besprechung verfügbar. Real-Time Analytics ermöglicht Administratoren die Problembehandlung bei geplanten Besprechungen, während sie gerade ausgeführt werden.

Real-Time Analytics zeigt detaillierte Informationen zu Teams Besprechungen für jeden Benutzer in Ihrem Office 365 Konto an, die in Echtzeit aktualisiert werden. Es enthält Informationen zu Geräten, Netzwerk, Konnektivität, Audio-, Video- und Inhaltsfreigabeproblemen, was Administratoren dabei hilft, die Anrufqualität effektiver zu beheben.

Als Teams-Administrator erhalten Sie vollumfänglichen Zugriff auf alle Telemetriedaten in Echtzeit für jeden Benutzer. Darüber hinaus können Sie den Supportmitarbeitern Azure Active Directory Rollen zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter [Erteilen von Berechtigungen für Support- und Helpdeskmitarbeiter](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Wo finden Sie die Problembehandlung für Telemetrie pro Benutzer in Echtzeit?

Um alle Besprechungsinformationen und -daten für einen Benutzer anzuzeigen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen Sie unter **"Benutzerbenutzer** >  **verwalten**" einen Benutzer aus, und öffnen Sie die Registerkarte **"Besprechungen & Anrufe**" auf der Profilseite des Benutzers. Unter **"Zuletzt verwendete Besprechungen**" wird eine Liste der Besprechungen angezeigt, an denen der Benutzer innerhalb der letzten 24 Stunden teilgenommen hat *, für die Telemetrie in Echtzeit verfügbar ist*, einschließlich aller laufenden Besprechungen. Wenn die Besprechung nicht ausgeführt wird oder keine Telemetriedaten in Echtzeit enthält, wird sie in **früheren Besprechungen** angezeigt.

:::image type="content" alt-text="Screenshot der Tabelle &quot;Zuletzt verwendete Besprechungen&quot;." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Wenn Sie weitere Informationen zu Teilnehmern einer laufenden Besprechung erhalten möchten, einschließlich geräte-, Netzwerk- und Audiostatistiken, suchen Sie die Besprechung in **"Zuletzt verwendete Besprechungen** ", und wählen Sie den Link unter der Spalte **"Teilnehmer** " aus.

:::image type="content" alt-text="Screenshot der Teilnehmerdetailseite." source="media/participant-details.png" lightbox="media/participant-details.png":::

Wählen Sie die **Besprechungs-ID** aus, um sich die Telemetrie eines bestimmten Benutzers für eine laufende Besprechung anzusehen, einschließlich Informationen zu Geräte-, Netzwerk-, Audio-, Video- und Inhaltsfreigabedetails.

:::image type="content" alt-text="Screenshot der Benutzersitzungsdaten der Anrufanalyse." source="media/real-time-telemetry.png" lightbox="media/real-time-telemetry.png":::

## <a name="measures-available-in-real-time-analytics"></a>In Real-Time Analytics verfügbare Maßnahmen

### <a name="audio"></a>Audio
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Jitter |Millisekunden |Weniger als 30 ms |Jitter ist ein Maß für die Variation der Paketverzögerung für einen Datenstrom. Wenn dies zu hoch ist, kann die Audiowiedergabe abgehackt werden. | 
|Paketverlust |Prozent |Weniger als 5 % |Paketverlust tritt auf, wenn Datenpakete ihr Ziel nicht erreichen. Der Prozentsatz der verlorenen Pakete basiert auf der Gesamtzahl der gesendeten Pakete. |
|Roundtripzeit |Millisekunden |Weniger als 500 ms |Roundtripzeit ist die Zeit, die ein einzelnes Paket benötigt, um vom Client zum Remoteendpunkt und zurück zum Client zu gelangen. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierfür ist, wenn zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt übereinander sprechen. |
|Bitrate |Kilobit pro Sekunde (KBit/s) |Mehr als 24 KBit/s |Durchsatz des Audiodatenstroms in Kilobit pro Sekunde. |


### <a name="video"></a>Video
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Roundtripzeit |Millisekunden |Weniger als 500 ms |Roundtripzeit ist die Zeit, die ein einzelnes Paket benötigt, um vom Client zum Remoteendpunkt und zurück zum Client zu gelangen. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierfür ist, wenn zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt übereinander sprechen. |
|Bitrate |Megabit pro Sekunde (MBit/s) | Nur Informationen |Durchsatz des Videodatenstroms in Megabit pro Sekunde. |
|Framerate (Video) |Frames pro Sekunde |360p oder höher: 25-30 FPS <br/> 270p oder niedriger: 7-15 FPS |Bei ausgehenden Videostreams ist die Framerate (FPS) die Anzahl der Frames pro Sekunde des Videos, das der Client sendet. Unter den erwarteten Werten können hier Systemressourceneinschränkungen, unzureichende Netzwerkbandbreite oder fehlerhafte Videoaufnahmegeräte vorgeschlagen werden. Unterschiedliche Auflösungen weisen unterschiedliche akzeptable FPS-Bereiche auf. |
|Codec |String | Nur Informationen |Zeigt den Videocodec und den Renderingmodus des ausgehenden Videostreams an. (Beispiel: H264 SW HW gibt einen H264-Videostream mit Software- und Hardwarerendering an.)|
|Lösung |Pixel | Nur Informationen |Die Auflösung des gesendeten Videos. Ausgehende Videoauflösung ist dynamisch, basierend auf der höchsten Anforderung eines Endpunkts in der Besprechung. Ein Client mit 1920 x 1080 Video kann nur 640 x 360-Video senden, wenn kein Client das Video dieses Benutzers in einem Frame anzeigt, der größer als 640 x 360 ist. |


### <a name="application-sharing-vbss"></a>Anwendungsfreigabe (VBSS)
|Name der Kennzahl |Einheiten |Guter Schwellenwert |Beschreibung |
|:---|:---|:---|:---|
|Paketverlust |Prozent |Weniger als 5 % |Paketverlust tritt auf, wenn Datenpakete ihr Ziel nicht erreichen. Der Prozentsatz der verlorenen Pakete basiert auf der Gesamtzahl der gesendeten Pakete. |
|Roundtripzeit |Millisekunden |Weniger als 500 ms |Roundtripzeit ist die Zeit, die ein einzelnes Paket benötigt, um vom Client zum Remoteendpunkt und zurück zum Client zu gelangen. Eine hohe Roundtripzeit kann zu Verzögerungen bei der Streamwiedergabe führen. Ein Beispiel hierfür ist, wenn zwei Personen in einer Besprechung aufgrund der Verzögerung unbeabsichtigt übereinander sprechen. |
|Bitrate |Megabit pro Sekunde (MBit/s) | Nur Informationen |Durchsatz des VBSS-Datenstroms in Megabit pro Sekunde. |
|Bildrate |Frames pro Sekunde (FPS) | Nur Informationen |Für VBSS ist die Framerate inhaltsbewusst, um sicherzustellen, dass so viele Frames wie nötig gesendet werden, um eine gute Erfahrung zu gewährleisten und das Senden von Frames zu vermeiden, wenn sie nicht benötigt werden. Beispielsweise erfordert die Freigabe eines Textdokuments auf dem Bildschirm nur 1 Frame pro Sekunde, um eine gute Erfahrung zu erzielen, während die Freigabe eines Videos oder Inhalts mit mehr Aktivität die Frames pro Sekunde auf maximal 30 FPS erhöht, um eine reibungslosere Erfahrung zu erzielen. |
|Codec |String | Nur Informationen |Zeigt den Codec- und Renderingmodus des VBSS-Datenstroms an. (Beispiel: H264 SW HW gibt einen H264 VBSS-Stream mit Software- und Hardwarerendering an.)|
|Lösung |Pixel | Nur Informationen |Die Auflösung des VBSS-Datenstroms, der gesendet und empfangen wird. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Für Echtzeittelemetrie unterstützte Clientplattformen

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams Webclient (einschließlich VDI) unterstützt keine Telemetriebereitstellung in Echtzeit.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams Geräten mit Unterstützung für Echtzeittelemetrie

- MTR - Surface Hub
- MTR - Teams Anzeige
- MTR – Zusammenarbeitsleiste
- IP-Telefon-Geräte

> [!NOTE]
> Geräte, die mit Cloud Video Interop (CVI)-Lösungen an der Besprechung teilnehmen, werden in Real-Time Analytics nicht unterstützt.


## <a name="limitations"></a>Einschränkungen

- Telemetrie in Echtzeit ist nur für geplante Besprechungen verfügbar. Für Ad-hoc-Besprechungen wie Meet Now, PSTN, 1:1-Anrufe und Gruppenanrufe ist keine Telemetrie in Echtzeit verfügbar.
- Telemetrie in Echtzeit ist nur für Referenten von geplanten Liveereignissen verfügbar. Es ist derzeit nicht für Liveereignisteilnehmer verfügbar.
- Telemetriedaten in Echtzeit sind 24 Stunden nach Beendigung der Besprechung für eine Besprechung unter **"Zuletzt verwendete Besprechungen** " verfügbar. Nach 24 Stunden können Sie nicht mehr auf die Daten zugreifen, und die Besprechung wechselt zu **"Vergangene Besprechungen**". Wenn eine Besprechung länger als 3 Stunden ist, ist die Echtzeittelemetrie nur für die *letzten 3 Stunden* verfügbar.
- Telemetrie ist nicht in Echtzeit verfügbar, wenn ältere Versionen von Teams verwendet werden. Wenn keine Telemetrie verfügbar ist, versuchen Sie, Ihren Client zu aktualisieren.
- Wenn externe Teilnehmer oder anonyme Benutzer an einer Besprechung teilnehmen, wird ihr Anzeigename als **nicht verfügbar** angezeigt, um mandantenübergreifenden Datenschutz beizubehalten.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

[Verwenden Sie Microsoft Teams Administratorrollen, um Teams zu verwalten](/MicrosoftTeams/using-admin-roles).
