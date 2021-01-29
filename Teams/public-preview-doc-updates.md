---
title: Öffentliche Vorschau in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die öffentliche Vorschau in Microsoft Teams. Testen Sie neue Features, und senden Sie Feedback.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043959"
---
# <a name="microsoft-teams-public-preview"></a>Public Preview für Microsoft Teams

> [!NOTE]
> Die in der Vorschau enthaltenen Features sind möglicherweise nicht vollständig und können geändert werden, bevor sie im öffentlichen Release verfügbar gemacht wird. Sie werden nur zu Evaluierungs- und Untersuchungszwecken bereitgestellt.

Public Preview für Microsoft Teams bietet frühzeitigen Zugriff auf unveröffentlichte Features in Teams. Mit der Vorschau können Sie bevorstehende Features untersuchen und testen. Wir freuen uns über Ihr Feedback zu jedem Feature in öffentlichen Vorschauen. Public Preview wird pro Teams-Benutzer aktiviert, daher müssen Sie sich keine Gedanken über die Auswirkungen auf die gesamte Organisation machen.

Eine Liste der in der Public Preview für Teams verfügbaren Informationen finden Sie unter [Versionshinweise für den aktuellen Office-Kanal (Vorschau)](https://docs.microsoft.com/officeupdates/current-channel-preview).

## <a name="set-the-update-policy"></a>Festlegen der Updaterichtlinie

Public Preview wird auf Benutzerbasis aktiviert, und die Option zum Aktivieren von Public Preview wird in einer Administratorrichtlinie gesteuert. Updaterichtlinien werden zur Verwaltung der Teams- und Office-Vorschaubenutzer verwendet, die Features von Vorabversionen oder Vorschauen in der Teams-App sehen. Sie können die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden und anpassen, oder eine oder mehrere benutzerdefinierte Richtlinien für Ihre Benutzer erstellen. Die Richtlinie muss bestimmten Benutzern zugewiesen werden, da sie die globale Richtlinie nicht überschreibt.

1. Melden Sie sich beim Admin Center an.
2. Wählen Sie **Teams**>**Updaterichtlinien** aus.

   ![Auswählen der Option "Updaterichtlinien"](media/updatePolicies.png)

3. Klicken Sie auf **Hinzufügen**.
4. Benennen Sie die Updaterichtlinie, fügen Sie eine Beschreibung hinzu, und aktivieren Sie **Vorschaufeatures anzeigen**.

Sie können die Richtlinie auch mit dem `CsTeamsUpdateManagementPolicy`-Cmdlet von PowerShell festlegen.

## <a name="enable-public-preview"></a>Aktivieren der öffentlichen Vorschau

Wenn Sie die öffentliche Vorschau auf einem Desktop- oder Webclient aktivieren möchten, müssen Sie die folgenden Aufgaben ausführen:

1. Wählen Sie Ihr Profil aus, um das Teams-Menü anzuzeigen.
2. Wählen Sie **Info** → **Public Preview** aus.
3. Wählen Sie **Zur Public Preview wechseln** aus.

## <a name="related-topics"></a>Verwandte Themen

[Öffentliche Entwicklervorschau](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

