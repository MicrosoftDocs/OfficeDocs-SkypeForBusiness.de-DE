---
title: Prüfliste für den Microsoft Teams-Gastzugriff
author: romanma
ms.author: romanma
manager: serdars
ms.date: 11/09/18
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Prüfliste, um Gastzugriff in Microsoft Access-Teams Gast einrichten.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4051c2db43f3aa1cdb2d26af07076496c4838a94
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674489"
---
<a name="teams-guest-access-checklist"></a>Teams Gast Access Prüfliste
==========================================

Verwenden Sie diese Prüfliste, mit denen Sie aktivieren und Konfigurieren des Gast Access-Features in Microsoft-Teams gemäß den Anforderungen Ihrer Organisation.

## <a name="understand-the-limitations-for-guests"></a>Verstehen der Grenzen für Gäste

Die Erfahrung Gast hat Einschränkungen Verhalten ist erwünscht. Stellen Sie sicher, dass die Erfahrung Gast verstehen, damit Sie nicht versuchen zu reparieren, die ein Problem nicht zur Verfügung. Hier wird beispielsweise eine Liste einiger Funktionen, die nicht an einen Gast in Microsoft-Teams zur Verfügung steht:

- OneDrive für Unternehmen
- Suche nach Personen außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungsdetails
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen Sie oder ändern Sie ein team
- Wechseln Sie für ein team
- Hochladen von Dateien in einer Person chat

Weitere Informationen finden Sie unter [Was die Erfahrung Gast entspricht](guest-experience.md) und [Gast Access in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).

## <a name="if-your-guests-are-seeing-license-errors"></a>Wenn Ihre Gäste Lizenz Fehlermeldungen angezeigt werden

Gast Access in Microsoft-Teams verwendet Azure Active Directory-Business, Business (B2B) und seine Lizenzierungsmodell. Wenn Sie die Lizenzierung Fehler angezeigt werden, stellen Sie sicher, lesen die Lizenzierung B2B-Anweisungen, um die Lizenzierung Anforderungen vertraut zu machen, die Ihre Organisation verfügt, damit Ihre Benutzer Gäste zu Ihrer Organisation einladen können.

Einige Dinge bedenken:

- Für jede Azure AD-Lizenz, die Sie einem Benutzer zuweisen kostenpflichtige, können die Benutzer bis zu fünf Gastbenutzer unter der Vergütung für externe Benutzer einladen.
- Gäste sind Benutzer außerhalb Ihrer Organisation. Ihre Mitarbeiter, Auftragnehmer vor Ort, vor-Ort-Agents und usw. können nicht als Gäste hinzugefügt werden. Das gleiche gilt für Ihre Erwerbs.
- Gast Lizenzen gegen die Organisation einladen, werden gezählt. Berücksichtigen Sie dies, wenn Sie die Anzahl der Lizenzen berechnen, die Sie benötigen.
- Ob die eingeladene Gäste aus einer anderen Office 365-Mandanten stammen oder ihre persönlichen e-Mail-Adressen verwenden, werden anhand Ihrer Organisation Lizenzen gezählt.

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a>□ Schritt 1: Konfigurieren von Einstellungen in Azure AD-B2B

1. Melden Sie sich bei https://portal.azure.com.
2. Klicken Sie im linken Bereich auf **Azure Active Directory** .
3. Klicken Sie unter **Verwalten**auf **benutzereinstellungen**.
4. Klicken Sie unter **externe Benutzer**klicken Sie auf **Einstellungen für externe verwalten für die Zusammenarbeit**.
5. Klicken Sie auf der Seite **Einstellungen für die externe Zusammenarbeit** sicherstellen Sie, dass **Mitglieder können einladen** auf **Ja**festgelegt ist.

      ![Screenshot zeigt ein Beispiel für eine Umschaltfläche AAD Einstellungen. ](media/guest-access-checklist-AADSettings1.png)

    Zur Unterstützung der Gäste müssen **Mitglieder können einladen** auf **Ja**festgelegt werden. 
   
