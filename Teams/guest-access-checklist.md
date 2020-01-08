---
title: Checkliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962533"
---
<a name="microsoft-teams-guest-access-checklist"></a>Checkliste für den Microsoft Teams-Gastzugriff
==========================================

Verwenden Sie diese Checkliste, damit Sie den Gastzugriff in Microsoft Teams aktivieren und konfigurieren können. Sie müssen ein globaler Administrator oder ein Teamadministrator sein, um diese Änderungen vornehmen zu können.

> [!IMPORTANT]
> Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 

Schauen Sie sich dieses kurze Video (5:31 Minuten) an, um zu erfahren, wie Sie den Gastzugriff in Microsoft 365, einschließlich Teams, aktivieren können.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Schritt 1: Aktivieren des Gastzugriffs auf der organisationsweiten Ebene von Teams

Wenn Sie den Gastzugriff aktivieren möchten, wechseln Sie zum **Microsoft Teams Admin Center**. 

1. Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.
2. Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. Aktivieren oder deaktivieren Sie auf dieser Seite die Einstellungen für **Anrufe**, **Besprechungen**und nach **richten** für Gäste.
4. Klicken Sie auf **Speichern**.

> [!TIP]
> Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Office 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen. In diesem Fall können Sie die restlichen Schritte überspringen. Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Office 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Schritt 2: Konfigurieren von Azure AD Business-to-Business-Einstellungen

1. Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.
3. Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.
   > [!NOTE]
   > Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen. Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.
4. Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.

    - **Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis. Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren. Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.
     - **Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.
     - **Mitglieder können einladen**: Damit Mitglieder Ihres Verzeichnisses, die nicht Administratoren sind, Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.

         > [!NOTE]
         > Wenn Sie **Mitglieder können einladen** auf **Nein** festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern. Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).
         > [!IMPORTANT]
         > Damit der Gastzugriff in Teams funktioniert, müssen Sie **Mitglieder können einladen** auf **Ja** festlegen.   
     - **Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.
         > [!IMPORTANT]
         > Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.
     - **Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Informationen zu Einschränkungen der Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
    Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Schritt 3: Konfigurieren von Office 365-Gruppen

1. Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Services #a0-Add-ins**, und wählen Sie dann **Office 365-Gruppen**aus.

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)
2. Stellen Sie sicher, dass das Kontrollkästchen **Gruppenmitglieder außerhalb des Organisations Zugriffs auf Gruppeninhalte zulassen** aktiviert ist. Wenn diese Einstellung nicht aktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.
3. Stellen Sie sicher, dass das Kontrollkästchen **Gruppenbesitzer Personen außerhalb des Unternehmens hinzufügen** aktiviert ist. Wenn diese Einstellung nicht aktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen. Diese Einstellung muss mindestens aktiviert sein, um den Gastzugriff zu unterstützen.

Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="step-4-configure-sharing-in-office-365"></a>Schritt 4: Konfigurieren der Freigabe in Office 365 

Stellen Sie sicher, dass Benutzer Gäste hinzufügen können. Dazu gehen Sie so vor:

1. Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Wählen Sie unter **Admin Center**die Option **SharePoint**aus.
3. Wählen Sie im neuen SharePoint Admin Center unter **Websites**die Option **aktive Websites**aus.

    ![Aktive Websites im SharePoint Admin Center](media/guest-access-checklist-SPOSettings0.png)

3. Wählen Sie die Website aus, und klicken Sie dann auf **Freigabe**.
4. Stellen Sie sicher, dass die Option auf **jeder** oder **neuen und vorhandenen Gästen**festgesetzt ist.
 
     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für SharePoint Online-Einstellungen](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Schritt 6: Einrichten von Gastbenutzer Berechtigungen

Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, die Steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können. Teams-Administratoren und Teambesitzer können diese Einstellungen konfigurieren.

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).


## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams haben, verwenden Sie diese Ressourcen, um Ihnen zu helfen:

[Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams](troubleshoot-guest-access.md)

[Problembehandlung für Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



