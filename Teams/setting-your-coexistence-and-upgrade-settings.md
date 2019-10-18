---
title: Festlegen Ihrer Einstellungen für Koexistenz und Upgrades
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
description: Dieser Artikel unterstützt Sie bei der Auswahl des Koexistenzmodus und bei der Einstellung anderer koexistenzeinstellungen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce472ca1c5307dd8a5573ca076c58e32e2d41df9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571524"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Festlegen Ihrer Einstellungen für Koexistenz und Upgrades

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Wenn Sie Ihre Skype for Business-Benutzer für die Verwendung von Teams upgraden, stehen Ihnen mehrere Optionen zur Verfügung, mit denen Sie einen nahtlosen Prozess für Ihre Benutzer durchführen können. Sie haben die Möglichkeit, Koexistenz-und Upgradeeinstellungen für alle Benutzer in Ihrer Organisation gleichzeitig zu erstellen, oder Sie können Änderungen an Einstellungen für eine einzelne Person oder eine Gruppe von Benutzern in Ihrer Organisation vornehmen. Beachten Sie, dass diese Einstellungen für ältere Versionen von Skype for Business-Clients nicht berücksichtigt werden. Weitere Informationen zu den Skype for Business-Clientversionen finden Sie auf der [Seite Skype for Business-Downloads und-Updates](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates). 

Sie können ein besseres Verständnis der Arten von Modi erhalten, die Ihnen zur Verfügung stehen, indem Sie verstehen, wie Sie [Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) oder [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)lesen.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für alle Benutzer in Ihrer Organisation

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Wechseln Sie in der linken Navigationsleiste zu **organisationsweiten Einstellungen** > **Teams Upgrade**. 

2. Nehmen Sie oben auf der Seite " **Teams-Upgrade** " die folgenden Änderungen vor, wenn Sie für Sie funktionieren.
    - Setzen Sie den **Koexistenzmodus** .
        - **Inseln** – verwenden Sie diese Einstellung, wenn Benutzer in der Lage sein sollen, Skype for Business und Teams gleichzeitig zu verwenden.
        - **Nur Skype for Business** – verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur Skype for Business verwenden.
        - **Nur für Teams** (in der Vorschau für einige Organisationen) – verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur Teams verwenden können. Beachten Sie, dass Benutzer auch bei dieser Einstellung weiterhin an Besprechungen teilnehmen können, die in Skype for Business gehostet werden.
    - Einrichten von **Skype for Business-Benutzern Benachrichtigen, dass Teams für ein Upgrade verfügbar sind**. Wenn Sie diese Option aktivieren, werden Sie den Skype for Business-Benutzern mitteilen, dass Sie in Kürze auf die Team-APP aktualisiert werden.
    - Wählen **Sie die bevorzugte App für Benutzer aus, um an Skype for Business-Besprechungen teilzunehmen**. Diese Einstellung bestimmt, welche App für die Teilnahme an Skype for Business-Besprechungen verwendet wird, und wird unabhängig vom Wert des Koexistenzmodus geehrt.
      - **Skype-Besprechungs-App**
      - **Skype for Business mit limitierten Funktionen**
    - Legen Sie fest, ob **die Teams-App im Hintergrund für Skype for Business-Benutzer heruntergeladen**werden soll.  Mit dieser Einstellung wird die Teams-App für Benutzer, die Skype for Business unter Windows ausführen, automatisch heruntergeladen. Sie wird nur berücksichtigt, wenn der Koexistenzmodus für den Benutzer nur Teams ist oder wenn Benachrichtigungen über ausstehende Upgrades in Skype for Business aktiviert sind.
3. Klicken Sie auf **Speichern** , nachdem Sie die Änderungen vorgenommen haben.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für einen einzelnen Benutzer in Ihrer Organisation

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Wechseln Sie in der linken Navigationsleiste zu **Benutzer**, und wählen Sie den Benutzer in der Liste aus. 
2. Klicken Sie auf der Registerkarte **Konto** für den Benutzer unter **Teams-Upgrade**auf **Bearbeiten**.
3. Sie können den **Koexistenzmodus**einstellen. Wählen Sie eine der folgenden Optionen aus:
     - **Verwenden von organisationsweiten Einstellungen** – verwenden Sie diese Einstellung, wenn der Benutzer die Einstellungen in den **organisationsweiten** Einstellungen verwenden soll. 
     - **Inseln** – verwenden Sie diese Einstellung, wenn der Benutzer in der Lage sein soll, Skype for Business und Teams zu verwenden. 
     - **Nur Skype for Business** – verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business verwendet. 
     - **Nur für Teams** – verwenden Sie diese Einstellung, wenn der Benutzer nur Teams verwenden soll. Der Benutzer kann weiterhin an Skype for Business-Besprechungen teilnehmen.
4. Wenn Sie einen anderen **Koexistenzmodus** als die **Verwendung von organisationsweiten Einstellungen**auswählen, haben Sie die Möglichkeit, Benachrichtigungen in der Skype for Business-App des Benutzers zu aktivieren, die in Kürze auf Teams aktualisiert wird. Sie können diese Benachrichtigung für den Benutzer aktivieren, indem Sie die Option **Skype for Business-Benutzer benachrichtigen** aktivieren.
5. Klicken Sie auf **Speichern** , nachdem Sie die Änderungen vorgenommen haben.

### <a name="related-topics"></a>Verwandte Themen
[Planen der Reise](upgrade-plan-journey.md)

[Grundlegendes zur Koexistenz-und Upgrade-Reise für Skype for Business und Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)
