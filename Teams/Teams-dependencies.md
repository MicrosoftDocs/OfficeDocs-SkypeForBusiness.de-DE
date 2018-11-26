---
title: Autorisieren des Gastzugriffs in Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/26/18
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76fae371f8cc82992f3396ae49cc9a4dff4432b0
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674513"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorisieren des Gastzugriffs in Microsoft Teams
===========================================

Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen verwalten. Alle Autorisierungsebenen gelten für Ihren Office 365-Mandanten. Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:

- **Azure Active Directory**: Für den Gastzugriff in Microsoft Teams wird die Azure AD B2B-Plattform (Business-to-Business) genutzt. Steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene. 
- **Microsoft Teams**: Steuert nur Microsoft Teams. 
- **Office 365-Gruppen**: Steuert den Gastzugriff in Office 365-Gruppen und in Microsoft Teams.
- **SharePoint Online und OneDrive for Business**: Steuert den Gastzugriff in SharePoint Online, OneDrive for Business, Office 365-Gruppen und Microsoft Teams.

Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation. Angenommen, wenn Sie nicht möchten Gast Benutzern in Ihrer Microsoft-Teams, aber es in Ihrer Organisation insgesamt zulassen möchten, deaktivieren Sie einfach Gast Access in Microsoft-Teams. Ein weiteres Beispiel: Sie können den Gastzugriff auf AAD-Ebene, Microsoft Teams-Ebene und Gruppenebene aktivieren, aber dann das Hinzufügen von Gastbenutzern zu ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien (z. B. der Datenklassifizierung „Vertraulich“) entsprechen. Für SharePoint Online und OneDrive for Business gibt es eigene Einstellungen für den Gastzugriff, die nicht auf Office 365-Gruppen basieren. 

> [!NOTE]
> Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen. 

Das folgende Diagramm zeigt, wie die Abhängigkeit der Gastzugriffsautorisierung zwischen Azure Active Directory, Microsoft Teams und Office 365 gewährt und integriert wird.

![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)

Das folgende Diagramm zeigt auf allgemeiner Ebene, wie die Benutzeroberfläche mit des Berechtigungsmodells in einem normalen Gast Access-Einladung und Rückzahlung Flow funktioniert.

![Darstellung der Einladung und Rückzahlung fließt.](media/authorize-guest-image1.png)

Es ist wichtig zu beachten, dass apps, Bots und Connectors möglicherweise einen eigenen Satz von Berechtigungen erfordern und/oder speziell für das Benutzerkonto stimmen. Diese müssen separat erteilt werden. In ähnlicher Weise kann SharePoint zusätzliche externe Freigabe Grenzen für einen bestimmten Benutzer, Gruppen von Benutzern oder sogar auf der Websiteebene bedingen.

## <a name="control-guest-access-in-azure-active-directory"></a>Steuern des Zugriffs Gast in Azure Active Directory

Verwenden Sie Azure AD, um zu bestimmen, ob externe Mitarbeiter in Ihrem Mandanten als Gäste und auf welche Weise eingeladen werden können. Weitere Informationen zu Azure B2B Gast Access finden Sie unter [Was ist Gast Benutzerzugriff in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b). Informationen zu Azure AD-Rollen finden Sie unter [Erteilen von Berechtigungen für Benutzer von Partnerorganisationen in Ihrem Azure Active Directory-Mandanten](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).

Die Einstellungen für Einladungen gelten auf Mandantenebene und steuern den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene. 

![Screenshot der Benutzereinstellungen im Azure Active Directory-Portal](media/teams_dependencies_image2.png)

Azure AD umfasst die folgenden Einstellungen zum Konfigurieren von externer Benutzern:

- **Benutzerberechtigungen Gast sind beschränkt**: **Ja** bedeutet, dass Gäste nicht über die Berechtigung für bestimmte Verzeichnisaufgaben verfügen, wie Aufzählen von Benutzern, Gruppen oder andere Directory Ressourcen. Darüber hinaus können nicht Gäste Administratorrollen in Ihrem Verzeichnis zugewiesen werden. **Keine** Möglichkeit, die Gäste haben den gleichen Zugriff auf Directory-Daten, die in Ihrem Verzeichnis reguläre Benutzer haben.
- **Administratoren und Benutzer in die Guest-Rolle eingeladenen können einladen**: **Ja** bedeutet, dass Administratoren und Benutzer in der Rolle "Gast eingeladenen" Gäste, die dem Mandanten einladen können. **No** bedeutet, dass Administratoren und Benutzer können keine Gäste, die dem Mandanten einladen.
- **Mitglieder können einladen**: **Ja** bedeutet, dass nicht-Administrator Mitglieder Ihres Verzeichnisses Gäste auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können. **No** bedeutet, dass nur Administratoren einladen können, die in das Verzeichnis Gäste.</br>
      
    > [!NOTE]
    > Derzeit Teams unterstützt nicht die Guest-Rolle eingeladenen. die **Mitglieder einladen können** mindestens muss Umschalten auf **Ja** für Access Gast Arbeit in Teams festgelegt werden.
