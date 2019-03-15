---
title: Anwesenheit in Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Administratoren Informationen müssen zum Verständnis von Anwesenheitsinformationen in Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75710a428273a38954de38ef5b6094d412aa3085
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640970"
---
# <a name="user-presence-in-teams"></a>Anwesenheit in Teams

Anwesenheit ist Teil der Profil eines Benutzers in Microsoft-Teams (und in der gesamten Office 365) – und gibt die aktuelle Verfügbarkeit und den Status für andere Benutzer in der Organisation des Benutzers an. Standardmäßig kann jeder Benutzer in Ihrer Organisation mithilfe von Teams anzeigen, und zwar unabhängig davon, ob andere Benutzer online zur Verfügung stehen.

## <a name="presence-states-in-teams"></a>Anwesenheitsstatus in Teams

Die Benutzer-Anwesenheitsstatus in Teams verfügbar sind:

|Benutzerdefiniert|App konfiguriert|
|:--- |:---|
| ![Anwesenheit verfügbar](media/Presence_Available.png) Verfügbar|![Anwesenheit verfügbar](media/Presence_Available.png) Verfügbar|
|| ![Oof verfügbar](media/Presence_Available_OOF.png) Verfügbar, abwesend |
|  ![Ausgelastet](media/Presence_Busy.png) Ausgelastet |  ![Ausgelastet](media/Presence_Busy.png) Ausgelastet  |
|| ![Ausgelastet](media/Presence_Busy.png) Im Gespräch|
|| ![Ausgelastet](media/Presence_Busy.png) In einer Besprechung |
|| ![ausgelastet oof](media/Presence_Busy_OOF.png) Im Gespräch abwesend|
|  ![Nicht stören](media/Presence_DND.png) Nicht stören ||
|| ![Nicht stören](media/Presence_DND.png) Einer Präsentation|
| ![Abwesend](media/Presence_Away.png) Abwesend| ![Abwesend](media/Presence_Away.png) Abwesend|
|| ![Abwesend](media/Presence_Away.png) abwesend letzten gesehen *Zeit*|
|![Abwesend](media/Presence_Away.png) Bin gleich zurück| |
|| ![Abwesend](media/Presence_Away.png)  Nicht bei der Arbeit|
|| ![Offline](media/Presence_Offline.png) Offline |
|| ![unbekannt](media/Presence_Unknown.png) Status unbekannt|
||![blockiert](media/Presence_Blocked.png) Blockiert |
|| ![Abwesend](media/Presence_OOF.png) Abwesend|
|||
 
Benutzer können ihre aktuellen Anwesenheitsstatus manuell auf einige Optionen festlegen, und deren Status Dient zum Abrufen und allen anderen Benutzern übernommen. Zusätzliche Anwesenheitsinformationen Benutzerdetails werden auch automatisch aktualisiert, basierend auf Benutzeraktivität (beispielsweise verfügbar oder abwesend), Outlook-Kalenderstatus (wie in einer Besprechung) oder Teams app-Status (In einem Aufruf präsentieren angezeigt), um Zustände, die in der Liste eingezogen werden.

Es ist ein Timeout 15 Minuten Inaktivität, nach dem wird der Benutzer aktuelle Anwesenheitsstatus in Abwesend zurückgesetzt werden.

Benutzer können angeben, die über unterbrechen können (in Kontakt treten Überschreiben einer Einstellung nicht stören). Diese Einstellungen sind verfügbar in-app.

## <a name="teams-is-not-skype-for-business"></a>Teams ist keine Skype für Unternehmen

Die folgenden administratoreinstellung in Skype für Unternehmen unterscheiden sich in Teams:
- Freigeben von Anwesenheitsinformationen wird immer in Teams für Benutzer in der Organisation aktiviert. Datenschutz (entscheiden, die Anwesenheitsinformationen angezeigt werden) Konfiguration ist nicht verfügbar in Teams.
- Anwesenheit Freigabe für alle Benutzer (einschließlich Federated Dienste) ist für Benutzer in Teams immer aktiviert. Ihrer Kontaktliste (Wenn sie SfB in war) wird angezeigt, unter **Chat > Kontakte** oder **Anrufe > Kontakte**.
- Client nicht stören und überzeugend Features sind für Benutzer in Teams immer aktiviert.
- Kalender (einschließlich OOF & anderen Kalender Info) Integration ist für Benutzer in Teams immer aktiviert, wenn in Outlook integriert.
- *Zuletzt gesehen* oder *Abwesend seit* (sofern in einer Umgebung mit zwei mit Skype für Unternehmen) Indikator ist für Benutzer in Teams immer aktiviert.
- Festlegen einer benutzerdefinierten Anwesenheitsstatus ist für Benutzer in Teams nicht aktiviert.

> [!NOTE]
> Die Möglichkeit zum Anpassen dieser Einstellungen einer Teams Admin wird derzeit nicht unterstützt.


## <a name="coexistence-with-skype-for-business"></a>Koexistenz mit Skype for Business

Informationen zur Funktionsweise von Teams Anwesenheit bei Koexistenz mit Skype für Unternehmen finden Sie unter [Koexistenz mit Skype für Unternehmen](coexistence-chat-calls-presence.md) . 