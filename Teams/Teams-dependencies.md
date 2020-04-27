---
title: Autorisieren des Gastzugriffs in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 848db9ea517876d941e837eaff34e72e0cff9c2a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778481"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autorisieren des Gastzugriffs in Microsoft Teams
===========================================

Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen verwalten. Für Ihre Office 365-Organisation gelten alle Berechtigungsstufen. Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:

- **Azure Active Directory**: Für den Gastzugriff in Microsoft Teams wird die Azure AD B2B-Plattform (Business-to-Business) genutzt. Diese Autorisierungsebene steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene.
- **Microsoft Teams**: Steuert die Gastumgebung nur in Microsoft Teams.
- **Microsoft 365-Gruppen**: steuert die Erfahrung der Gäste in Microsoft 365-Gruppen und Microsoft Teams.
- **SharePoint Online und OneDrive for Business**: steuert die Erfahrung der Gäste in SharePoint Online, OneDrive for Business, Microsoft 365-Gruppen und Microsoft Teams.

Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation. Wenn Sie zum Beispiel in Ihrer Microsoft Teams-Organisation keine Gastbenutzer zulassen möchten (aber generell in Ihrer Organisation), deaktivieren Sie einfach den Gastzugriff in Microsoft Teams. Ein weiteres Beispiel: Sie können den Gastzugriff auf Azure AD-, Microsoft Teams- und Gruppenebene aktivieren, aber dann das Hinzufügen von Gastbenutzern zu ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien (z. B. der Datenklassifizierung „Vertraulich“) entsprechen. SharePoint Online und OneDrive for Business haben ihre eigenen Gastzugriffseinstellungen, die nicht auf Microsoft 365-Gruppen beruhen.

> [!NOTE]
> Gäste unterliegen den [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen. 

Das folgende Diagramm zeigt, wie die Abhängigkeit der Gastzugriffsautorisierung zwischen Azure Active Directory, Microsoft Teams und Office 365 gewährt und integriert wird.

![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)

Das nächste Diagramm bietet einen Überblick, wie das Benutzererlebnis mit dem Berechtigungsmodell über einen typischen Einladungs- und Einlösungsprozess in Bezug auf den Gastzugriff funktioniert.

![Diagramm zu Einladungs- und Einlösungsprozess](media/authorize-guest-image1.png)

Es ist wichtig, zu beachten, dass Apps, Bots und Connectors evtl. einen eigenen Satz Berechtigungen und/oder je nach Benutzerkonto eine Zustimmung erfordern. Diese müssen möglicherweise separat gewährt werden. Gleichermaßen kann SharePoint zusätzliche externe Freigabegrenzen für einen bestimmten Benutzer, bestimmte Benutzergruppen oder sogar auf Site-Ebene auferlegen.

Die beiden vorherigen Diagramme sind auch in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) verfügbar.

## <a name="control-guest-access-in-azure-active-directory"></a>Steuern des Gastzugriffs in Azure Active Directory

Verwenden Sie Azure AD, um festzustellen, ob externe Projektmitarbeiter in Ihren Mandanten als Gäste eingeladen werden können und wie. Weitere Informationen zu Azure B2B-Gastzugriff, finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b). Informationen zu Azure AD-Rollen finden Sie unter [Erteilen von Berechtigungen für Benutzer von Partnerorganisationen in Ihrem Azure Active Directory-Mandanten](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).

Die Einstellungen für Einladungen gelten auf Mandantenebene und steuern den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene. Um diese Einstellungen im Azure-Portal zu konfigurieren, wechseln Sie zu **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen**, und wählen dann unter **Externe Benutzer** **Einstellungen für die externe Zusammenarbeit verwalten** aus.

Azure AD umfasst die folgenden Einstellungen, um externe Benutzer zu konfigurieren:

- **Gastbenutzerberechtigungen sind beschränkt**: **Ja** bedeutet, dass Gäste keine Berechtigung für bestimmte Verzeichnisaufgaben haben, wie das Aufzählen von Benutzern, Gruppen oder anderen Verzeichnisressourcen. Darüber hinaus können Gästen in Ihrem Verzeichnis keine administrativen Rollen zugewiesen werden. **Nein** bedeutet, dass Gäste denselben Zugriff auf Verzeichnisdaten haben wie normale Benutzer in Ihrem Verzeichnis.
- **Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: **Ja** bedeutet, dass Administratoren und Benutzer mit der Rolle „Einladender“ Gäste in den Mandanten einladen können. **Nein** bedeutet, dass Administratoren und Benutzer Gäste nicht in den Mandanten einladen können.
- **Mitglieder können einladen**: Um Mitgliedern Ihres Verzeichnisses, die keine Administratoren SIND; zu erlauben, Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest (empfohlen). Wenn Sie nur Administratoren erlauben möchten, Gäste hinzuzufügen, können Sie diese Richtlinie auf **Nein** festlegen. Denken Sie daran, dass die Einstellung **Nein** die Gasterfahrung für Besitzer von Teams, die keine Administratoren sind, einschränkt. Sie können nur Gäste zu Teams hinzufügen, die bereits vom Administrator in AAD hinzugefügt wurden.
- **Gäste können einladen**: **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis andere Gäste zur Zusammenarbeit an Ressourcen einladen können, die durch Azure AD gesichert sind, z. B. SharePoint-Sites oder Azure-Ressourcen. **Nein** bedeutet, dass Gäste keine anderen Gäste zur Zusammenarbeit mit Ihrer Organisation einladen können.
    > [!IMPORTANT]
    > Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.
 
Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> Sie können auch verwalten, welche Domänen in Ihren Mandanten als Gäste eingeladen werden können. Siehe [Zulassen/Blockieren des Gastzugriffs auf Microsoft 365-Gruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).

