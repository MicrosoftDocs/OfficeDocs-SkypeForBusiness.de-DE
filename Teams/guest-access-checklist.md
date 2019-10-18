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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83cd25ed9f675f04f090255cbc387275c0dee90d
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253918"
---
<a name="teams-guest-access-checklist"></a>Checkliste für den Teams-Gastzugriff
==========================================

Verwenden Sie diese Checkliste, um die Gastzugriffs-Funktionen in Microsoft Teams gemäß den Präferenzen Ihrer Organisation einzurichten und zu konfigurieren.

> [!NOTE] 
> Informationen zu Einschränkungen für die Zusammenarbeit finden Sie unter [Einrichten der externen B2B-Zusammenarbeit und verwalten, wer Gäste einladen kann](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="understand-the-limitations-for-guests"></a>Grundlegendes zu den Einschränkungen für Gäste

Die Gastumgebung hat Beschränkungen, die beabsichtigt sind. Stellen Sie sicher, dass Sie die Gastumgebung verstehen, damit Sie nicht versuchen, ein Problem zu beheben, das keines ist. Hier finden Sie beispielsweise eine Liste der Funktionen, die für einen Gast in Microsoft Teams nicht verfügbar sind:

- OneDrive for Business
- Personensuche außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungsdetails
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen oder Überarbeiten eines Teams
- Suche nach Teams
- Hochladen von Dateien in einen persönlichen Chat
- Gäste können weiterhin Benutzer (außerhalb Ihres Teams) suchen und finden, wenn Sie die vollständige e-Mail-ID des Benutzers kennen. Um das zu verhindern, können IT-Administratoren Muster wie den [Umfang der Verzeichnissuche](https://docs.microsoft.com/de-DE/MicrosoftTeams/teams-scoped-directory-search) verwenden, die Gäste auf Ihre eigene virtuelle GAL beschränken können.

Weitere Details finden Sie unter [Gastfunktionalität](guest-experience.md) und [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

### <a name="guest-access-vs-external-access-federation"></a>Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> Derzeit unterstützt Microsoft Teams nicht die Rolle „Gasteinladender“. Mindestens die Umschaltfläche „Mitglieder können einladen“ muss auf „Ja“ festgelegt werden, damit der Gastzugriff in Microsoft Teams funktioniert. Wenn Sie „Mitglieder können einladen“ auf „Nein“ festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern. Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenzfehler sehen

Für den Gastzugriff in Microsoft Teams wird Azure Active Directory (Azure AD) Business-to-Business (B2B) und dessen Lizenzierungsmodell genutzt. Wenn Sie auf Lizenzfehler stoßen, lesen Sie bitte die [B2B-Lizenzierungsanleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance), um die Lizenzierungsanforderungen Ihrer Organisation zu verstehen und sicherzustellen, dass Ihre Benutzer Gäste in Ihre Organisation einladen können.

Einige Dinge, die Sie beachten sollten:

- Gäste sind Benutzer außerhalb Ihrer Organisation. Ihre Mitarbeiter, Auftragnehmer oder Agenten vor Ort usw. können nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Partner.
- Gastlizenzen werden für die einladende Organisation gezählt. Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.
- Lizenzen werden gegen Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□  Schritt 1: Konfigurieren von Einstellungen in Azure AD Business-to-Business

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
   
   - **Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.
   - **Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).

   - **Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
    
## <a name="-step-2-configure-office-365-groups"></a>□ Schritt 2: Konfigurieren von Office 365-Gruppen

1. Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Dienste und Add-Ins** > **Office 365-Gruppen**.
2. Stellen Sie sicher, dass **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** auf **Ein** gestellt ist. Wenn diese Einstellung deaktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.
3. Stellen Sie sicher, dass **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **Ein** gestellt ist. Wenn diese Einstellung deaktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen. Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)

Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Schritt 3: Aktivieren des Gastzugriffs auf Mandantenebene

Sie müssen im **Microsoft Teams Admin Center** mindestens den Gastzugriff für Microsoft Teams aktivieren. 

1. Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.
2. Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. Konfigurieren Sie auf dieser Seite alle anderen für Sie erforderlichen Gasteinstellungen.
4. Klicken Sie auf **Speichern**.

Detaillierte Anweisungen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Schritt 4: Konfigurieren der Freigabe in Office 365 

Stellen Sie sicher, dass Benutzer Gäste hinzufügen können. Dazu gehen Sie so vor:

1. Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Diese Einstellung entspricht der Einstellung **Mitglieder können einladen** in  **Benutzereinstellungen** > **Externe Benutzer**  in Azure AD.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Schritt 5: Überprüfen der Freigabeeinstellung in SharePoint

1. Melden Sie sich beim Microsoft 365 Admin Center an.
2. Klicken Sie auf **Admin Center** und wählen Sie dann **SharePoint** aus.
3. Wählen Sie im SharePoint Admin Center **Freigabe** aus.
4. Vergewissern Sie sich, dass die Option für **Freigabe außerhalb Ihrer Organisation nicht zulassen** *nicht* aktiviert ist.
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter von Einstellungen in SharePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Schritt 6: Aktivieren spezifischer Einstellungen für Kanäle 

Konfigurieren Sie in der Teams-Anwendung die Gastberechtigungen auf der einzelnen Teamebene so, dass Gäste Kanäle erstellen, aktualisieren und löschen können. Neben den Administratoren können Teambesitzer diese Einstellung konfigurieren.

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

Weitere Informationen sowie Anleitungsvideos finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).


## <a name="troubleshooting"></a>Problembehandlung

Solten Sie Probleme beim Hinzufügen von Gästen in Microsoft Teams haben, lesen Sie den [Leitfaden zur Problembehandlung bei Gastzugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


