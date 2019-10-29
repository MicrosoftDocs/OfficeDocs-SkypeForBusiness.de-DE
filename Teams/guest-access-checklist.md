---
title: Checkliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
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
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753320"
---
<a name="microsoft-teams-guest-access-checklist"></a>Checkliste für den Microsoft Teams-Gastzugriff
==========================================

Verwenden Sie diese Checkliste, damit Sie den Gastzugriff in Microsoft Teams aktivieren und konfigurieren können.

> [!IMPORTANT]
> Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 



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
       > Damit Gastzugriff überhaupt in Teams funktioniert, müssen Sie die **Mitglieder können** auf **Ja**einladen einstellen.   
   - **Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.
       > [!IMPORTANT]
       > Derzeit unterstützt Teams die Rolle "gastinviter" nicht, daher können Gäste keine anderen Gäste in Teams einladen, selbst wenn Sie die Möglichkeit haben, die Gäste zu " **Ja**" **einzuladen** .
   - **Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
   - **Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
      > [!NOTE]
      > Informationen zu Einschränkungen der Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Schritt 3: Konfigurieren von Office 365-Gruppen

1. Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Dienste und Add-Ins** > **Office 365-Gruppen**.
2. Stellen Sie sicher, dass **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** auf **Ein** gestellt ist. Wenn diese Einstellung deaktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.
3. Stellen Sie sicher, dass **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **Ein** gestellt ist. Wenn diese Einstellung deaktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen. Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)

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

Das hier ist ein bisschen ein Rätsel. Gastzugriff in Teams funktioniert nicht, wenn im SharePoint Admin Center die Einstellung " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " aktiviert ist.

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Klicken Sie auf **Admin Center** und wählen Sie dann **SharePoint** aus.
3. Wählen Sie im SharePoint Admin Center **Freigabe** aus.
4. Vergewissern Sie sich, dass die Option für **Freigabe außerhalb Ihrer Organisation nicht zulassen** *nicht* aktiviert ist.
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter von Einstellungen in SharePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Schritt 6: Einrichten von Gastbenutzer Berechtigungen

Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, die Steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können. Teams-Administratoren und Teambesitzer können diese Einstellungen konfigurieren.

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).


## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams haben, verwenden Sie diese Ressourcen, um Ihnen zu helfen:

[Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams](troubleshoot-guest-access.md)

[Problembehandlung für Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



