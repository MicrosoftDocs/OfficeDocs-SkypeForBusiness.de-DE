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
description: Administratoren können Microsoft Teams in Desktop- und Webclients und Azure Active Directory B2B-Portal neue Gäste zu einer Organisation hinzufügen.
ms.openlocfilehash: 1525a389b5299491dc7d0de2adfd744d0d3437aff7fbeb5832cd37790ab24ffb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344394"
---
# <a name="add-a-guest-to-a-team"></a>Hinzufügen eines Gasts zu einem Team

Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen.

Als Administrator können Sie der Organisation auf verschiedene Arten einen neuen Gast hinzufügen:

- Globale Administratoren oder Teams Administratoren und Teambesitzer fügen einen Gast zu einem Team in den Teams Clients oder im Team Admin Center hinzu. Weitere Informationen dazu finden Sie unter [Hinzufügen von Gästen zu einem Team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Wenn Sie noch keinen Gastzugriff eingerichtet haben, führen Sie die Schritte in [Zusammenarbeit mit Gästen in einem Team](/microsoft-365/solutions/collaborate-as-team) aus.

- Fügen Sie Gäste über Azure Active Directory (Azure AD) B2B-Zusammenarbeit zu Ihrer Organisation hinzu. Weitere Informationen finden Sie unter Schnellstart: Hinzufügen von Gästen zu Ihrem Verzeichnis [im Azure-Portal.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)

Administratoren können auch Berechtigungen zum Hinzufügen von Gästen an andere in ihrer Organisation delegieren, indem sie die Rolle des Gasteinladers zuweisen. Weitere Informationen hierzu finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten, wer Gäste einladen kann](/azure/active-directory/external-identities/delegate-invitations).

Mit Azure AD B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen. Diese Richtlinien können auf Mandantenebene, App-Ebene oder der Ebene einzelner Benutzer auf die gleiche Weise erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden können. Solche Richtlinien werden bei der Ressourcenorganisation erzwungen. Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](/azure/active-directory/external-identities/conditional-access). Einzelne Gäste können nicht blockiert werden.

Gäste, die Sie bereits über Azure AD B2B, Microsoft 365 Oder SharePoint hinzugefügt haben, können losgehen. Der Microsoft 365 oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen. Wenn Sie einen Gast direkt zu der Microsoft 365-Gruppe hinzufügen, die einem Team zugeordnet ist, hat der Gast Zugriff auf das Team, aber die Microsoft 365-Gruppe generiert keine Einladungs-E-Mail an den Gast. Daher sollte jemand im Team den Gast benachrichtigen.

> [!NOTE]
> Gäste unterliegen den [Microsoft 365- oder Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library)- und [Azure Active Directory](/azure/active-directory/external-identities/current-limitations)-Dienstbeschränkungen.

In Azure AD oder im Microsoft 365 Security Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen. Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert. Weitere Informationen finden Sie unter Überwachen und Melden eines [B2B-Zusammenarbeitsbenutzers](/azure/active-directory/external-identities/auditing-and-reporting) und Durchsuchen des Überwachungsprotokolls [im Compliance Center.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>Verwandte Themen

[Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md)

[Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams](set-up-guests.md)