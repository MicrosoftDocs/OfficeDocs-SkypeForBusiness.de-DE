---
title: Anwesenheit in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informieren Sie sich über die Anwesenheitsstatus in Teams und die administrativen Einstellungen für das Anwesenheits Feature.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2949ef0defec37ce674fb8d7a94250d29fe0a3a
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385642"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Microsoft 365 oder Office 365). Anwesenheitsinformationen kennzeichnet die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer. Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind. Anwesenheitsinformationen werden in Echtzeit auf der Web-und Desktop Version aktualisiert, wenn Sie die Seite auf mobilen Geräten aktualisieren.

 > [!Note]
 > Ausführliche Informationen zu Teams-Benutzerprofilen auf unterschiedlichen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

|Benutzerdefiniert|Durch die App konfiguriert|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) Verfügbar, außer Haus. Hinweis: Abwesenheit wird automatisch für die Zeiträume festgelegt, in denen der Benutzer "automatische Antworten" festlegt. Wenn der Benutzer die APP während dieser Zeiträume verwendet, wird möglicherweise ein doppelter Anwesenheitsstatus angezeigt, beispielsweise "außer Haus, verfügbar". |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) Am Telefon|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) In einer Besprechung |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) Am Telefon – abwesend|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) Nicht stören ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) Hält Präsentation|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) Fokussierung. Der Fokus tritt auf, wenn die Benutzer die Fokus Zeit in myAnalytics/Insights in ihren Kalendern planen.|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend|
|| ![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) Bin gleich zurück| |
|![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Als offline anzeigen|![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Offline.  Wenn Benutzer für ein paar Minuten nicht auf einem Ihrer Geräte angemeldet sind, werden Sie offline angezeigt. | |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) Nicht im Büro. Die Abwesenheit wird verwendet, wenn eine automatische Antwort festgesetzt wird. (Nur in Outlook verfügbar.) |
|||

App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation). Wenn Sie sich auf Grundlage Ihres Kalenders im Fokusmodus befinden, ist die **Fokussierung** der Status der Personen, die in Teams angezeigt werden. Der Fokusmodus wird in anderen Produkten als " **nicht stören** " angezeigt.

Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn Ihr Computer in den Leerlauf-oder Ruhemodus wechselt. Auf einem mobilen Gerät ändert sich Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.

Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus. Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist. Wenn ein Benutzerstatus auf "nicht stören" festgelegt ist, wird der Benutzer weiterhin Chatnachrichten empfangen, aber Banner Benachrichtigungen werden nicht angezeigt.

Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden. Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.

Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln. Personen mit Prioritätszugriff können sich an den Benutzer wenden, auch wenn der Status des Benutzers auf "nicht stören" eingestellt ist.

### <a name="dual-presence"></a>Doppelter Anwesenheitsstatus

  Die Art und Weise, wie die Anwesenheit für die meisten Benutzer funktioniert, ist von den Ereignissen in den Kalender-oder Geräteereignissen wie einem Anruf motiviert. Der Benutzer kann diesen Status auf der Benutzeroberfläche überschreiben, indem er Zustände, die eine gewisse Ablaufzeit aufweisen, manuell festlegt.

## <a name="user-configured-states-expiration"></a>Ablaufdatum des Benutzer konfigurierten Status

Wenn ein Benutzer einen bestimmten Anwesenheitsstatus auswählt, hat er Vorrang vor dem Update einer APP-Aktivität. Wenn sich ein Benutzer beispielsweise als "nicht stören" einstellt, bleibt sein Anwesenheitsstatus unverändert, auch wenn Sie an einer Besprechung teilnehmen oder einen Anruf entgegennehmen.

Benutzer konfigurierte Status weisen standardmäßige Ablaufeinstellungen in Teams auf, um zu verhindern, dass Benutzer einen Status anzeigen, der nach einer bestimmten Zeitspanne nicht relevant ist.

|Benutzer konfigurierter Zustand|Standardablaufdatum|
|:--- |:---|
| Beschäftigt|1 Tag|
| Nicht stören|1 Tag|
| Andere|7 Tage|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Administratoreinstellungen in Teams im Vergleich zu Skype for Business

Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:

- In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert. Der Datenschutz (in dem Sie definieren, wer Anwesenheitsinformationen sehen kann) ist in Microsoft Teams nicht verfügbar.
- Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert. Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.
- Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.
- Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.
- Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.

> [!NOTE]
> Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Administratoreinstellungen in Teams im Vergleich zu Microsoft Outlook

Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.

Wenn die Richtlinie für den Upgrademodus des Benutzerkontos auf TeamsOnly eingestellt ist, kommuniziert Outlook mit Teams, um Anwesenheitsinformationen zu erhalten. Wenn das Benutzerkonto nicht auf TeamsOnly eingestellt ist, spricht Outlook mit Skype for Business.

## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Weitere Informationen dazu, wie die Anwesenheit von Teams funktioniert, wenn Ihre Organisation ebenfalls Skype for Business verwendet, finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) .
