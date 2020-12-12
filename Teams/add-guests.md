---
title: Hinzufügen eines Gasts zu einem Team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Administratoren können erfahren, wie Sie in Microsoft Teams Desktop-und Webclients und Azure Active Directory B2B-Zusammenarbeitsportal neue Gäste zu einer Organisation hinzufügen.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662440"
---
# <a name="add-a-guest-to-a-team"></a>Hinzufügen eines Gasts zu einem Team

Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen.

Als Administrator können Sie der Organisation auf verschiedene Weise einen neuen Gast hinzufügen:

- Globale Administratoren oder Teams Administratoren und Teambesitzer fügen einen Gast zu einem Team in den Teams Clients oder im Team Admin Center hinzu. Weitere Informationen dazu finden Sie unter [Hinzufügen von Gästen zu einem Team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Wenn Sie noch keinen Gastzugriff eingerichtet haben, führen Sie die Schritte in [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) aus.

- Fügen Sie Gäste über Azure Active Directory (Azure AD) B2B-Zusammenarbeit zu Ihrer Organisation hinzu. Weitere Informationen finden Sie unter [Schnellstart: Hinzufügen von Gästen zu Ihrem Verzeichnis im Azure-Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Administratoren können auch Berechtigungen zum Hinzufügen von Gästen an andere in ihrer Organisation delegieren, indem sie die Rolle des Gasteinladers zuweisen. Weitere Informationen hierzu finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten, wer Gäste einladen kann](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Mit Azure AD B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen. Diese Richtlinien können auf Mandantenebene, App-Ebene oder der Ebene einzelner Benutzer auf die gleiche Weise erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden können. Solche Richtlinien werden bei der Ressourcenorganisation erzwungen. Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454). Einzelne Gäste können nicht blockiert werden.

Gäste, die Sie bereits über Azure AD B2B, Microsoft 365-Gruppen oder SharePoint hinzugefügt haben, sind einsatzbereit. Der Microsoft 365-Administrator oder ein Teambesitzer kann diese Gäste zu ihren jeweiligen Teams hinzufügen. Wenn Sie einen Gast direkt zu der Microsoft 365-Gruppe hinzufügen, die einem Team zugeordnet ist, erhält der Gastzugriff auf das Team, aber die Microsoft 365-Gruppe generiert keine Einladungs-e-Mail an den Gast, damit jemand im Team den Gast benachrichtigt.

> [!NOTE]
> Gäste unterliegen den [Microsoft 365- oder Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.

In Azure AD oder im Microsoft 365 Security Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen. Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert. Weitere Informationen finden Sie unter über [wachen und melden eines Benutzers für die B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) und [Durchsuchen des Überwachungsprotokolls im Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Verwandte Themen

[Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md)

[Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams](set-up-guests.md)
