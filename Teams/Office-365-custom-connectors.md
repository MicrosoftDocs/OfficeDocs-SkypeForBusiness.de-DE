---
title: Verwalten von Microsoft 365- und benutzerdefinierten Connectors
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Connectors Ihr Team auf dem neuesten Stand halten, indem sie häufig Inhalte und Updates direkt in einem Teams-Kanal für von Ihnen verwendete Dienste bereitstellen.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8abc7dc981902945cdb8be8ed9a2fe705e0d6e73
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486740"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Verwalten von Microsoft 365- und benutzerdefinierten Connectors

Um Ihr Team auf dem neuesten Stand zu halten, stellen die Connectors häufig verwendete Inhalte und Dienstupdates direkt in einem Teams-Kanal bereit. Mithilfe von Connectors können Ihre Teams-Benutzer Updates von beliebten Diensten wie Trello, Wunderlist, GitHub und Azure DevOps Services empfangen. Die Updates werden direkt im Chatstream ihres Teams veröffentlicht.

Microsoft 365-Connectors werden sowohl mit Microsoft Teams als auch mit Microsoft 365-Gruppen verwendet. Sie erleichtern es allen Mitgliedern, synchron zu bleiben und schnell die relevanten Informationen zu erhalten. Sie können die gleichen Connectors sowohl in Microsoft Teams als auch in Microsoft Exchange verwenden. Wenn Sie jedoch Connectors deaktivieren, die für eine Microsoft 365-Gruppe konfiguriert sind, wird auch die Möglichkeit für die Microsoft 365-Gruppe deaktiviert, Connectors zu erstellen.

Jedes Mitglied eines Teams kann sein Team mit den Connectors mit beliebten Clouddiensten verbinden, wenn die Teamberechtigungen dies zulassen, und alle Teammitglieder werden über Aktivitäten von diesem Dienst benachrichtigt. Connectors funktionieren weiterhin, nachdem das Mitglied, das den Connector ursprünglich eingerichtet hat, austritt. Jedes Teammitglied mit den Berechtigungen zum Hinzufügen oder Entfernen kann Connectors ändern, die von anderen Mitgliedern eingerichtet wurden.

## <a name="enable-or-disable-connectors-in-teams"></a>Aktivieren oder deaktivieren von Connectors in Teams

Das Exchange Online PowerShell V2-Modul verwendet moderne Authentifizierung und arbeitet mit Multi-Faktor-Authentifizierung (MFA) für die Verbindung mit allen Exchange-bezogenen PowerShell-Umgebungen in Microsoft 365. Administratoren können Exchange Online PowerShell verwenden, um Connectors für einen gesamten Mandanten oder ein bestimmtes Gruppenpostfach zu deaktivieren, was sich auf alle Benutzer in diesem Mandanten oder Postfach auswirkt. Es ist nicht möglich, diese Option für einige bestimmte Benutzer zu deaktivieren. Außerdem sind Connectors für Government Community Cloud (GCC)-Umgebungen standardmäßig deaktiviert.

> [!NOTE]
> Connectors sind für Government Community Cloud (GCC)-Umgebungen standardmäßig deaktiviert. Um diese zu aktivieren, legen Sie die Parameter `ConnectorsEnabled` oder `ConnectorsEnabledForTeams` mit dem Cmdlet `SetOrganizationConfig` auf `$true` fest. Stellen Sie eine Verbindung mit der [Exchange-Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true) her.

Die Mandanteneinstellung überschreibt die Gruppeneinstellung. Wenn ein Administrator beispielsweise Connectors für die Gruppe aktiviert und sie auf dem Mandanten deaktiviert, werden Connectors für die Gruppe deaktiviert. Um einen Connector in Teams zu aktivieren, verwenden Sie die modernen Authentifizierung mit oder ohne MFA, um [eine Verbindung mit Exchange Online PowerShell herzustellen](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true).

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um einen Connector zu aktivieren oder zu deaktivieren:

* So deaktivieren Sie Connectors für den Mandanten: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* So deaktivieren Sie Aktionen erfordernde Nachrichten für den Mandanten: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Führen Sie die folgenden Befehle aus, um Connectors für Teams zu aktivieren:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Weitere Informationen zum Exchange PowerShell-Modul finden Sie unter [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Um Outlook-Connectors zu aktivieren oder zu deaktivieren, [verbinden Sie Apps mit Ihren Gruppen in Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Veröffentlichen von Connectors für ihre Organisation

Um den Benutzern Ihrer Organisation einen benutzerdefinierten Connector zur Verfügung zu stellen, laden Sie eine benutzerdefinierte Connector-App in den App-Katalog Ihrer Organisation hoch. Endbenutzer innerhalb der Organisation können den Connector in einem Team installieren, konfigurieren und verwenden.

> [!IMPORTANT]
> Benutzerdefinierte Connectors sind in Government Community Cloud (GCC)-, Government Community Cloud-High (GCCH)- und Department of Defense (DOD)-Umgebungen nicht verfügbar.

Um Connectors in einem Team oder Kanal zu verwenden, öffnen Sie das Menü „Weitere Optionen“ in der oberen rechten Ecke eines Kanals. Wählen Sie im Menü die Option **Connectors** aus, und suchen Sie dann nach dem erforderlichen Connector. Konfigurieren Sie bei Bedarf den ausgewählten Connector.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Fügen Sie Ihrem Kanal in Teams über die Optionen „Weitere“ in der oberen rechten Ecke des Kanals Connectors hinzu.":::

## <a name="update-url-of-a-connector"></a>URL eines Connectors aktualisieren

Die Teams-Connectors wechseln zu einer neuen URL, um die Sicherheit zu verbessern. Während des Übergangs erhalten Sie eine Benachrichtigung zum Aktualisieren des konfigurierten Connectors. Aktualisieren Sie Ihren Connector so früh wie möglich, um Unterbrechungen der Connectordienste zu verhindern. So aktualisieren Sie Ihren Connector:

1. Überprüfen Sie auf der Konfigurationsseite für Connectors, ob neben dem konfigurierten Connector die Nachricht **Aufmerksamkeit erforderlich** angezeigt wird.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Screenshot der Nachricht „Aufmerksamkeit erforderlich“.":::

1. Um die Verbindung für eingehende Webhook-Connectors neu zu erstellen, wählen Sie **URL aktualisieren** aus, und verwenden Sie die generierte Webhook-URL.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Screenshot der Schaltfläche „URL aktualisieren“.":::

1. Entfernen Sie für andere Connectortypen den Connector, und erstellen Sie die Connectorkonfiguration neu. Eine Nachricht **URL ist auf dem neuesten Stand** wird angezeigt.

   :::image type="content" source="media/teams-url-updated.png" alt-text="Screenshot der Nachricht „URL ist auf dem neuesten Stand“.":::

## <a name="related-articles"></a>Verwandte Artikel

* [Übersicht über benutzerdefinierte Connectors und Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Erstellen von Office 365-Connectors](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
