---
title: Anwesenheit in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informieren Sie sich über die Anwesenheitsstatus in Microsoft Teams und die administrativen Einstellungen für die Anwesenheitsfunktion.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17848cd1abd588ea1cd5106327ee576a318191bd06035389a8475b1fc258f8f2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350517"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

Die Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und überall in Microsoft 365 oder Office 365). Die Anwesenheit zeigt anderen Benutzern die aktuelle Verfügbarkeit und den aktuellen Status des Benutzers an. Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer gerade online verfügbar sind. Die Anwesenheit wird auf dem Web und den Desktop-Versionen in Echtzeit aktualisiert, wenn Sie die Seite auf dem Mobilgerät aktualisieren.

 > [!NOTE]
 > Mehr über Teams-Benutzerprofile auf verschiedenen Plattformen erfahren Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

 > [!NOTE]
 > Teams berücksichtigt Ihre Datenschutzkonfiguration, d. h.,wenn Sie den Datenschutzmodus aktiviert haben, ist Ihre Anwesenheit für externe Benutzer nicht sichtbar.
## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

|Benutzerdefiniert|Durch die App konfiguriert|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) Verfügbar, Außer Haus. Hinweis: „Außer Haus“ wird automatisch für die Zeiträume eingestellt, in denen der Benutzer "automatische Antworten" festlegt. Wenn der Benutzer die App in diesen Zeiträumen verwendet, kann eine doppelte Anwesenheit angezeigt werden wie z. B. „Außer Haus, verfügbar“. |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) Am Telefon|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) In einer Besprechung |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) Am Telefon – abwesend|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) Nicht stören ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) Hält Präsentation|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) Fokuszeit: Eine Fokuszeit findet statt, wenn die Benutzer die Fokuszeit unter MyAnalytics/Insights in ihren Kalendern einplanen.|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend|
|| ![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) Bin gleich zurück| |
|![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Als offline anzeigen|![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Offline: Wenn Benutzer einige Minuten nicht auf ihren Geräten angemeldet sind, wird Offline als ihr Status angezeigt. | |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
|| ![Lila Kreis mit Pfeil zeigt an: Außer Haus](media/Presence_OOF.png) Abwesenheit: Abwesenheit wird verwendet, wenn die Option „Abwesenheitsnachricht“ aktiviert ist. |
|||
 > [!NOTE]
 > Für Benutzer, deren Postfach lokal gehostet wird, werden Verzögerungen der Anwesenheitsmeldungen von bis zu einer Stunde (maximal) erwartet.

App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (Verfügbar, Abwesend), Outlook-Kalenderstatus (In einer Besprechung) oder Team-App-Status (In einem Anruf, Präsentieren). Wenn Sie gemäß Ihrem Kalender im Fokusmodus sind, dann werden Personen in Teams den Status **Fokussierend** sehen. In anderen Produkten wird der Fokusmodus als **Nicht stören** angezeigt.

Ihr aktueller Anwesenheitsstatus wechselt zu „Abwesend“, wenn Sie Ihren Computer sperren oder wenn Ihr Computer in den Leerlauf oder Ruhezustand übergeht. Auf einem Mobilgerät ändert sich Ihr Anwesenheitsstatus immer auf „Abwesend“, wenn die Teams-App im Hintergrund läuft.

Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus. Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist. Wenn ein Benutzerstatus auf „Nicht stören“ gesetzt ist, wird der Benutzer weiterhin Chat-Nachrichten erhalten, aber Banner-Benachrichtigungen werden nicht angezeigt.

Benutzer erhalten Anrufe in jedem Anwesenheitsstatus, außer für „Nicht stören“. In diesem Fall gehen eingehende Anrufe zu Voicemail. Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.

Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln. Personen mit Vorrang können den Benutzer auch dann kontaktieren, wenn der Benutzerstatus auf „Nicht stören“ gesetzt ist.

### <a name="dual-presence"></a>Doppelte Anwesenheit

  Die Art, wie die Anwesenheit für die meisten Benutzer funktioniert, wird durch die Ereignisse im Kalender oder durch Geräteereignisse wie z. B. einen Anruf beeinflusst. Der Benutzer kann diesen Status in der Benutzeroberfläche überschreiben, indem er manuell Status festlegt, die eine gewisse Ablaufzeit haben.

## <a name="user-configured-states-expiration"></a>Ablaufzeit benutzerdefinierter Status

Wenn ein Benutzer einen bestimmten Anwesenheitsstatus auswählt, hat dieser Vorrang vor jeder Aktualisierung durch App-Aktivität. Wenn der Benutzer beispielsweise seinen Status selber auf „Nicht stören“ setzt, dann bleibt diese Anwesenheit auf „Nicht stören“, selbst wenn der Benutzer an einer Besprechung teilnimmt oder einen Anruf beantwortet.

Vom Benutzer konfigurierte Status haben Standardablaufeinstellungen in Teams, um zu verhindern, dass Benutzer einen Status anzeigen, der nach einer bestimmten Zeit möglicherweise nicht mehr relevant ist.

|Benutzerdefinierter Status|Standardablauf|
|:--- |:---|
| Beschäftigt|1 Tag|
| Nicht stören|1 Tag|
| Sonstige|7 Tage|
|||

> [!NOTE]
> Ein Benutzer kann die Dauer einer Anwesenheit auch manuell konfigurieren. Ein Benutzer kann sich beispielsweise selber den Status „Als offline anzeigen bis Morgen früh“ setzen.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Administratoreinstellungen in Teams im Vergleich zu Skype for Business

Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:

- In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert. Die Konfiguration der Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) ist in Teams nicht verfügbar.
- Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert. Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.
- Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.
- Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.
- Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.

> [!NOTE]
> Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Administratoreinstellungen in Teams im Vergleich zu Microsoft Outlook

Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher für Kontakte in der gleichen Organisation unterstützt.

Wenn die Richtlinie für den Aktualisierungsmodus für das Benutzerkonto auf „Nur Teams“ gesetzt ist, dann wird Outlook mit Teams sprechen, um die Anwesenheit zu erhalten. Wenn das Benutzer nicht auf „Nur Teams“ gesetzt ist, dann wird Outlook mit Skype for Business sprechen.

## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Funktionalität der Teams-Anwesenheitsfunktionen, wenn Ihre Organisation auch Skype for Business verwendet.
