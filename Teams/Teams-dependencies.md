---
title: Autorisieren des Gastzugriffs in Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d31bb8eafdaa6a04fe34f8433e8484ec447e7c1
ms.sourcegitcommit: 2ce680aba13d1d781019b766a04e4e7d46d4f72c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "21136307"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorisieren des Gastzugriffs in Microsoft Teams
===========================================

Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen verwalten. Alle Autorisierungsebenen gelten für Ihren Office 365-Mandanten. Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:
- **Azure Active Directory**: Für den Gastzugriff in Microsoft Teams wird die Azure AD B2B-Plattform (Business-to-Business) genutzt. Steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene. 
- **Microsoft Teams**: Steuert nur Microsoft Teams. 
- **Office 365-Gruppen**: Steuert den Gastzugriff in Office 365-Gruppen und in Microsoft Teams.
- **SharePoint Online und OneDrive for Business**: Steuert den Gastzugriff in SharePoint Online, OneDrive for Business, Office 365-Gruppen und Microsoft Teams.

Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation. Wenn Sie zum Beispiel in Ihrer Microsoft Teams-Organisation keine Gastbenutzer zulassen möchten, deaktivieren Sie einfach den Gastzugriff in Microsoft Teams. Ein weiteres Beispiel: Sie können den Gastzugriff auf AAD-Ebene, Microsoft Teams-Ebene und Gruppenebene aktivieren, aber dann das Hinzufügen von Gastbenutzern zu ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien (z. B. der Datenklassifizierung „Vertraulich“) entsprechen. Vielleicht verwenden Sie auch keine Office 365-Gruppen. Für SharePoint Online und OneDrive for Business gibt es eigene Einstellungen für den Gastzugriff, die nicht auf Office 365-Gruppen basieren. 

> [!NOTE]
> Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen. 

  Das folgende Diagramm zeigt, wie die Abhängigkeit der Gastzugriffsautorisierung zwischen Azure Active Directory, Microsoft Teams und Office 365 gewährt und integriert wird.


![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a>Azure Active Directory

Mit Azure AD B2B-Zusammenarbeit ist das Senden von Einladungen an potenzielle Gastbenutzer nicht auf Mandantenadministratoren beschränkt. Sie können stattdessen Richtlinien verwenden, um das Senden von Einladungen an Benutzer zu delegieren, die aufgrund ihrer Rollen Einladungen senden können.

Die Einstellungen für Einladungen gelten auf Mandantenebene und steuern den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene. Mindestens zur Unterstützung von Gäste müssen **Mitglieder einladen können** auf **Ja**festgelegt werden.


![Screenshot der Benutzereinstellungen im Azure Active Directory-Portal](media/teams_dependencies_image2.png)

Azure AD umfasst die folgenden Einstellungen zum Konfigurieren von externer Benutzern:
- **Benutzerberechtigungen Gast sind beschränkt**: **Ja** bedeutet, dass Gäste nicht über die Berechtigung für bestimmte Verzeichnisaufgaben verfügen, wie Aufzählen von Benutzern, Gruppen oder andere Directory Ressourcen. Darüber hinaus können nicht Gäste Administratorrollen in Ihrem Verzeichnis zugewiesen werden. **Keine** Möglichkeit, die Gäste haben den gleichen Zugriff auf Directory-Daten, die in Ihrem Verzeichnis reguläre Benutzer haben.
- **Administratoren und Benutzer in die Guest-Rolle eingeladenen können einladen**: **Ja** bedeutet, dass Administratoren und Benutzer in der Rolle "Gast eingeladenen" Gäste, die dem Mandanten einladen können. **No** bedeutet, dass Administratoren und Benutzer können keine Gäste, die dem Mandanten einladen.
- **Mitglieder können einladen**: **Ja** bedeutet, dass nicht-Administrator Mitglieder Ihres Verzeichnisses Gäste auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können. **No** bedeutet, dass nur Administratoren einladen können, die in das Verzeichnis Gäste.
- **Gäste können einladen**: **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis selbst anderen Gast auf Ressourcen, die durch Ihre Azure AD, wie SharePoint-Websites oder Azure Ressourcen gesichert Zusammenarbeit einladen können. **Keine** Möglichkeit, die Gäste einladen nicht andere Gäste für die Zusammenarbeit mit Ihrer Organisation.
 


> [!NOTE]
> Sie können auch verwalten, welche Domänen in Ihrem Mandanten als Gäste eingeladen werden können. Finden Sie unter [Zulassen/Blockieren Gast des Zugriffs auf Office 365-Gruppen](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da). 

## <a name="microsoft-teams"></a>Microsoft Teams
Sie können in Microsoft Teams steuern, ob der Gastzugriff für Ihre Organisation aktiviert oder deaktiviert ist. Die Einstellung ist standardmäßig deaktiviert und gilt auf Mandantenebene nur für Microsoft Teams.



Sie können die Einstellungen für den Gastzugriff in Microsoft Teams über das Office 365 Admin Center verwalten. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md). 


