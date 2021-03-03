---
title: Verwenden von Microsoft 365 und benutzerdefinierten Connectors
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076417"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Verwenden von Microsoft 365 und benutzerdefinierten Connectors in Microsoft Teams
=======================================================

Connectors halten Ihr Team auf dem neuesten Stand, indem häufig verwendete Inhalte und Dienstupdates direkt in einem Kanal zur Verfügung gestellt werden. Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Trello, Wunderlist, GitHub und Azure DevOps Services innerhalb des Chatstreams ihres Teams erhalten.

Jedes Mitglied eines Teams kann sein Team mit beliebten Clouddiensten mit den Connectors verbinden, sofern die Teamberechtigungen dies zulassen, und alle Teammitglieder werden über Aktivitäten dieses Diensts benachrichtigt. Verbinder funktionieren auch dann weiterhin, wenn das Mitglied, das den Verbinder erst eingerichtet hat, den Verbinder verlassen hat. Jedes Teammitglied mit den Berechtigungen zum Hinzufügen\Entfernen kann die Einrichtung von Connectors durch andere Mitglieder ändern.

Microsoft 365-Connectors können sowohl mit Microsoft Teams als auch mit Microsoft 365-Gruppen verwendet werden, wodurch es für alle Mitglieder einfacher ist, synchronisiert zu bleiben und relevante Informationen schnell zu erhalten. Sowohl Microsoft Teams als auch Exchange verwenden dasselbe Connectormodell, das es Ihnen ermöglicht, die gleichen Connectors auf beiden Plattformen zu verwenden. Es ist jedoch zu erwähnen, dass durch das Deaktivieren von Connectors für die Microsoft 365-Gruppe, von der ein Team abhängig ist, auch die Möglichkeit zum Erstellen von Connectors für dieses Team deaktiviert wird.

<a name="add-a-connector-to-a-channel"></a>Hinzufügen eines Connectors zu einem Kanal
----------------------------

Derzeit können Sie Connectors mithilfe von Microsoft Teams-Desktop- und -Webclients hinzufügen. Die von diesen Connectors bereitgestellten Informationen können jedoch auf allen Clients **angezeigt werden, auch** auf mobilen Geräten.

1. Wenn Sie einem Kanal einen Verbinder hinzufügen möchten, klicken Sie rechts neben einem Kanalnamen auf die **Auslassungspunkte (...),** und klicken Sie dann auf "Verbinder". 

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Benutzeroberfläche von Teams mit ausgewählter Option "Connectors"](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Sie können aus einer Vielzahl von verfügbaren Connectors auswählen und dann auf **"Hinzufügen" klicken.**

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Dialogfelds "Verbinder" mit den verfügbaren Verbindern](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **Benachrichtigung über die Connector-URL-Aktualisierung**
>
> Die Connectors in Teams werden auf eine neue URL umstellen, um die Sicherheit zu erhöhen. Während dieses Übergangs erhalten Sie bestimmte Benachrichtigungen zum Aktualisieren des konfigurierten Connectors für die Verwendung der neuen URL. Es wird dringend empfohlen, den Verbinder sofort zu aktualisieren, um Unterbrechungen der Connectordienste zu verhindern. Die folgenden Schritte müssen zum Aktualisieren der URL befolgt werden:
> 1. Auf der Konfigurationsseite für Connectors wird unter der Schaltfläche "Verwalten" die Meldung "Achtung erforderlich" für die Verbindungen angezeigt, die aktualisiert werden müssen.
> ![Screenshot der Meldung "Aufmerksamkeit erforderlich".](media/Teams_Attention_Required_message.png)
> 2. Bei eingehenden Webhook-Connectors können Benutzer die Verbindung neu erstellen, indem sie einfach **"URL aktualisieren"** auswählen und die neu generierte Webhook-URL verwenden.
> ![Screenshot der Schaltfläche "URL aktualisieren"](media/Teams_update_URL_button.png)
> 3. Bei anderen Connectortypen müsste der Benutzer den Connector entfernen und die Connectorkonfiguration erneut erstellen.
> 4. Nach der erfolgreichen Aktualisierung der URL wird die Meldung "DIE URL ist aktuell" angezeigt.
> ![Screenshot der Meldung "DIE URL ist aktuell".](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>Entwickeln von benutzerdefinierten Connectors
----------------------------

Sie können auch benutzerdefinierte Connectors sowie eingehende und ausgehende Webhooks erstellen. Weitere Informationen finden Sie in der [Dokumentation für Entwickler](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
