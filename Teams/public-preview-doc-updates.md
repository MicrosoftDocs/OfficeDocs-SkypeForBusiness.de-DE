---
title: Öffentliche Vorschau in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
description: 'Erfahren Sie mehr über die öffentliche Vorschau in Microsoft Teams. Testen Sie neue Features, und senden Sie Feedback.'
appliesto:
  - Microsoft Teams
ms.localizationpriority: high
---

# <a name="microsoft-teams-public-preview"></a>Public Preview für Microsoft Teams

> [!NOTE] 
> Die in der Vorschau enthaltenen Features sind möglicherweise nicht vollständig und könnten geändert werden, bevor sie im öffentlichen Release verfügbar gemacht werden. Sie werden nur zu Evaluierungs- und Untersuchungszwecken bereitgestellt. Die Vorschau-Features werden in Office 365 Government Community Cloud (GCC) nicht unterstützt.

Public Preview für Microsoft Teams bietet frühzeitigen Zugriff auf unveröffentlichte Features in Microsoft Teams. Über die Preview können Sie bevorstehende Features erkunden und testen. Wir freuen uns über Ihr Feedback zu jedem Feature in öffentlichen Vorschauen. Public Preview wird auf Ebene des einzelnen Microsoft Teams-Benutzers aktiviert, daher müssen Sie sich keine Gedanken über etwaige Auswirkungen auf die gesamte Organisation machen.

Eine Liste der verfügbaren Funktionen in der öffentlichen Vorschau von Microsoft Teams finden Sie unter [Technische Hinweise zu Microsoft Teams Public Preview](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [Versionshinweise zu Microsoft Teams-Administratorfunktionen](/OfficeUpdates/teams-admin) und [Neuerungen in Microsoft Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).

## <a name="set-the-update-policy"></a>Festlegen der Updaterichtlinie

Die öffentliche Vorschau wird auf Ebene des einzelnen Benutzers aktiviert, und die Option zum Aktivieren der öffentlichen Vorschau wird über eine Administratorrichtlinie gesteuert. Updaterichtlinien werden zur Verwaltung der Microsoft Teams- und Office-Vorschau-Benutzer verwendet, die Features von Vorabversionen oder Vorschauen in der Microsoft Teams-App sehen. Sie können die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden und anpassen bzw. eine oder mehrere benutzerdefinierte Richtlinien für Ihre Benutzer erstellen. Die Richtlinie muss bestimmten Benutzern zugewiesen werden, da sie die globale Richtlinie nicht außer Kraft setzt.

1. Melden Sie sich beim [Admin Center für Microsoft Teams](https://admin.teams.microsoft.com/) an.

2. Wählen **Teams** > **Teams-Updaterichtlinien** aus.

1. Wählen Sie **Hinzufügen** aus, um eine neue Richtlinie zu erstellen, oder bearbeiten Sie eine vorhandene Richtlinie, um **Updaterichtlinie** zu öffnen.

2. Benennen Sie die Updaterichtlinie, fügen Sie eine Beschreibung hinzu, und wählen Sie die Einstellung **Vorschaufeatures anzeigen** aus.

   -   **Office Preview folgen** (Standard): Diese neue Standardoption aktiviert automatisch Microsoft Teams Public Preview-Features für alle Benutzer, die im aktuellen Office-Kanal (Vorschau) registriert sind. Der Endbenutzer muss keine weiteren Aktionen ausführen.
   -   **Aktiviert**: Mit dieser Option wird Microsoft Teams Public Preview unabhängig davon aktiviert, ob ein Benutzer im aktuellen Office-Kanal (Vorschau) registriert ist. Der Endbenutzer muss außerdem ein Opt-in für die öffentliche Vorschau von Microsoft Teams in seiner Microsoft Teams-App durchführen.

   > [!NOTE]  
   > Für vorhandene Benutzer in Microsoft Teams Public Preview, die NICHT im **Aktuellen Kanal (Vorschau)** registriert sind, müssen IT-Administratoren von der Standardeinstellung **Office Preview folgen** zu **Aktiviert** wechseln.
 
   - **Nicht aktiviert**: Microsoft Teams Public Preview-Features stehen Endbenutzern nicht zur Verfügung.

    ![zeigt das Dialogfenster "Vorschaueinstellungen" an.](media/public-preview-policy.png)  

Sie können die Richtlinie auch mit dem `Set-CsTeamsUpdateManagementPolicy`-Cmdlet von PowerShell mit dem Parameter `-AllowPublicPreview` festlegen.

> [!NOTE]   
> Der AllowPreview-Parameter wird bald als veraltet verworfen.

## <a name="enable-public-preview"></a>Aktivieren der öffentlichen Vorschau

Wenn Sie die öffentliche Vorschau auf einem Desktop- oder Webclient aktivieren möchten, müssen Sie die folgenden Aufgaben ausführen:

1. Wählen Sie die drei Punkte links neben Ihrem Profil aus, um das Menü „Teams“ anzuzeigen.
2. Wählen Sie **Info** > **Public Preview** aus.
3. Wählen Sie **Zur Public Preview wechseln** aus.

> [!NOTE]  
> Diese Option ist nur verfügbar, wenn **Vorschaufeatures anzeigen** auf **Aktiviert** festgelegt ist.

## <a name="teams-now-follows-office-preview-users"></a>Microsoft Teams folgt jetzt Office Preview-Benutzern

Die neue globale standardmäßige Richtlinieneinstellung **Office Preview folgen** ermöglicht Benutzern, sich automatisch im Public Preview-Kanal von Microsoft Teams zu befinden, wenn sie sich im aktuellen Kanal (Vorschau) für den Office 365-Client unter Windows befinden.

Microsoft Office erhält weiterhin Updates aus dem aktuellen Kanal (Vorschau), und der Microsoft Teams-Client erhält Updates über den Public Preview-Kanal. Durch diese Richtlinie werden KEINE Office-Kanäle basierend auf Microsoft Teams-Kanälen gewechselt. 

**Wie können Sie Ihre vorhandenen Microsoft Teams-Vorschaubenutzer beibehalten, die den aktuellen Kanal (Vorschau) für Office NICHT verwenden?**

Für vorhandene Benutzer, die ein Opt-in oder Opt-out für Microsoft Teams Public Preview vornehmen dürfen und diese Einstellung in ihrer aktuellen Form beibehalten möchten, müssen Sie von der neuen Standardeinstellung **Office Preview folgen** zu **Aktiviert** wechseln (siehe [Festlegen der Updaterichtlinie](#set-the-update-policy)).

**Wie kann ich diese Einstellung deaktivieren?**

Sie können die Einstellung im Microsoft Teams Admin Center von **Office Preview folgen** auf **Nicht aktiviert** ändern (siehe [Festlegen der Updaterichtlinie](#set-the-update-policy)).

## <a name="known-issues"></a>Bekannte Probleme

Benutzer des aktuellen Kanals (Vorschau) für Office können Microsoft Teams Public Preview über das Menü "Info" des Microsoft Teams-Clients beenden, während ihre Updaterichtlinie auf **Office Preview folgen** festgelegt ist. Diese Funktionalität ist nicht vorgesehen und wird in Zukunft entfernt. Der Microsoft Teams-Client kann sich automatisch wieder auf Public Preview einstellen, wenn sich das Gerät das nächste Mal im Leerlauf befindet, wenn sich der Benutzer im aktuellen Kanal (Vorschau) für Office befindet.

## <a name="related-topics"></a>Verwandte Themen

[Öffentliche Entwicklervorschau](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
