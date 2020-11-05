---
title: Autorisieren des Gastzugriffs in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
ms.openlocfilehash: 1040d548140d0fbb781e9cc9296be3d374b7b314
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48918987"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorisieren des Gastzugriffs in Microsoft Teams

Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen von Guest Access für Teams über vier verschiedene Autorisierungsebenen verwalten. Alle Autorisierungsebenen gelten für Ihre Microsoft 365-Organisation. Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:

- **Azure Active Directory** : Gastzugriff in Teams basiert auf der Azure AD Business-to-Business (B2B)-Plattform. Diese Autorisierungsebene steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene.
- **Teams** : steuert die Gast Erfahrung nur in Teams.
- **Microsoft 365-Gruppen** : steuert die Gast Erfahrung in Microsoft 365-Gruppen und-Teams.
- **SharePoint und OneDrive** : steuert die Gast Erfahrung in SharePoint, OneDrive, Microsoft 365-Gruppen und Teams.

Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation. Wenn Sie beispielsweise nicht möchten, dass Gastbenutzer in Teams, Sie aber insgesamt in Ihrer Organisation zulassen möchten, deaktivieren Sie einfach Gastzugriff in Teams. Ein weiteres Beispiel: Sie können den Gastzugriff auf Azure AD-, Teams-und Gruppenebene aktivieren, aber dann [das Hinzufügen von Gastbenutzern in ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien entsprechen, beispielsweise die Datenklassifizierung entspricht vertraulich](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint und OneDrive haben eigene Einstellungen für den Gastzugriff, die nicht von Microsoft 365-Gruppen abhängen.

Eine End-to-End-Konfigurationsanleitung für den Gastzugriff finden Sie unter [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Gäste unterliegen den unter [Microsoft 365- und Office 365-Dienstbeschreibungen](https://go.microsoft.com/fwlink/p/?linkid=282347) und [Einschränkungen der Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations) beschriebenen Diensteinschränkungen. 

Das folgende Diagramm zeigt, wie die Autorisierungs Abhängigkeit für Gast Zugriffe gewährt und zwischen Azure Active Directory, Teams und Microsoft 365 integriert wird.

> [!div class="mx-imgBorder"]
> ![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)

Das nächste Diagramm bietet einen Überblick, wie das Benutzererlebnis mit dem Berechtigungsmodell über einen typischen Einladungs- und Einlösungsprozess in Bezug auf den Gastzugriff funktioniert.

> [!div class="mx-imgBorder"]
> ![Diagramm zu Einladungs- und Einlösungsprozess](media/authorize-guest-image1.png)

Es ist wichtig, hier zu beachten, dass apps, Bots und Connectors möglicherweise einen eigenen Satz von Berechtigungen und/oder Zustimmung für das Benutzerkonto benötigen. Diese müssen möglicherweise separat gewährt werden. Gleichermaßen kann SharePoint zusätzliche externe Freigabegrenzen für einen bestimmten Benutzer, bestimmte Benutzergruppen oder sogar auf Site-Ebene auferlegen.

Die beiden vorherigen Diagramme sind auch in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) verfügbar.

## <a name="control-guest-access-in-azure-active-directory"></a>Steuern des Gastzugriffs in Azure Active Directory

Verwenden Sie Azure AD, um festzustellen, ob externe Projektmitarbeiter in Ihren Mandanten als Gäste eingeladen werden können und wie. Weitere Informationen zu Azure B2B-Gastzugriff, finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b). Informationen zu Azure AD-Rollen finden Sie unter [Erteilen von Berechtigungen für Benutzer von Partnerorganisationen in Ihrem Azure Active Directory-Mandanten](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).

Die Einstellungen für Einladungen gelten auf Organisationsebene und steuern die Gast Erfahrung auf Verzeichnis-und Anwendungsebene. Sie können diese Einstellungen in den [Einstellungen für die externe Zusammenarbeit](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)konfigurieren.

Azure AD umfasst die folgenden Einstellungen, um externe Benutzer zu konfigurieren:

- [Einschränkungen für Gastbenutzer Zugriff](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Administratoren und Benutzer mit der Rolle „Einladender“ können einladen** : **Ja** bedeutet, dass Administratoren und Benutzer mit der Rolle „Einladender“ Gäste in den Mandanten einladen können. **Nein** bedeutet, dass Administratoren und Benutzer Gäste nicht in den Mandanten einladen können.
- **Mitglieder können einladen** : Um Mitgliedern Ihres Verzeichnisses, die keine Administratoren SIND; zu erlauben, Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest (empfohlen). Wenn Sie nur Administratoren erlauben möchten, Gäste hinzuzufügen, können Sie diese Richtlinie auf **Nein** festlegen. Denken Sie daran, dass die Einstellung **Nein** die Gasterfahrung für Besitzer von Teams, die keine Administratoren sind, einschränkt. Sie können nur Gäste zu Teams hinzufügen, die bereits vom Administrator in AAD hinzugefügt wurden.
- **Gäste können einladen** : **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis andere Gäste zur Zusammenarbeit an Ressourcen einladen können, die durch Azure AD gesichert sind, z. B. SharePoint-Sites oder Azure-Ressourcen. **Nein** bedeutet, dass Gäste keine anderen Gäste zur Zusammenarbeit mit Ihrer Organisation einladen können. Auch wenn Sie auf **Ja** eingestellt ist, kann Gast keine anderen Gäste in Teams einladen.
 
Weitere Informationen zum Steuern, wer Gäste einladen kann, finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)können.

> [!NOTE]
> Sie können auch verwalten, welche Domänen in Ihren Mandanten als Gäste eingeladen werden können. Weitere Informationen finden Sie unter [zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).

Das manuelle Hinzufügen des Benutzergastkontos zu Azure AD B2B ist nicht erforderlich, da das Konto automatisch zum Verzeichnis hinzugefügt wird, wenn Sie den Gast zu Teams hinzufügen.

### <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Die Guest Access-Lizenzierung verwendet Azure AD External Identity-Preise und basiert auf monatlichen aktiven Gästen. Details finden Sie unter [Abrechnungsmodell für Azure AD External Identitys](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) .

> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Referenz zu Gastfreigabeeinstellungen für Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Einrichten einer sicheren Zusammenarbeit mit Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
