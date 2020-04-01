---
title: Anwesenheit in Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informationen für Administratoren zur Anwesenheit in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096970"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt. Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **Nur-Teams**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Problemumgehung: Wenn Sie die Anwesenheitsinformationen in Outlook (und anderen Office-Apps) anzeigen möchten, muss Skype for Business installiert sein, auch wenn Sie Microsoft Teams im **Nur-Teams**-Modus ausführen. Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.

Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

|Benutzerdefiniert|Durch die App konfiguriert|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) Verfügbar – außer Haus |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) Am Telefon|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) In einer Besprechung |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) Am Telefon – abwesend|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) Nicht stören ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) Hält Präsentation|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) Fokussierend|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend|
|| ![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) Bin gleich zurück| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  Nicht bei der Arbeit|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Offline |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) Gesperrt |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) Außer Haus|
|||

App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation).

Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn er in den Leerlauf-oder Ruhemodus wechselt. Auf mobilen Geräten wechselt Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.

Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus. Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist. Wenn sich ein Benutzer in "nicht stören" befindet, erhält der Benutzer weiterhin Chatnachrichten, aber Banner Benachrichtigungen werden nicht angezeigt.

Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden. Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.

Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln. Personen mit Prioritätszugriff können sich an den Benutzer wenden, selbst wenn sich der Benutzer in "nicht stören" befindet.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Administratoreinstellungen in Teams im Vergleich zu Skype for Business

Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:

- In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert. Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.
- Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert. Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.
- Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.
- Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.
- Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.

> [!NOTE]
> Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.

## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.
