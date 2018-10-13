---
title: Microsoft-Teams Gast Access Prüfliste
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Verwenden Sie diese Prüfliste, um Gastzugriff in Microsoft Access-Teams Gast einrichten.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58dd3bb4e0f870cfcfff0f1297acdab7a82eb4a9
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546685"
---
<a name="teams-guest-access-checklist"></a>Teams Gast Access Prüfliste
==========================================

Verwenden Sie diese Prüfliste, mit denen Sie aktivieren und Konfigurieren des Gast Access-Features in Microsoft-Teams gemäß den Anforderungen Ihrer Organisation.




## <a name="--enable-guest-access-at-the-tenant-level"></a>□ Gast-Zugriff auf der Ebene der Mandant aktivieren

Wechseln Sie zu der Teams & Skype für Business-Verwaltungskonsole über https://admin.teams.microsoft.com. Wählen Sie hier "Org geltende Settings", und wählen Sie die Registerkarte "Gastzugriff" und schließlich auf dieser Registerkarte wählen Sie 'Zulassen Gast Access in Microsoft-Teams' auf aktiviert. 

## <a name="need-a-new-screenshot-for-new-admin-center-enablement"></a>Benötigen Sie einen neuen Screenshot zum neuen Admin Center-Aktivierung. 

## <a name="-enable-specific-settings-for-channels"></a>□ bestimmte Einstellungen für Kanäle aktivieren 
Konfigurieren Sie in der Anwendung Teams auf Ebene der einzelnen Teams Gastberechtigungen, sodass Gäste erstellen, aktualisieren und Löschen von Kanäle können. Zusätzlich zur-Administratoren können Team Besitzer dieser Einstellung konfigurieren.

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Team/Channel-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)


Weitere Informationen, einschließlich videoanleitungen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).



## <a name="--configure-sharing-in-office-365"></a>□ Konfigurieren der Freigabe von in Office 365 

□ Stellen Sie sicher, dass Benutzer Gäste hinzufügen können. Hier ist wie:

1. Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Sicherheit und Datenschutz**.
![Screenshot zeigt ein Beispiel einer Services-Einstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)
1. Wählen Sie in der **Freigabe** **Bearbeiten**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen Bearbeiten-Schaltfläche](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
2. Legen Sie **dazu, Benutzern das Hinzufügen von neuen Gäste auf diese Organisation** auf **aktiviert**, und klicken Sie dann auf **Speichern**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 

 > [!NOTE]
> Diese Einstellung entspricht der Einstellung **Mitglieder einladen können** in benutzereinstellungen > externe Benutzer in Azure AD.  




## <a name="-configure-office-365-groups"></a>□ Konfigurieren von Office 365-Gruppen

Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Services & -Add-ins** > **Office 365-Gruppen**.

Stellen Sie sicher, dass **Let Gruppenmitglieder außerhalb der Organisation Access Gruppe Inhalt** auf **aktiviert**festgelegt ist. Wenn diese Einstellung deaktiviert ist, werden nicht Gäste auf eine beliebige Gruppe Inhalte zugreifen.

Stellen Sie sicher, dass **Let Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **aktiviert**festgelegt ist. Wenn diese Einstellung deaktiviert ist, werden nicht Besitzer Team neue Gäste hinzufügen können. Mindestens muss diese Einstellung für die Unterstützung Gast Zugriffs "auf" sein.

Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie im Abschnitt "Office 365 Groups" im [Autorisieren Gast in Microsoft-Teams](Teams-dependencies.md) und [Zulassen/Blockieren Gastzugriff auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=869658).
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a>□ Configure Settings in Azure AD Business-to-Business (B2B)
1. Melden Sie sich bei https://portal.azure.com.
2. Klicken Sie im linken Bereich auf **Azure Active Directory** .
3. Klicken Sie unter **Verwalten**auf **benutzereinstellungen**.
4. Klicken Sie unter **externe Benutzer**klicken Sie auf **Einstellungen für externe verwalten für die Zusammenarbeit**
5. Klicken Sie auf der Seite **Einstellungen für die externe Zusammenarbeit** sicherstellen Sie, dass **Mitglieder können einladen** auf **Ja**festgelegt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche AAD Einstellungen. ](media/guest-access-checklist-AADSettings1.png)

    

► Mindestens Gäste unterstützen, müssen **Mitglieder einladen können** auf **Ja**festgelegt werden.

> > [!NOTE]
> > Wenn Sie auf **Nein** **können Mitglieder einladen festlegen** und Gastzugriff in Office 365-Gruppen und Microsoft-Teams, aktivieren, können Administratoren Gast Einladungen an Ihr Verzeichnis steuern. Nachdem das Verzeichnis Gäste sind, können sie Teams von nicht-Administrator Membern (Team Besitzer) hinzugefügt werden.


Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).







## <a name="-verify-sharing-setting-in-sharepoint"></a>□ Verify sharing Einstellung in SharePoint
1. Melden Sie sich beim Office 365 Admin Center an.
2. Klicken Sie auf **Administrationscenter**, und wählen Sie dann **SharePoint**aus.
3. Wählen Sie in der SharePoint-Verwaltungskonsole **Freigabe**.
4. Stellen Sie sicher, dass die Option für **nicht zulassen Freigabe außerhalb Ihrer Organisation** *nicht* ausgewählt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Sparepoint Online-Einstellungen. ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a>□ Verify Konto Lizenzen und Typen

- **Konto für Teams lizenziert**: bei einem Gastkonto "" als Stamm eines echten Benutzerkontos in einige andere Office 365-Mandanten mit echten dem Benutzerkonto muss lizenziert für Teams für "Gast"aufgeführt. 
- **Konto muss Office 365 Schule oder arbeiten, oder MSA Konto**: aktuell, können Benutzer, die e-Mail-Adresse für ein Azure Active Directory, Office 365 Arbeit oder Schule Konto oder einem Microsoft-Konto (MSA) als Gast hinzugefügt werden. 
 
## <a name="-configure-environment"></a>□ Konfigurieren-Umgebung


Gäste sind erforderlich, um die mehrstufige Authentifizierung (mehrstufiger Authentifizierung das) verwenden, wenn der hosting Mandanten erforderlich ist.
Weitere Informationen finden Sie unter [Modelle Identität und Authentifizierung in Microsoft-Teams](identify-models-authentication.md).

## <a name="-understand-limitations-for-guests"></a>□ Machen Sie sich mit Einschränkungen für Gäste

Die Erfahrung Gast hat Einschränkungen Verhalten ist erwünscht. Stellen Sie sicher, dass die Erfahrung Gast verstehen, damit Sie nicht versuchen zu reparieren, die ein Problem nicht zur Verfügung.
Hier wird beispielsweise eine Liste einiger Funktionen, die nicht an einen Gast in Microsoft-Teams zur Verfügung steht:

- OneDrive für Unternehmen
- Suche nach Personen außerhalb von Teams
- Kalender, geplante Besprechungen oder Besprechungsdetails
- Telefonfestnetz (PSTN)
- Organigramm
- Erstellen Sie oder ändern Sie ein team
- Wechseln Sie für ein team
- Hochladen von Dateien in einer Person chat

Weitere Informationen finden Sie unter [Was die Erfahrung Gast entspricht](guest-experience.md) und [Gast Access in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).




## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie Probleme beim Hinzufügen von Gäste in Microsoft-Teams haben, finden Sie im [Handbuch zur Problembehandlung für Gast Zugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).


