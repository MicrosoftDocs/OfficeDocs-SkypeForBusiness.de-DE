---
title: Verwalten von Microsoft 365 und benutzerdefinierten Connectors
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Connectors Ihr Team auf dem neuesten Stand halten, indem Sie häufig Inhalte und Updates direkt in einen Teams-Kanal für dienste bereitstellen, die Sie verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb056cbee4dc1d56a6cd967d3f46c3f0680e9b73
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880229"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Verwalten von Microsoft 365 und benutzerdefinierten Connectors

Um Ihr Team auf dem neuesten Stand zu halten, stellen die Connectors häufig verwendete Inhalts- und Dienstupdates direkt in einem Teams-Kanal bereit. Mit Connectors können Ihre Teams-Benutzer Updates von beliebten Diensten wie Trello, Wunderlist, GitHub und Azure DevOps Services erhalten. Die Updates werden direkt im Chatstream in ihrem Team veröffentlicht.

Microsoft 365-Connectors werden sowohl mit Microsoft Teams als auch mit Microsoft 365-Gruppen verwendet, wodurch es für alle Mitglieder einfacher ist, synchron zu bleiben und relevante Informationen schnell zu erhalten. Sowohl Microsoft Teams als auch Exchange verwenden das gleiche Connectormodell, mit dem Sie die gleichen Connectors auf beiden Plattformen verwenden können. Wenn Sie jedoch connectors deaktivieren, die für eine Microsoft 365-Gruppe konfiguriert sind, wird auch die Möglichkeit der Microsoft 365-Gruppe zum Erstellen von Connectors deaktiviert.

Jedes Mitglied eines Teams kann sein Team mit beliebten Clouddiensten mit den Connectors verbinden, wenn die Teamberechtigungen dies zulassen, und alle Teammitglieder werden über Aktivitäten von diesem Dienst benachrichtigt. Connectors funktionieren weiterhin, nachdem das Mitglied, das den Verbinder ursprünglich eingerichtet hat, die Verbindung verlässt. Jedes Teammitglied mit den Berechtigungen zum Hinzufügen oder Entfernen kann die Einrichtung von Connectors durch andere Mitglieder ändern.

## <a name="enable-or-disable-connectors-in-teams"></a>Aktivieren oder Deaktivieren von Connectors in Teams

Das Exchange Online PowerShell V2-Modul verwendet moderne Authentifizierung und arbeitet mit der mehrstufigen Authentifizierung, die als MFA bezeichnet wird, um eine Verbindung mit allen Exchange-verwandten PowerShell-Umgebungen in Microsoft 365 herzustellen. Administratoren können Exchange Online PowerShell verwenden, um Connectors für einen gesamten Mandanten oder ein bestimmtes Gruppenpostfach zu deaktivieren, was sich auf alle Benutzer in diesem Mandanten oder Postfach auswirkt. Es ist nicht möglich, diese Option für einige bestimmte Benutzer zu deaktivieren. Außerdem sind Connectors für Government Community Cloud, die als GCC-Mandanten bezeichnet werden, standardmäßig deaktiviert.

Die Mandanteneinstellung setzt die Gruppeneinstellung außer Kraft. Wenn beispielsweise ein Administrator Connectors für die Gruppe aktiviert und im Mandanten deaktiviert, sind Connectors für die Gruppe deaktiviert. Um einen Connector in Teams zu aktivieren, stellen Sie mithilfe der modernen Authentifizierung mit oder ohne MFA [eine Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) her.

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus, um einen Connector zu aktivieren oder zu deaktivieren:

* So deaktivieren Sie Connectors für den Mandanten: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* So deaktivieren Sie Nachrichten mit Aktionen für den Mandanten: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Führen Sie die folgenden Befehle aus, um Connectors für Teams zu aktivieren:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Weitere Informationen zum Austausch von PowerShell-Modulen finden [Sie unter Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Um Outlook-Connectors zu aktivieren oder zu deaktivieren, [verbinden Sie Apps mit Ihren Gruppen in Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Veröffentlichen von Connectors für Ihre Organisation

Wenn Sie möchten, dass ein benutzerdefinierter Connector nur für die Benutzer in Ihrer Organisation verfügbar ist, können Sie eine benutzerdefinierte Connector-App in den App-Katalog Ihrer Organisation hochladen. Nachdem Sie das App-Paket hochgeladen haben, können die Endbenutzer den Connector aus dem App-Katalog der Organisation installieren und den Connector in einem Team konfigurieren und verwenden.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> Benutzerdefinierte Connectors sind in Government Community Cloud (GCC), Government Community Cloud-High (GCCH) und Department of Defense (DOD) nicht verfügbar.

Um Connectors in einem Team oder Kanal zu verwenden, öffnen Sie das Menü "Weitere Optionen" in der oberen rechten Ecke eines Kanals. Wählen Sie im Menü **"Connectors** " aus, und suchen Oder suchen Sie nach dem erforderlichen Connector. Konfigurieren Sie bei Bedarf den ausgewählten Connector.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Fügen Sie Connectors zu Ihrem Kanal in Teams über die Optionen &quot;Weitere&quot; in der oberen rechten Ecke des Kanals hinzu.":::

## <a name="update-url-of-a-connector"></a>Url eines Connectors aktualisieren

Die Teams-Connectors wechseln zu einer neuen URL, um die Sicherheit zu verbessern. Während des Übergangs erhalten Sie eine Benachrichtigung zum Aktualisieren des konfigurierten Connectors. Aktualisieren Sie Ihren Connector so früh wie möglich, um Unterbrechungen der Connectordienste zu verhindern. So aktualisieren Sie Ihren Connector:

1. Überprüfen Sie auf der Konfigurationsseite für Connectors, ob neben dem konfigurierten Connector die Meldung **"Aufmerksamkeit erforderlich** " angezeigt wird.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Screenshot der Meldung &quot;Aufmerksamkeit erforderlich&quot;.":::

1. Um die Verbindung für eingehende Webhook-Connectors neu zu erstellen, wählen Sie " **URL aktualisieren"** aus, und verwenden Sie die generierte Webhook-URL.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Screenshot der Schaltfläche &quot;URL aktualisieren&quot;.":::

1. Entfernen Sie bei anderen Connectortypen den Connector, und erstellen Sie die Konnektorkonfiguration neu. Eine **URL wird auf dem neuesten Stand** angezeigt.

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="Screenshot der URL ist eine aktuelle Nachricht.":::

## <a name="related-articles"></a>Verwandte Artikel

* [Übersicht über benutzerdefinierte Connectors und Webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Erstellen Office 365 Connectors](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
