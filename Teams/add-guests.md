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
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Administratoren lernen, wie sie neue Gastbenutzer zu einer Organisation im Microsoft Teams-Desktop, in Webclients und im Portal für Azure Active Directory B2B-Zusammenarbeit hinzufügen können.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: baac3c7c7e83547672b8baeb0915081523e5bfe8
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761281"
---
<a name="add-a-guest-to-a-team"></a>Hinzufügen eines Gasts zu einem Team
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen.

Als globaler Administrator können Sie einen neuen Gastbenutzer auf unterschiedliche Weise zur Organisation hinzufügen:
- Globale Administratoren oder Teams Administratoren und Teambesitzer fügen einen Gast zu einem Team in den Teams Clients oder im Team Admin Center hinzu. Weitere Informationen dazu finden Sie unter [Hinzufügen von Gästen zu einem Team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Wenn Sie noch keinen Gastzugriff eingerichtet haben, führen Sie die Schritte in [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) aus.

> [!NOTE] 
> Dies gilt nicht, wenn **Administratoren und Benutzer mit der Rolle "Gasteinladender" können einladen** aktiviert ist. Der Grund dafür ist, dass die Rolle "Gasteinladender" in Teams nicht unterstützt wird.

- Fügen Sie Gäste über Azure Active Directory (Azure AD) B2B-Zusammenarbeit zu Ihrer Organisation hinzu. Azure AD B2B-Zusammenarbeit ermöglicht es einem globalen Administrator, eine Reihe externer Benutzer einzuladen und zu autorisieren, indem er eine CSV-Datei (durch Trennzeichen getrennte Werte) mit nicht mehr als 2.000 Zeilen in das Portal für B2B-Zusammenarbeit hochlädt. Ausführlichere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=826383).

Mit Azure AD B2B-Zusammenarbeit können Organisationen Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung für B2B-Benutzer erzwingen. Diese Richtlinien können auf Mandantenebene, App-Ebene oder der Ebene einzelner Benutzer auf die gleiche Weise erzwungen werden, wie sie für Vollzeitmitarbeiter und Mitglieder der Organisation aktiviert werden können. Solche Richtlinien werden bei der Ressourcenorganisation erzwungen. Weitere Informationen finden Sie unter [Bedingter Zugriff für Benutzer der B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/?linkid=857454). Einzelne Gastbenutzer können nicht blockiert werden.

Für die von Ihnen bereits über Azure AD B2B, Microsoft 365-Gruppen oder SharePoint Online hinzugefügten Gastbenutzer kann es losgehen. Der Microsoft 365- oder Office 365-Administrator oder ein Teambesitzer kann diese Gäste zu den jeweiligen Teams hinzufügen. Wenn ein Team bereits zu einer Microsoft 365-Gruppe gehört und ein Gast zur Gruppe hinzugefügt wird, erhält der Gast Zugriff auf das Team. Wenn ein Gast über die Microsoft 365-Gruppe hinzugefügt wird, erhält der Gast keine Einladungs-E-Mail. Ein Mitglied des Teams sollte den Gast daher benachrichtigen.

> [!NOTE]
> Gäste unterliegen den [Microsoft 365- oder Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)- und [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)-Dienstbeschränkungen.

In Azure AD oder im Microsoft 365 Security Center können Sie das Hinzufügen von Gastbenutzern nachverfolgen. Das Hinzufügen eines Gasts in /+/Microsoft_Teams/+/ wird als Azure AD-Gruppenverwaltungsaktivität „Mitglied zur Gruppe hinzugefügt“ überwacht und protokolliert. Nähere Einzelheiten finden Sie unter [Überwachung eines B2B-Zusammenarbeitsbenutzers und Berichterstellung](https://go.microsoft.com/fwlink/p/?linkid=858884) und [Durchsuchen des Überwachungsprotokolls im Microsoft 365 Security Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).


## <a name="more-information"></a>Weitere Informationen

[Autorisieren des Gastzugriffs in Microsoft Teams](teams-dependencies.md)</br>
[Aktivieren oder Deaktivieren des Gastzugriffs in Microsoft Teams](set-up-guests.md)</br>
[Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team](guest-access-powershell.md)
