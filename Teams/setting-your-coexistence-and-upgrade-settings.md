---
title: Festlegen von Einstelllungen Upgrade und Koexistenz
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: In diesem Artikel helfen Ihnen beim Wählen Sie des Koexistenzmodus und andere Einstellungen Koexistenz festgelegt.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a83382ff46e5a698e3755f2c1d2d859dddd65f0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013201"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Festlegen von Einstelllungen Upgrade und Koexistenz

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Beim Aktualisieren von Ihrer Skype für Unternehmensbenutzer Teams verwenden, müssen Sie mehrere Optionen, die Sie machen einen nahtlosen Prozess für Ihre Benutzer unterstützen. Sie haben die Möglichkeit, stellen Koexistenz und Einstellungen für alle Benutzer in Ihrer Organisation gleichzeitig zu aktualisieren können, oder Sie Einstellungen Änderungen für einen einzelnen oder eine Gruppe von Benutzern in Ihrer Organisation. Beachten Sie, dass ältere Versionen von Skype für Business Clients diese Einstellungen nicht beachtet können.

Einstellungen auf der Benutzerebene zugewiesen haben Vorrang vor Ebene der gesamte Org Einstellungen. Sie erhalten ein besseres Verständnis der Typen von Modi, die Ihnen zur Verfügung stehen, Beitrag [Koexistenz verstehen und Durchführen eines Upgrades Weg für Skype für Unternehmen und Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="setting-upgrade-options-for-all-users-in-your-organization"></a>Festlegen von Optionen für alle Benutzer in Ihrer Organisation für upgrade

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Wechseln Sie im linken Navigationsbereich **Org geltende**Einstellungen > **Teams zu aktualisieren**. 

2. Stellen Sie wie folgt geändert am oberen Rand der Seite **Teams Seite ' upgrade '** Wenn sie für Sie geeignet ist.
    - Legen Sie den Modus **Koexistenz** .
        - **Inseln** - verwenden Sie diese Einstellung, wenn Benutzer gleichzeitig beide Skype für Unternehmen und Teams verwenden können sollen.
        - **Für Unternehmen nur Skype** - verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur verwenden Skype für Business.
        - Nur Teams werden **nur Teams** - verwenden Sie diese Einstellung, wenn Sie die Benutzer verwenden möchten. Beachten Sie, dass selbst bei dieser Einstellung Benutzer weiterhin in Skype für Unternehmen gehostet Besprechungen teilnehmen können.
    - Legen Sie **Benachrichtigen Skype für Unternehmensbenutzer, Teams für das Upgrade verfügbar ist**. Wenn Sie diese aktivieren, informiert sie die Skype für Unternehmensbenutzer, dass sie die App Teams bald aktualisiert werden.
    - Legen Sie die **bevorzugte app für Benutzer Skype für Business Besprechungen beitreten**. Diese Einstellung bestimmt, welche app verwendet wird, für die Teilnahme an Skype für Business Besprechungen und ungeachtet des Werts der Koexistenzmodus berücksichtigt wird.
      - **Skype-Besprechungen-app**
      - **Skype für Unternehmen mit begrenzten features**
    - Legen Sie auf **die app Teams im Hintergrund für Skype für Unternehmensbenutzer herunterladen**.  Diese Einstellung downloads im Hintergrund die app Teams bei Benutzern, die auf Windows Skype für Unternehmen. Es wird berücksichtigt, wenn der Koexistenzmodus für den Benutzer nur Teams ist oder Benachrichtigungen über ausstehende in Skype für Unternehmen aktiviert sind.
3. Klicken Sie auf **Speichern** , nachdem Sie die Änderungen vorgenommen haben.

## <a name="setting-upgrade-options-for-a-single-user-in-your-organization"></a>Festlegen von Optionen für einen einzelnen Benutzer in Ihrer Organisation für upgrade

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich besuchen Sie **Benutzer**, und wählen Sie dann den Benutzer aus der Liste aus. 
2. Klicken Sie auf der Registerkarte **Konto** für den Benutzer unterhalb von **Teams zu aktualisieren**auf **Bearbeiten**.
- Sie können die **Koexistenz-Modus**festlegen. Wählen Sie die folgenden Optionen aus:
    - **Verwendung Org geltende Einstellungen** - verwenden Sie diese Einstellung, wenn der Benutzer die Einstellungen in den Einstellungen für die **gesamte Org** verwenden soll. 
    - **Inseln** - verwenden Sie diese Einstellung, wenn der Benutzer auf beide Skype für Unternehmen und Teams verwenden können soll. 
    - **Für Unternehmen nur Skype** - verwenden Sie diese Einstellung, wenn der Benutzer für Business Skype verwenden soll. 
    - Nur Teams werden **nur Teams** - verwenden Sie diese Einstellung, wenn Sie den Benutzer verwenden möchten. Der Benutzer wird weiterhin Skype für Business-Besprechungen teilnehmen können.
3. Wenn Sie eine beliebige **Koexistenzmodus** als **Verwendung Org geltende Einstellungen**auswählen, müssen Sie die Option zum Aktivieren von Benachrichtigungen in Skype des Benutzers für Geschäfts-app, die auf Teams aktualisieren bald verfügbar ist. Sie können diese Benachrichtigung für den Benutzer aktivieren, durch die Option **Benachrichtigen der Skype für Geschäftsbenutzer** einschalten.
4. Klicken Sie auf **Speichern** , nachdem Sie die Änderungen vorgenommen haben.

### <a name="related-topics"></a>Verwandte Themen
[Planen der Weg](upgrade-plan-journey.md)

[Grundlegendes zu Koexistenz und Aktualisieren von Weg für Skype für Unternehmen und Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Hinweise zur Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)
