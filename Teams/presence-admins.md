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
description: Informationen, die Administratoren benötigen, um Anwesenheit in Teams zu verstehen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244827"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Microsoft Teams

Anwesenheit ist Teil des Benutzerprofils in Microsoft Teams (und innerhalb von Office 365). Sie zeigt anderen Benutzern in der Organisation die gegenwärtige Verfügbarkeit und den Status des Benutzers an. Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, in beinahe in Echtzeit sehen, ob andere Benutzer online gerade verfügbar sind oder nicht.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

Die Anwesenheitsstatus in Team sind:

|Benutzerdefiniert|Durch die App konfiguriert|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) Verfügbar|
|| ![Ein nicht gefülltes grünes Häckchen zeigt an: verfügbar – abwesend](media/Presence_Available_OOF.png) Verfügbar – außer Haus |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) Beschäftigt  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einem Gespräch](media/Presence_Busy.png) Am Telefon|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) In einer Besprechung |
|| ![Ein offener roter Kreis zeigt an: beschäftigt – abwesend](media/Presence_Busy_OOF.png) Am Telefon – abwesend|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) Nicht stören ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) Hält Präsentation|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) Abwesend|
|| ![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*|
|![Das Symbol „gelbe Uhr“ zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) Bin gleich zurück| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  Nicht bei der Arbeit|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) Offline |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
||![Offener roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) Geblockt |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) Außer Haus|
|||
 
Benutzer haben verschiedene Möglichkeiten, Ihren aktuellen Anwesenheitsstatus festzulegen, und ihr Status wird für alle anderen Benutzer sichtbar. Weitere Details zum Anwesenheitsstatus eines Benutzers werden basierend auf Benutzeraktivitäten (z. b. "verfügbar" oder "abwesend"), dem Outlook-Kalenderstatus (z. b. in einer Besprechung) oder dem Teams-App-Status (in einem Aufruf, hält Präsentation) aktualisiert, die in der Liste aufgeführt sind.

Es gibt ein Inaktivitätszeitlimit von 15 Minuten. Danach wird der aktuelle Anwesenheitsstatus des Benutzers auf „abwesend“ zurückgesetzt.

Benutzer können festlegen, wer sie unterbrechen darf, d. h. sie trotz der „Nicht stören“-Einstellung kontaktieren kann. Diese Einstellungen stehen In-App zur Verfügung.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Administratoreinstellungen in Teams im Vergleich zu Skype for Business

Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:

- In Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert. Datenschutz (d. h. die Entscheidung, wer den Anwesenheitsstatus sehen kann) ist in Teams nicht verfügbar.
- Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Teams immer aktiviert. Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.
- Die Features „Nicht stören“ und „Unterbrechen“ sind für Benutzer in Teams immer aktiviert.
- Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.
- Die Anzeige *zuletzt anwesend* oder *abwesend seit* (in einem dualen Umfeld mit Skype for Business) ist für Benutzer in Teams immer aktiviert.

> [!NOTE]
> Die Möglichkeit diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.

## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen im Rahmen einer Koexistenz mit Skype for Business. 