> [!NOTE] 
> Wenn Sie auf **Nein** festlegen **Mitglieder einladen können** und anschließend Gast Access in Office 365-Gruppen und Microsoft-Teams aktivieren, können Administratoren Gast Einladungen an Ihr Verzeichnis steuern. Nachdem Gäste im Verzeichnis vorhanden sind, können sie Teams von Membern von nicht-Administrator hinzugefügt werden, die Eigentümer Team sind.

Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).


## <a name="-step-2-configure-office-365-groups"></a>□ Schritt 2: Konfigurieren von Office 365-Gruppen

1. Wechseln Sie in der Microsoft-365-Verwaltungskonsole zu **Einstellungen** > **Services & -Add-ins** > **Office 365-Gruppen**.
2. Stellen Sie sicher, dass **Let Gruppenmitglieder außerhalb der Organisation Access Gruppe Inhalt** auf **aktiviert**festgelegt ist. Wenn diese Einstellung deaktiviert ist, werden nicht Gäste auf eine beliebige Gruppe Inhalte zugreifen.
3. Stellen Sie sicher, dass **Let Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **aktiviert**festgelegt ist. Wenn diese Einstellung deaktiviert ist, werden nicht Besitzer Team neue Gäste hinzufügen können. Diese Einstellung muss mindestens bei Support Gast Access.

     ![Screenshot zeigt die Office 365 Gruppen schaltet](media/guest-access-checklist-office365.png)

Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten Gast Benutzerzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und im Abschnitt "Office 365 Groups" im [Autorisieren Gast Access in Microsoft-Teams](Teams-dependencies.md).
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a>□ Schritt 3: Aktivieren des Zugriffs auf der Ebene der Mandant Gast

Zumindest müssen Sie Microsoft-Teams, für alle Benutzer des Lizenztyps **Gast**aktivieren. 

1. Wählen Sie in der Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **Gastzugriff**.
2. Legen Sie die Option **Zulassen Gast Access in Microsoft-Teams** auf **aktiviert**.

    ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Teams Einstellungen](media/set-up-guests-image1.png)

3. Klicken Sie auf der gleichen Seite konfigurieren Sie alle anderen Gast-Einstellungen, die Sie benötigen.
4. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Gastzugriff auf Microsoft-Teams](set-up-guests.md).


## <a name="--step-4-configure-sharing-in-office-365"></a>□ Schritt 4: Konfigurieren der Freigabe von in Office 365 

Stellen Sie sicher, dass Benutzer Gäste hinzufügen können. Hier ist wie:

1. Wechseln Sie in der Microsoft-365-Verwaltungskonsole zu **Einstellungen** > **Sicherheit und Datenschutz**.

     ![Screenshot zeigt ein Beispiel einer Services-Einstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Wählen Sie in der **Freigabe** **Bearbeiten**.

     ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Legen Sie **dazu, Benutzern das Hinzufügen von neuen Gäste auf diese Organisation** auf **aktiviert**, und klicken Sie dann auf **Speichern**.

     ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> Diese Einstellung entspricht der Einstellung **Mitglieder einladen können** in **benutzereinstellungen** > **externe Benutzer** in Azure Active Directory.  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a>□ Schritt 5: Überprüfen Sie die Freigabe Einstellung in SharePoint

1. Melden Sie sich beim Office 365 Admin Center an.
2. Klicken Sie auf **Administrationscenter**, und wählen Sie dann **SharePoint**aus.
3. Wählen Sie in der SharePoint-Verwaltungskonsole **Freigabe**.
4. Stellen Sie sicher, dass die Option für **nicht zulassen Freigabe außerhalb Ihrer Organisation** *nicht* ausgewählt ist.
 
     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Sparepoint Online-Einstellungen.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a>□ Schritt 6: Aktivieren Sie bestimmte Einstellungen für Kanäle 

Konfigurieren Sie in der Anwendung Teams auf Ebene der einzelnen Teams Gastberechtigungen, sodass Gäste erstellen, aktualisieren und Löschen von Kanäle können. Zusätzlich zur-Administratoren können Team Besitzer dieser Einstellung konfigurieren.

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Team/Channel-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)

Weitere Informationen, einschließlich videoanleitungen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).


## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie Probleme beim Hinzufügen von Gäste in Microsoft-Teams haben, finden Sie im [Handbuch zur Problembehandlung für Gast Zugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