## <a name="office-365-groups"></a>Office 365-Gruppen

Über Office 365-Gruppen können Sie das Hinzufügen von Gastbenutzern sowie den Gastzugriff auf alle Office 365-Gruppen und auf Microsoft Teams in Ihrer Organisation steuern.

1. Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
  
2. Wählen Sie im Navigationsmenü **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.
    
  
3. Wählen Sie **Office 365-Gruppen** aus.
    
     ![Office 365-Gruppen](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Je nachdem, ob Sie den Zugriff für Team- oder Gruppenbesitzer außerhalb Ihres Unternehmens auf Office 365-Gruppen gewähren möchten, legen Sie die Umschaltfläche auf der Seite „Office 365-Gruppen“ auf **Ein** oder **Aus** fest. Klicken oder tippen Sie neben **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen** auf die Umschaltfläche, um sie in **Ein** zu ändern. Wenn Sie diese Umschaltfläche in „Ein“ ändern, sehen Sie eine weitere Option. Mit dieser können Sie steuern, ob es Gruppen- und Teambesitzern möglich sein soll, Personen außerhalb der Organisation zu Office 365-Gruppen und Microsoft Teams hinzuzufügen. Legen Sie diese Umschaltfläche auf „Ein“ fest, wenn Sie Gruppen- und Teambesitzern das Hinzufügen von Gastbenutzern ermöglichen möchten. ![Dieser Screenshot bildet den Office 365 Groups-Bereich mit den aktivierten Optionen für den Zugriff von Gruppenmitgliedern außerhalb der Organisation auf Gruppeninhalte sowie für das Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer ab.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




Die oben genannten Einstellungen gelten auf Mandantenebene und steuern den Gastzugriff in Office 365-Gruppen und in Microsoft Teams.


## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online und OneDrive for Business

Teams nutzt SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen.  
  
    
    
Um alle Gastzugriffsfunktionen in Microsoft Teams zu aktivieren, müssen Office 365-Administratoren für die folgenden Einstellungen die Option **Ein** auswählen:
  
    
    

- In SharePoint Online: **Freigabe nur für bereits im Verzeichnis enthaltenen externen Benutzern zulassen**
    
    Weitere Informationen finden Sie unter [Verwalten von externer Freigabe für Ihre SharePoint Online-Umgebung](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- In Office 365-Gruppen: **Hinzufügen von Personen außerhalb der Organisation zu Gruppen durch Gruppenbesitzer zulassen**
    
    Weitere Informationen finden Sie unter [Steuern des Gastzugriffs auf Microsoft Teams](#controlguest).
  

Die oben genannten Einstellungen gelten auf Mandantenebene und steuern den Gastzugriff in SharePoint Online, OneDrive for Business, Office 365-Gruppen und Microsoft Teams.


Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Microsoft Teams verbundene Teamwebsite verwalten. Weitere Einzelheiten finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿
