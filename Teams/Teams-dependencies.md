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
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Verwalten Sie die Features und Funktionen für den Gastzugriff in Microsoft Teams mit vier verschiedenen Autorisierungsebenen.
ms.openlocfilehash: d52fdeb1f9867ac1faa0f8cf77023109155a8967
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094467"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autorisieren des Gastzugriffs in Microsoft Teams

Um die Anforderungen Ihrer Organisation zu erfüllen, können Sie die Features und Funktionen für den Gastzugriff in Teams mit vier verschiedenen Autorisierungsebenen verwalten. Für Ihre Microsoft 365-Organisation gelten alle Berechtigungsstufen. Die einzelnen Autorisierungsebenen steuern den Gastzugriff wie unten beschrieben:

- **Azure Active Directory**: Für den Gastzugriff in Teams wird die Azure AD B2B-Plattform (Business-to-Business) genutzt. Diese Autorisierungsebene steuert den Gastzugriff auf Verzeichnis-, Mandanten- und Anwendungsebene.
- **Teams**: Steuert die Gastumgebung nur in Teams.
- **Microsoft 365-Gruppen**: Steuert die Erfahrung der Gäste in Microsoft 365-Gruppen und Teams.
- **SharePoint Online und OneDrive for Business**: steuert die Erfahrung der Gäste in SharePoint Online, OneDrive for Business, Microsoft 365-Gruppen und Teams.

Diese verschiedenen Autorisierungsebenen bieten Ihnen Flexibilität beim Einrichten des Gastzugriffs für Ihre Organisation. Wenn Sie zum Beispiel in Ihrer Microsoft Teams-Organisation keine Gastbenutzer zulassen möchten (aber generell in Ihrer Organisation), deaktivieren Sie einfach den Gastzugriff in Microsoft Teams. Ein weiteres Beispiel: Sie können den Gastzugriff auf Azure AD-, Microsoft Teams- und Gruppenebene aktivieren, aber dann [das Hinzufügen von Gastbenutzern zu ausgewählten Teams deaktivieren, die einem oder mehreren Kriterien (z. B. der Datenklassifizierung „Vertraulich“) entsprechen](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint und OneDrive haben ihre eigenen Gastzugriffseinstellungen, die nicht auf Microsoft 365-Gruppen beruhen.

Anweisungen für die End-to-End-Konfiguration für den Gastzugriff finden Sie unter [Zusammenarbeit mit Gästen in einem Team](/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Gäste unterliegen den unter [Microsoft 365- und Office 365-Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library) und [Einschränkungen der Azure AD B2B-Zusammenarbeit](/azure/active-directory/external-identities/current-limitations) beschriebenen Diensteinschränkungen. 

Das folgende Diagramm zeigt, wie die Abhängigkeit der Gastzugriffsautorisierung zwischen Azure Active Directory, Teams und Microsoft 365 gewährt und integriert wird.

> [!div class="mx-imgBorder"]
> ![Diagramm der Autorisierungsabhängigkeiten für den Gastzugriff](media/teams_dependencies_image1.png)

Das nächste Diagramm bietet einen Überblick, wie das Benutzererlebnis mit dem Berechtigungsmodell über einen typischen Einladungs- und Einlösungsprozess in Bezug auf den Gastzugriff funktioniert.

> [!div class="mx-imgBorder"]
> ![Diagramm zu Einladungs- und Einlösungsprozess](media/authorize-guest-image1.png)

Es ist wichtig, zu beachten, dass Apps, Bots und Connectors evtl. einen eigenen Satz Berechtigungen und/oder je nach Benutzerkonto eine Zustimmung erfordern. Diese müssen möglicherweise separat gewährt werden. Gleichermaßen kann SharePoint zusätzliche externe Freigabegrenzen für einen bestimmten Benutzer, bestimmte Benutzergruppen oder sogar auf Site-Ebene auferlegen.

Die beiden vorherigen Diagramme sind auch in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) verfügbar.

## <a name="control-guest-access-in-azure-active-directory"></a>Steuern des Gastzugriffs in Azure Active Directory

Verwenden Sie Azure AD, um festzustellen, ob externe Projektmitarbeiter in Ihren Mandanten als Gäste eingeladen werden können und wie. Weitere Informationen zu Azure B2B-Gastzugriff, finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](/azure/active-directory/b2b/what-is-b2b). Informationen zu Azure AD-Rollen finden Sie unter [Erteilen von Berechtigungen für Benutzer von Partnerorganisationen in Ihrem Azure Active Directory-Mandanten](/azure/active-directory/b2b/add-guest-to-role).

Die Einstellungen für Einladungen gelten auf Organisationsebene und steuern den Gastzugriff auf Verzeichnis- und Anwendungsebene. Sie können diese Einstellungen in [Einstellungen für die externe Zusammenarbeit](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings) konfigurieren.

Azure AD umfasst die folgenden Einstellungen, um externe Benutzer zu konfigurieren:

- [Zugriffsbeschränkungen für Gastbenutzer](/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: **Ja** bedeutet, dass Administratoren und Benutzer mit der Rolle „Einladender“ Gäste in den Mandanten einladen können. **Nein** bedeutet, dass Administratoren und Benutzer Gäste nicht in den Mandanten einladen können.
- **Mitglieder können einladen**: Um Mitgliedern Ihres Verzeichnisses, die keine Administratoren SIND; zu erlauben, Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest (empfohlen). Wenn Sie nur Administratoren erlauben möchten, Gäste hinzuzufügen, können Sie diese Richtlinie auf **Nein** festlegen. Denken Sie daran, dass die Einstellung **Nein** die Gasterfahrung für Besitzer von Teams, die keine Administratoren sind, einschränkt. Sie können nur Gäste zu Teams hinzufügen, die bereits vom Administrator in AAD hinzugefügt wurden.
- **Gäste können einladen**: **Ja** bedeutet, dass Gäste in Ihrem Verzeichnis andere Gäste zur Zusammenarbeit an Ressourcen einladen können, die durch Azure AD gesichert sind, z. B. SharePoint-Sites oder Azure-Ressourcen. **Nein** bedeutet, dass Gäste keine anderen Gäste zur Zusammenarbeit mit Ihrer Organisation einladen können. Auch wenn diese auf **Ja** festgelegt ist, können Gäste keine anderen Gäste in Teams einladen.
 
Weitere Informationen zum Steuern, wer Gäste einladen kann, finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten, wer Gäste einladen kann](/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> Sie können auch verwalten, welche Domänen in Ihren Mandanten als Gäste eingeladen werden können. Siehe [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](/azure/active-directory/external-identities/allow-deny-list).

Das manuelle Hinzufügen des Benutzergastkontos zu Azure AD B2B ist nicht erforderlich, da das Konto automatisch zum Verzeichnis hinzugefügt wird, wenn Sie den Gast zu Teams hinzufügen.

### <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Die Gastzugriffslizenzierung verwendet Azure AD External Identities-Preise und basiert auf monatlichen aktiven Gästen. Weitere Informationen finden Sie unter [Abrechnungsmodell für Azure AD for External Identities](/azure/active-directory/external-identities/external-identities-pricing).

> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Office 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Referenz zu Gastfreigabeeinstellungen für Microsoft 365](/Office365/Enterprise/microsoft-365-guest-settings)

[Sichere Zusammenarbeit mit Microsoft 365 einrichten](/microsoft-365/solutions/setup-secure-collaboration-with-teams)