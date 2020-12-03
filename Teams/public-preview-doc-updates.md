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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530982"
---
# <a name="microsoft-teams-public-preview"></a>Public Preview für Microsoft Teams

> [!NOTE]
> Die in der Vorschau enthaltenen Features sind möglicherweise nicht vollständig und können geändert werden, bevor sie im öffentlichen Release verfügbar gemacht wird. Sie werden nur zu Evaluierungs- und Untersuchungszwecken bereitgestellt.

Public Preview für Microsoft Teams bietet frühzeitigen Zugriff auf unveröffentlichte Features in Teams. Mit der Vorschau können Sie bevorstehende Features untersuchen und testen. Wir freuen uns über Ihr Feedback zu jedem Feature in öffentlichen Vorschauen. Die öffentliche Vorschau ist für jeden Teams-Benutzer aktiviert, daher müssen Sie sich keine Gedanken über die Auswirkungen auf die gesamte Organisation machen.

## <a name="set-the-update-policy"></a>Festlegen der Updaterichtlinie

 Die öffentliche Vorschau ist für jeden Benutzer aktiviert, und die Option zum Aktivieren der öffentlichen Vorschau wird in einer Administratorrichtlinie gesteuert. Updaterichtlinien werden zur Verwaltung der Teams- und Office-Vorschaubenutzer verwendet, die Features von Vorabversionen oder Vorschauen in der Teams-App sehen. Sie können die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden und anpassen, oder eine oder mehrere benutzerdefinierte Richtlinien für Ihre Benutzer erstellen. Die Richtlinie muss bestimmten Benutzern zugewiesen werden, da sie die globale Richtlinie nicht überschreibt.

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
