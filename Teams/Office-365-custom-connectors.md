---
title: Verwenden von Microsoft 365 und benutzerdefinierten Connectors
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 33a407de891f0d988b1fb32988556059c6adc2e0
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778591"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Verwenden von Microsoft 365 und benutzerdefinierten Connectors in Microsoft Teams
=======================================================

Connectors halten Ihr Team auf dem neuesten Stand, indem Sie häufig verwendete Inhalte und dienstupdates direkt in einem Kanal bereitstellen. Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, wunderlist, GitHub und Azure DevOps-Diensten innerhalb des Chat-Streams in Ihrem Team erhalten.

Jedes Mitglied eines Teams kann sein Team mit den gängigen Cloud-Diensten mit den Connectors verbinden, wenn die Team Berechtigungen dies zulassen, und alle Teammitglieder werden über die Aktivitäten dieses Diensts benachrichtigt. Connectors funktionieren auch dann weiterhin, wenn das Mitglied, das den Connector zunächst eingerichtet hat, den Link verlassen hat. Jedes Teammitglied, das über die Berechtigungen für Faxkomponente verfügt, kann Connectors-Setup von anderen Mitgliedern ändern.

Microsoft 365-Connectors können sowohl mit Microsoft Teams als auch mit Microsoft 365-Gruppen verwendet werden, wodurch es für alle Mitglieder einfacher ist, synchron zu bleiben und relevante Informationen schnell zu erhalten. Sowohl Microsoft Teams als auch Exchange verwenden das gleiche Connector-Modell, mit dem Sie dieselben Connectors in beiden Plattformen verwenden können. Beachten Sie jedoch, dass das Deaktivieren von Connectors für die Office 365-Gruppe, von der ein Team abhängig ist, auch die Möglichkeit zum Erstellen von Connectors für dieses Team deaktiviert.

<a name="add-a-connector-to-a-channel"></a>Hinzufügen eines Verbinders zu einem Kanal
----------------------------

Derzeit können Sie mithilfe von Microsoft Teams-Desktop-und-Webclienten Connectors hinzufügen. Informationen, die von diesen Konnektoren gepostet werden, können jedoch auf **allen Clients** , einschließlich Handy, angezeigt werden.

1. Wenn Sie einen Verbinder zu einem Kanal hinzufügen möchten, klicken Sie auf die **Auslassungszeichen (...)** rechts neben einem Kanalnamen, und klicken Sie dann auf **Verbinder**.

    ![Screenshot der Benutzeroberfläche von Teams mit ausgewählter Option "Verbinder".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Sie können aus einer Vielzahl von verfügbaren Connectors auswählen und dann auf **Hinzufügen**klicken.

    ![Screenshot des Dialogfelds "Verbinder" mit verfügbaren Connectors](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Entwickeln von benutzerdefinierten Connectors
----------------------------

Sie können auch benutzerdefinierte Connectors sowie eingehende und ausgehende webhooks erstellen. Weitere Informationen finden Sie in der [Dokumentation für Entwickler](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).
