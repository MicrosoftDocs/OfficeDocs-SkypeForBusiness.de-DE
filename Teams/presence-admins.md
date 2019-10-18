---
title: Anwesenheit in Microsoft Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informationen für Administratoren zur Anwesenheit in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573217"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt. Standardmäßig können alle Personen in Ihrer Organisation, die Teams verwenden, (nahezu in Echtzeit) sehen, ob andere Benutzer online verfügbar sind.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **TeamsOnly**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Problemumgehung: damit die Anwesenheit in Outlook (und anderen Office-Apps) angezeigt wird, muss Skype for Business installiert sein, auch wenn Sie nur Teams im Modus " **nur Teams** " ausführen. Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

Die in Teams verfügbaren Benutzer Anwesenheitsstatus sind:

|Benutzer konfiguriert|App konfiguriert|
|:--- |:---|
| ![Vollständiges grünes Häkchen, kennzeichnet Anwesenheitsstatus](media/Presence_Available.png) Verfügbar|![Vollständiges grünes Häkchen, kennzeichnet Anwesenheitsstatus](media/Presence_Available.png) Verfügbar|
|| ![Grünes Häkchen öffnen, kennzeichnet verfügbare Abwesenheit](media/Presence_Available_OOF.png) Verfügbar, außer Haus |
|  ![Vollständiger roter Kreis, zeigt "beschäftigt" an](media/Presence_Busy.png) Beschäftigt |  ![Vollständiger roter Kreis, zeigt "beschäftigt" an](media/Presence_Busy.png) Beschäftigt  |
|| ![Vollständiger roter Kreis, kennzeichnet beschäftigt in einem Anruf](media/Presence_Busy.png) In einem Anruf|
|| ![Vollständiger roter Kreis, zeigt "beschäftigt" in einer Besprechung an](media/Presence_Busy.png) In einer Besprechung |
|| ![Roter Kreis öffnen, zeigt "beschäftigt" an](media/Presence_Busy_OOF.png) In einem Anruf: Abwesenheit|
|  ![Roter Kreis mit weißer Zeile, kennzeichnet "nicht stören"](media/Presence_DND.png) Nicht stören ||
|| ![Roter Kreis mit weißer Zeile, zeigt die Präsentation an](media/Presence_DND.png) Präsentieren|
|| ![Roter Kreis mit weißer Zeile, zeigt die Fokussierung an](media/Presence_DND.png) Fokussierung|
| ![Symbol "gelbe Uhr", zeigt "Abwesend" an](media/Presence_Away.png) Abwesend| ![Symbol "gelbe Uhr", zeigt "Abwesend" an](media/Presence_Away.png) Abwesend|
|| ![Symbol "gelbe Uhr",](media/Presence_Away.png) zeigt "Abwesend" als letztes *mal* an|
|![Symbol "gelbe Uhr", "Abwesend", "gleich zurück"](media/Presence_Away.png) Bin gleich zurück| |
|| ![Symbol "gelbe Uhr", zeigt "Abwesend", "Arbeit" an](media/Presence_Away.png)  Off-Arbeit|
|| ![Grauer Kreis mit x, kennzeichnet offline](media/Presence_Offline.png) Offline |
|| ![Grauer Kreis öffnen, kennzeichnet Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
||![Roter Kreis mit diagonaler Linienart öffnen, zeigt "blockiert" an](media/Presence_Blocked.png) Blockiert |
|| ![Lila Kreis mit Pfeil, kennzeichnet Abwesenheitsanzeige](media/Presence_OOF.png) Abwesenheit|
|||
 
Benutzer können Ihren aktuellen Anwesenheitsstatus manuell auf einige Optionen einstellen, und Ihr Status wird für alle anderen Benutzer wiedergegeben. Weitere Details zur Benutzer Anwesenheit werden ebenfalls automatisch aktualisiert. Die Änderungen basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalender Zuständen (in einer Besprechung) oder Teams-App-Zustände (in einem Aufruf, Präsentation) an Zustände, die in der Liste eingerückt sind.

Es gibt ein 15-minütiges Inaktivitäts-Timeout, nach dem ein aktueller Anwesenheitsstatus auf "Abwesend" zurückgesetzt wird.

Benutzer können angeben, wer durchbrechen kann (was bedeutet, dass Sie trotz des Zustands "nicht stören" Kontakt mit Ihnen aufnehmen können). Diese Einstellungen sind im Team-Client verfügbar.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Administratoreinstellungen in Teams im Vergleich zu Skype for Business

Die folgenden Administratoreinstellungen für Skype for Business unterscheiden sich in Teams:

- In Teams ist die Anwesenheits Freigabe für Benutzer in der Organisation immer aktiviert. Der Datenschutz (in dem Sie definieren, wer Anwesenheitsinformationen sehen kann) ist in Microsoft Teams nicht verfügbar.
- Anwesenheits Freigaben für alle (einschließlich der Verbunddienste) sind für Benutzer in Teams immer aktiviert. Ihre Kontaktliste (wenn Sie eine in Skype for Business hatte) ist unter **Chat #a0 Kontakte** oder unter **Anrufe #a1 Kontakte**sichtbar.
- Der Client stört nicht, und Durchbruch Features sind für Benutzer in Teams immer aktiviert.
- Kalender (einschließlich Abwesenheits-und anderer Kalenderinformationen) die Integration ist für Benutzer immer aktiviert, wenn Teams in Outlook integriert sind.
- Der Indikator *zuletzt gesehen* oder *Abwesend* ist für Benutzer in Teams immer aktiviert, wenn die Organisation ebenfalls Skype for Business verwendet.

> [!NOTE]
> Die Fähigkeit eines Teams-Administrators, diese Einstellungen anzupassen, wird derzeit nicht unterstützt.

## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Weitere Informationen dazu, wie die Anwesenheit von Teams funktioniert, wenn Ihre Organisation ebenfalls Skype for Business verwendet, finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) .
