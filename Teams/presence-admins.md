---
title: Anwesenheit in Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Informations Administratoren müssen sich mit der Anwesenheit in Teams vertraut machen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fd6ac289df238d9f410266b1eca43a3a18f493e
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548525"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Teams

Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365) – und zeigt die aktuelle Verfügbarkeit und den Status des Benutzers an, die anderen Benutzern in der Organisation zur Verfügung stehen. Standardmäßig können alle Personen in Ihrer Organisation, die Teams verwenden, in nahezu Echtzeit sehen, ob andere Benutzer online verfügbar sind oder nicht.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

Die in Teams verfügbaren Benutzer Anwesenheitsstatus sind:

|Benutzer konfiguriert|App konfiguriert|
|:--- |:---|
| ![Vollständiges grünes Chek-Zeichen mit verfügbarem Anwesenheitsstatus](media/Presence_Available.png) Verfügbar|![Vollständiges grünes Chek-Zeichen mit verfügbarem Anwesenheitsstatus](media/Presence_Available.png) Verfügbar|
|| ![Open Green Chek Mark, der angibt, dass OOF verfügbar ist](media/Presence_Available_OOF.png) Verfügbar, außer Haus |
|  ![Vollständiger roter Kreis mit Anzeige von "beschäftigt"](media/Presence_Busy.png) Beschäftigt |  ![Beschäftigt](media/Presence_Busy.png) Beschäftigt  |
|| ![Vollständiger roter Kreis mit Anzeige von beschäftigt in einem Anruf](media/Presence_Busy.png) In einem Anruf|
|| ![Vollständiger roter Kreis, der angibt, dass in einer Besprechung beschäftigt ist](media/Presence_Busy.png) In einer Besprechung |
|| ![Roter Kreis öffnen, der auf busy OOF hinweist](media/Presence_Busy_OOF.png) In einem Anruf: Abwesenheit|
|  ![Roter Kreis mit weißer Zeile, Anzeige "nicht stören"](media/Presence_DND.png) Nicht stören ||
|| ![Roter Kreis mit weißer Zeile, der die Präsentation angibt](media/Presence_DND.png) Präsentieren|
| ![Symbol "gelbe Uhr" mit Anzeige "Abwesend"](media/Presence_Away.png) Abwesend| ![abwesend](media/Presence_Away.png) Abwesend|
|| ![Symbol "gelbe Uhr", das](media/Presence_Away.png) die letzte Anzeige *Zeit* entfernt|
|![Das gelbe Uhr-Symbol, das wegzeigt, ist gleich zurück](media/Presence_Away.png) Bin gleich zurück| |
|| ![Symbol "gelbe Uhr" mit Anzeige "Abwesend"](media/Presence_Away.png)  Off-Arbeit|
|| ![Grauer Kreis mit x, der Offline angibt](media/Presence_Offline.png) Offline |
|| ![Grauer Kreis öffnen, Anzeige des Status unbekannt](media/Presence_Unknown.png) Status unbekannt|
||![Öffnen des roten Kreises mit einer Diagonalen Zeile, die auf "blockiert" hinweist](media/Presence_Blocked.png) Blockiert |
|| ![Lila Kreis mit Pfeil, der auf Abwesenheit hinweist](media/Presence_OOF.png) Abwesenheit|
|||
 
Benutzer können Ihren aktuellen Anwesenheitsstatus manuell auf einige Optionen einstellen, und Ihr Status wird für alle anderen Benutzer wiedergegeben. Zusätzliche Benutzeranwesenheitsinformationen werden auch automatisch auf der Grundlage von Benutzeraktivitäten (wie "verfügbar" oder "Abwesend"), von Outlook-Kalenderstatus (wie in einer Besprechung) oder von Teams-App-Zuständen (in einem Aufruf, Präsentation) an Zustände aktualisiert, die in der Liste eingerückt sind.

Es gibt ein 15-minütiges Inaktivitäts-Timeout, nach dem der aktuelle Anwesenheitsstatus Ihrer Benutzer auf "Abwesend" zurückgesetzt wird.

Benutzer können angeben, wer durchbrechen kann (setzen Sie die Einstellung "nicht stören" außer Kraft). Diese Einstellungen sind in-app verfügbar.

## <a name="teams-is-not-skype-for-business"></a>Teams ist nicht Skype for Business

Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:
- Die Anwesenheits Freigabe ist in Teams für Benutzer in der Organisation immer aktiviert. Der Datenschutz (die Entscheidung, wer Anwesenheitsinformationen sehen kann) steht in Teams nicht zur Verfügung.
- Anwesenheits Freigaben für alle (einschließlich der Verbunddienste) sind für Benutzer in Teams immer aktiviert. Ihre Kontaktliste (sofern Sie eine in SFB hatte) ist unter **Chat >-Kontakte** oder unter **Anrufe >-Kontakte**sichtbar.
- Der Client stört nicht, und Durchbruch Features sind für Benutzer in Teams immer aktiviert.
- Kalender (einschließlich Abwesenheits-& andere Kalenderinformationen) die Integration ist für Benutzer in Microsoft Teams immer aktiviert, wenn Sie in Outlook integriert ist.
- Die *zuletzt* gesehene oder *Abwesenheits* Anzeige (falls in einer dualen Umgebung mit Skype for Business) ist für Benutzer in Teams immer aktiviert.

> [!NOTE]
> Die Fähigkeit eines Teams-Administrators, diese Einstellungen anzupassen, wird derzeit nicht unterstützt.


## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Weitere Informationen dazu, wie die Anwesenheit von Teams funktioniert, wenn Sie mit Skype for Business zusammen existieren, finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) . 
