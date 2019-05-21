---
title: Prüfliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 833d79d16365a1b90e8cd35e88e43468f0e25fa8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280925"
---
<a name="teams-guest-access-checklist"></a>Checkliste für Teams-Gastzugriff
==========================================

Verwenden Sie diese Checkliste, damit Sie das Feature "Gastzugriff" in Microsoft Teams entsprechend den Einstellungen Ihrer Organisation aktivieren und konfigurieren können.

## <a name="understand-the-limitations-for-guests"></a>Grundlegendes zu den Einschränkungen für Gäste

Die Gast Erfahrung hat Einschränkungen durch Design. Stellen Sie sicher, dass Sie die Gastfreundlichkeit verstehen, damit Sie nicht versuchen, etwas zu beheben, das kein Problem ist. Nachfolgend finden Sie eine Liste mit einigen Funktionen, die einem Gast in Microsoft Teams nicht zur Verfügung stehen:

- OneDrive for Business
- Personen suchen außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungs Details
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen oder Überarbeiten eines Teams
- Suchen nach einem Team
- Hochladen von Dateien in einen Chat zwischen zwei Personen
- Gäste können weiterhin nach Benutzern außerhalb Ihres Teams suchen und diese finden, wenn Sie Ihre vollständige e-Mail-ID kennen. Um dies zu verhindern, können IT-Administratoren Muster wie [Bereichs Verzeichnissuche](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) verwenden, die die Möglichkeit haben, Gäste in Ihre eigene virtuelle GAL zu beschränken.

Weitere Informationen finden Sie unter [Was ist die Gastfreundlichkeit](guest-experience.md) und [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)?

### <a name="guest-access-vs-external-access-federation"></a>Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenzfehler sehen

Der Gastzugriff in Microsoft Teams verwendet Azure Active Directory Business to Business (B2B) und sein Lizenzierungsmodell. Wenn Lizenzierungsfehler angezeigt werden, lesen Sie unbedingt die B2B-Lizenzierungs Anleitung, um die Lizenzierungsanforderungen Ihrer Organisation zu verstehen, damit Ihre Benutzer Gäste in Ihre Organisation einladen können.

Ein paar Dinge, die Sie beachten sollten:

- Für jede kostenpflichtige Azure AD-Lizenz, die Sie einem Benutzer zuweisen, können Ihre Benutzer bis zu fünf Gastbenutzer unter dem Kontingent für externe Benutzer einladen.
- Gäste sind Benutzer außerhalb Ihrer Organisation. Ihre Mitarbeiter, Onsite-Vertragspartner, vor-Ort-Agents usw. können nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Affiliates.
- Gast Lizenzen werden gegen die einladende Organisation gezählt. Bedenken Sie dies, wenn Sie die Anzahl der benötigten Lizenzen berechnen.
- Lizenzen werden für Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Schritt 1: Konfigurieren von Einstellungen in Azure AD Business-to-Business

1. Anmelden beihttps://portal.azure.com
2. Klicken Sie im linken Bereich auf **Azure Active Directory** .
3. Klicken Sie unter **Verwalten**auf **Benutzereinstellungen**.
4. Klicken Sie unter **externe Benutzer**auf Einstellungen für die **externe Zusammenarbeit verwalten**.
5. Stellen Sie auf der Seite Einstellungen für die **externe Zusammenarbeit** sicher, dass **Mitglieder einladen** auf **Ja**eingestellt sind.

      ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Aad-Einstellungen. ](media/guest-access-checklist-AADSettings1.png)

    Um Gäste zu unterstützen, **können Mitglieder einladen** muss auf **Ja**eingestellt sein. 
   
> [!NOTE] 
> Wenn Sie festlegen, dass Mitglieder auf **Nein** **einladen** und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren können, können Administratoren Gast Einladungen in Ihrem Verzeichnis steuern. Nachdem sich die Gäste im Verzeichnis befinden, können Sie Teams von Mitgliedern des nicht-Administrators hinzugefügt werden, die Teambesitzer sind.

Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).


## <a name="-step-2-configure-office-365-groups"></a>□ Schritt 2: Konfigurieren von Office 365-Gruppen

1. Wechseln Sie im Microsoft 365 Admin Center zu **Settings** > **Services & Add-ins** > **Office 365-Gruppen**.
2. Stellen Sie sicher, dass **Gruppenmitglieder außerhalb des Organisations Zugriffsgruppen-Inhalts** auf **ein**gesetzt sind. Wenn diese Einstellung deaktiviert ist, können die Gäste nicht auf Gruppeninhalte zugreifen.
3. Stellen Sie sicher, dass **Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **ein**gesetzt ist. Wenn diese Einstellung deaktiviert ist, können Team Besitzer keine neuen Gäste hinzufügen. Diese Einstellung muss mindestens aktiviert sein, um den Gastzugriff zu unterstützen.

     ![Screenshot der Office 365 Groups-Umschalter](media/guest-access-checklist-office365.png)

Ausführliche Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und im Abschnitt "Office 365-Gruppen" unter Autorisieren des [Gastzugriffs in Microsoft Teams](Teams-dependencies.md).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Schritt 3: Aktivieren des Gastzugriffs auf Mandantenebene

Sie müssen mindestens den Gastzugriff für Microsoft Teams unter dem **Microsoft Teams Admin Center**aktivieren. 

1. Wählen Sie im Team Admin Center die Option **organisationsweite Einstellungen** > **Gastzugriff**aus.
2. Legen Sie die Option **Gastzugriff in Microsoft Teams zulassen** auf **aktiviert**.

    ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. Konfigurieren Sie auf dieser Seite alle anderen von Ihnen gewünschten Gast Einstellungen.
4. Klicken Sie auf **Speichern**.

Ausführliche Anweisungen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Schritt 4: Konfigurieren der Freigabe in Office 365 

Stellen Sie sicher, dass Benutzer Gäste hinzufügen können. Gehen Sie wie folgt vor:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.

     ![Screenshot zeigt ein Beispiel für Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Wählen Sie in **Freigabe**die Option **Bearbeiten**aus.

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Legen Sie zulassen, dass **Benutzer dieser Organisation neue Gäste hinzufügen** auf **ein**, und klicken Sie dann auf **Speichern**.

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint

1. Anmelden beim Microsoft 365 Admin Center.
2. Klicken Sie auf **Admin Center**, und wählen Sie dann **SharePoint**aus.
3. Wählen Sie im SharePoint Admin Center die Option **Freigabe**aus.
4. Stellen Sie sicher, dass die Option " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " *nicht* aktiviert ist.
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter für SparePoint Online-Einstellungen.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Schritt 6: Aktivieren bestimmter Einstellungen für Kanäle 

Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, damit Gäste Kanäle erstellen, aktualisieren und löschen können. Zusätzlich zu Administratoren können Teambesitzer diese Einstellung konfigurieren.

![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Team/Kanal-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)

Weitere Informationen, einschließlich Anleitungen zu Videos, finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).


## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie Probleme beim Hinzufügen von Gästen in Microsoft Teams haben, lesen Sie den [Leitfaden zur Problembehandlung für Gastzugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