Das manuelle Hinzufügen des Benutzergastkontos zu Azure AD B2B ist nicht erforderlich, da das Konto automatisch zum Verzeichnis hinzugefügt wird, wenn Sie den Gast zu Teams hinzufügen.

### <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff
Die Gastzugriffslizenzierung ist Bestandteil der Azure AD-Lizenzierung. Der Gastzugriff ist in allen Microsoft 365 Business Standard- und Office 365 Enterprise-Abonnements enthalten. Weitere Informationen zur Lizenzierung finden Sie unter [Lizenzierungsanleitung zur Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="control-guest-access-in-teams"></a>Steuern des Gastzugriffs in Teams

Der Gastzugriff ist standardmäßig in Teams deaktiviert. Informationen zum Aktivieren des Gastzugriffs finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-microsoft-365-groups"></a>Steuern des Gastzugriffs in Microsoft 365-Gruppen

Über Microsoft 365-Gruppen können Sie das Hinzufügen von Gastbenutzern und den Gastzugriff auf alle Microsoft 365-Gruppen und Microsoft Teams-Teams in Ihrer Organisation steuern.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.

2. Wählen Sie links **Einstellungen** und dann **Dienste &amp; Add-Ins** aus.

3. Wählen Sie **Microsoft 365-Gruppen** aus.

     ![Screenshot von Microsoft 365-Gruppen in Einstellungen](media/authorize-guest-image2.png)
  
4. Setzen Sie auf der Seite Microsoft 365-Gruppen den Umschalter auf **Ein** oder **Aus**, je nachdem, ob Sie Team- und Gruppenbesitzern außerhalb Ihrer Organisation Zugriff auf Microsoft 365-Gruppen gewähren möchten. Ändern Sie die Umschaltfläche in **Ein** neben **Gruppenbesitzern das Hinzufügen von Personen außerhalb der Organisation zu Gruppen ermöglichen**. Wenn Sie diesen Umschalter auf **Ein** stellen, sehen Sie eine weitere Option, mit der Sie steuern können, ob Gruppen- und Teambesitzer Personen außerhalb Ihrer Organisation zu Microsoft 365-Gruppen und Microsoft Teams hinzufügen dürfen. Legen Sie diese Umschaltfläche auf **Ein** fest, wenn Sie Gruppen- und Teambesitzern das Hinzufügen von Gastbenutzern ermöglichen möchten. 
 
   ![Screenshot des Microsoft 365-Gruppenbereichs mit den aktivierten Optionen](media/authorize-guest-image3.png)

Diese Einstellungen gelten auf Mandantenebene und steuern das Gasterlebnis in Microsoft 365-Gruppen und Teams.

Unter [Gastzugriff in Microsoft 365-Gruppen](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) finden Sie weitere Informationen zum Gastzugriff in Gruppen, einschließlich der Funktionsweise des Gastzugriffs, der Verwaltung des Gastzugriffs und Antworten auf häufig gestellte Fragen.

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Steuern des Gastzugriffs auf Sharepoint Online und OneDrive for Business

Teams nutzt SharePoint Online und OneDrive for Business zum Speichern von Dateien und Dokumenten für Kanäle und Chatunterhaltungen.  

Um alle Gastzugriffsfunktionen in Teams zu aktivieren, müssen Office 365-Administratoren die folgenden Einstellungen konfigurieren:

- In SharePoint Online: Wählen Sie **Vorhandene Gäste**, **Neue und vorhandene Gäste** oder **Jeder** aus.

    Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der externen Freigabe](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).

- In Microsoft 365-Gruppen: Aktivieren Sie **Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen lassen**

    Weitere Informationen finden Sie obenstehend unter [Steuern des Gastzugriffs in Microsoft 365-Gruppen](#control-guest-access-in-microsoft-365-groups).
  
Diese Einstellungen gelten auf Mandantenebene und steuern den Gastzugriff in Microsoft Office SharePoint Online, OneDrive for Business, Microsoft 365-Gruppen und Teams.

Sie können SharePoint Online-Einstellungen für externe Benutzer für die mit Teams verbundenen Teamwebsites verwalten. Weitere Informationen  finden Sie unter [Verwalten der Einstellungen Ihrer SharePoint-Teamwebsite](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Referenz zu Gastfreigabeeinstellungen für Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
