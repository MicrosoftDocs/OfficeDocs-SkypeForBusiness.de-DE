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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062961"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

"Anwesenheit" ist Teil des Benutzerprofils in Microsoft Teams (und innerhalb von Office 365). Sie zeigt anderen Benutzern die gegenwärtige Verfügbarkeit und den Status des Benutzers an. Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **Nur-Teams**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Problemumgehung: Wenn Sie die Anwesenheitsinformationen in Outlook (und anderen Office-Apps) anzeigen möchten, muss Skype for Business installiert sein, auch wenn Sie Microsoft Teams im **Nur-Teams**-Modus ausführen. Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

Die Anwesenheitsstatus in Team sind:

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
 
Benutzer haben verschiedene Möglichkeiten, ihren aktuellen Anwesenheitsstatus festzulegen, und ihr Status wird für alle anderen Benutzer sichtbar. Weitere Details zur Benutzeranwesenheit werden ebenfalls automatisch aktualisiert. Dies geschieht auf Basis von Benutzeraktivitäten (z. B. "verfügbar" oder "abwesend"), des Outlook-Kalenderstatus (z. B. "in einer Besprechung") oder des Teams-App-Status ("am Telefon", "hält Präsentation"), die in der Liste aufgeführt sind.

Es gibt ein Inaktivitätszeitlimit von 15 Minuten. Danach wird der aktuelle Anwesenheitsstatus eines Benutzers auf "abwesend" zurückgesetzt.

Benutzer können festlegen, wer sie unterbrechen darf, d. h. sie trotz eines „Nicht stören“-Status kontaktieren kann. Diese Einstellungen stehen im Teams-Client zur Verfügung.

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
