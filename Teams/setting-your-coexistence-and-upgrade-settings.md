---
title: Festlegen Ihrer Einstellungen für Koexistenz und Upgrade
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Dieser Artikel soll Ihnen dabei helfen, den Koexistenzmodus zu wählen und andere Koexistenzeinstellungen festzulegen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8cf8b0400ae924924d73394be0ca4deabcdeb9e
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579611"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Festlegen Ihrer Einstellungen für Koexistenz und Upgrade


Wenn Sie Ihre Skype for Business-Benutzer zur Verwendung von Teams aktualisieren, stehen Ihnen mehrere Optionen zur Verfügung, mit denen Sie den Umstieg für Ihre Benutzer nahtlos gestalten können. Sie haben die Option, die Einstellungen für Koexistenz und Upgrade für alle Benutzer in Ihrer Organisation gleichzeitig bzw. für einzelne Personen oder Benutzergruppe in Ihrer Organisation festzulegen bzw daran Änderungen vorzunehmen. Beachten Sie, dass in älteren Versionen der Skype for Business-Clients diese Einstellungen möglicherweise nicht unterstützt werden. Weitere Informationen über die Clientversionen von Skype for Business finden Sie auf der [Seite Skype for Business-Downloads und -Updates](https://docs.microsoft.com/skypeforbusiness/software-updates). 

Sie können ein besseres Verständnis der für Sie verfügbaren Modi erhalten, indem Sie verstehen, wie Sie [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) oder [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)lesen.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für alle Benutzer in Ihrer Organisation

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie in der linken Navigation des [Microsoft Teams Admin Centers](https://admin.teams.microsoft.com/) zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**. 

2. Ändern Sie oben auf der Seite " **Teams-Upgrade** " die folgenden Optionen wie gewünscht.
    - Legen Sie den **Koexistenzmodus** fest.
        - **Inseln** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass die Benutzer Skype for Business und Teams gleichzeitig verwenden können.
        - **Nur Skype for Business** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur Skype for Business verwenden.
        - **Skype for Business mit Zusammenarbeit in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) verwenden.
        - **Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) und für Teams-Besprechungen verwenden.
        - **Nur für Teams** – verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur Teams verwenden. Beachten Sie, dass Benutzer trotz dieser Einstellung weiterhin an in Skype for Business gehosteten Besprechungen teilnehmen können.
        
    - **Skype for Business-Benutzern benachrichtigen, dass ein Upgrade für Teams zur Verfügung steht** einstellen. Wenn Sie diese Funktion aktivieren, teilt sie Skype for Business-Benutzern mit, dass sie in Kürze auf die Teams-App umsteigen werden.
    - Legen Sie die **Bevorzugte App für Benutzer zur Teilnahme an Skype for Business-Besprechungen** fest. Diese Einstellung bestimmt, welche App zur Teilnahme an Skype for Business-Besprechungen verwendet wird und wird unabhängig vom Wert des Koexistenzmodus berücksichtigt.
      - **Skype-Besprechungs-App**
      - **Skype for Business mit eingeschränkten Funktionen**
    - Wählen, Sie, ob die Funktion **Teams-App im Hintergrund für Benutzer von Skype for Business herunterladen** durchgeführt werden sollte.  Mit dieser Einstellung wird die Teams-App für Benutzer, die Skype for Business unter Windows ausführen, automatisch heruntergeladen. Dies erfolgt nur, wenn der Koexistenzmodus für den Benutzer auf „Nur Teams“ gesetzt ist oder eine ausstehende Aktualisierungsbenachrichtigung in der Skype for Business-App aktiviert ist.
3. Nachdem Sie die gewünschten Änderungen vorgenommen haben, drücken Sie **Speichern**.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für einen einzelnen Benutzer in Ihrer Organisation

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Benutzer** und wählen Sie dann den Benutzer aus der Liste aus. 
2. Klicken Sie auf der Registerkarte **Konto** für den Benutzer unter **Teams-Upgrade** auf **Bearbeiten**.
3. Sie können den **Koexistenzmodus** festlegen. Wählen Sie aus den folgenden Optionen aus:
     - **Organisationsweite Einstellungen verwenden** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer die Einstellungen in den **Organisationsweiten** Einstellungen verwendet. 
     - **Inseln** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business und Teams zusammen verwenden kann. 
     - **Nur Skype for Business** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer nur Skype for Business verwendet.
     - **Skype for Business mit Zusammenarbeit in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) verwendet.
      - **Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) und für Teams-Besprechungen verwendet.
     - **Nur Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer nur Teams verwendet. Der Benutzer kann weiterhin an Skype for Business-Besprechungen teilnehmen.
4. Wenn Sie einen anderen **Koexistenzmodus** als **Organisationsweite Einstellungen** verwenden wählen, haben Sie die Möglichkeit, in der Skype for Business-App des Nutzers Benachrichtigungen zu aktivieren, dass das Upgrade auf Teams demnächst erfolgt. Sie können diese Benachrichtigung für den Benutzer aktivieren, indem Sie die Option **Den Skype for Business-Benutzer benachrichtigen** aktivieren.
5. Nachdem Sie die gewünschten Änderungen vorgenommen haben, drücken Sie **Speichern**.

### <a name="related-topics"></a>Verwandte Themen
[Upgrade von Skype for Business auf Teams – für IT-Administratoren](upgrade-to-teams-on-prem-overview.md)

[Die Reise planen](upgrade-plan-journey.md)

[Die Koexistenz und den Upgrade-Prozess für Skype for Business und Teams verstehen](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)