- **Gäste können einladen**: **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis selbst andere Gäste auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können. **Keine** Möglichkeit, die Gäste einladen nicht andere Gäste für die Zusammenarbeit mit Ihrer Organisation.
 
Weitere Informationen zu steuern, wer Gäste einladen können finden Sie unter [Stellvertreter Einladungen für die Zusammenarbeit mit Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> Sie können auch verwalten, welche Domänen in Ihrem Mandanten als Gäste eingeladen werden können. Finden Sie unter [Zulassen/Blockieren Gast des Zugriffs auf Office 365-Gruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

Manuelles Hinzufügen das Benutzerkonto Gast zu Azure AD B2B ist nicht erforderlich, wie das Konto in das Verzeichnis automatisch soll beim Hinzufügen des Gasts zu Teams eingefügt werden. 

Azure AD-Lizenzierung können Sie bis zu 5 Gäste pro Lizenz hinzufügen. Weitere Informationen zur Lizenzierung von Azure AD finden Sie unter [Azure Active Directory B2B Zusammenarbeit Lizenzierung Anweisungen](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Steuern des Zugriffs Gast in Teams

In Teams können Sie steuern, ob die Erfahrung Gast aktiviert oder für Ihre Organisation deaktiviert ist. Diese Einstellung ist standardmäßig deaktiviert und auf der Ebene der Mandant gilt für Teams nur.

Sie können Teams Gast Access-Einstellungen aus dem Microsoft-Teams & Skype für Business Admin Center verwalten. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Steuern des Zugriffs Gast in Office 365-Gruppen

Über Office 365-Gruppen können Sie das Hinzufügen von Gastbenutzern sowie den Gastzugriff auf alle Office 365-Gruppen und auf Microsoft Teams in Ihrer Organisation steuern.

1. Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
2. Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.
    
3. Wählen Sie **Office 365-Gruppen** aus.
    
     ![Office 365-Gruppen](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  
4. Legen Sie auf der Seite Office 365 Gruppen die Umschaltfläche auf **ein-** oder **Ausschalten**, je nachdem, ob Sie Teams und der Gruppe Besitzer außerhalb Ihrer Organisation Zugriff auf Office 365-Gruppen ermöglichen möchten. Klicken oder tippen Sie neben **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen** auf die Umschaltfläche, um sie in **Ein** zu ändern. Wenn Sie diese umschalten, **Klicken Sie auf**deaktivieren, sehen Sie eine andere Option steuern, ob Sie Gruppe lassen möchten und Team Besitzer Hinzufügen von Personen außerhalb Ihrer Organisation zu Office 365-Gruppen und Microsoft-teams. Legen Sie diese Umschalten auf **auf** , wenn Sie Gruppe lassen möchten und Team Besitzer Gastbenutzer hinzufügen. 
 
   ![Dieser Screenshot bildet den Office 365 Groups-Bereich mit den aktivierten Optionen für den Zugriff von Gruppenmitgliedern außerhalb der Organisation auf Gruppeninhalte sowie für das Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer ab.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)

Diese Einstellungen auf der Ebene der Mandanten anwenden und steuern die Gast Erfahrung in Office 365-Gruppen und Microsoft-Teams.

Weitere Informationen über Gast in Gruppen, einschließlich Gast Access Funktionsweise der Verwaltung von Gastzugriff und Antworten auf häufig gestellte Fragen finden Sie unter [Gast in Office 365 Gruppen zugreifen](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) .

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Steuern Gast des Zugriffs auf SharePoint Online und OneDrive für Unternehmen

Teams nutzt SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen.  
   
Um alle Gastzugriffsfunktionen in Microsoft Teams zu aktivieren, müssen Office 365-Administratoren für die folgenden Einstellungen die Option **Ein** auswählen:

- In SharePoint Online: **Freigabe nur für bereits im Verzeichnis enthaltenen externen Benutzern zulassen**
    
    Weitere Informationen finden Sie unter [Verwalten von externer Freigabe für Ihre SharePoint Online-Umgebung](https://docs.microsoft.com/sharepoint/external-sharing-overview).
    
- In Office 365-Gruppen: **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen**
    
    Weitere Informationen finden Sie unter [Steuern des Zugriffs Gast in Office 365-Gruppen](#control-guest-access-in-office-365-groups), oben.
  
Diese Einstellungen auf der Ebene der Mandanten anwenden und steuern die Gast Erfahrung mit SharePoint Online, OneDrive für Unternehmen, Office 365-Gruppen und Teams.

Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Microsoft Teams verbundene Teamwebsite verwalten. Weitere Einzelheiten finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿

