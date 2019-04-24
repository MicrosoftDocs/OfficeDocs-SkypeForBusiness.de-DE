---
title: Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdb4184ed203994f1275c9c074371655a627b1fe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195095"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
=======================================================

Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden. Mit Connectors können Ihre Benutzer Microsoft-Teams von häufig verwendete Dienste wie Twitter, Trello, Wunderlist, GitHub und Azure DevOps Services im Chat Stream in ihr Team Updates erhalten.

Ein beliebiges Mitglied eines Teams kann ihr Team mit beliebte Clouddiensten mit Connectors verbinden, wenn die Teamberechtigungen zulassen, und alle Teammitglieder Aktivitäten von diesem Dienst benachrichtigt werden. Verbinder bleiben auch nach der Member-Funktion, die Anfangs Setup hat, die der Connector verlassen hat. Jedes Teammitglied mit den Berechtigungen zum hinzufügen/entfernen kann Konnektoren Setup anderer Mitglieder ändern.

Office 365-Connectors können mit beiden Microsoft-Teams verwendet werden und Office 365-Gruppen, erleichtert es für alle Mitglieder synchronisiert bleiben und relevanten Informationen schnell zu erhalten. Microsoft-Teams und Exchange verwenden dasselbe Modell Connector, das Sie die gleichen Connectors in beiden Plattformen verwenden kann. Dabei ist zu beachten, jedoch, deaktivieren Connectors für die Office 365-Gruppe, die ein Team abhängig ist die Möglichkeit zum Erstellen von Konnektoren für dieses Team auch deaktivieren.

Zurzeit können Connectors mit den Microsoft Teams-Desktopclients und -Webclients hinzugefügt werden. Von diesen Connectors gepostete Informationen können jedoch mit **allen Clients**, auch den mobilen Clients, angezeigt werden.

1.  Um einen Connector zu einem Kanal hinzuzufügen, klicken Sie auf das **Auslassungszeichen (…)** rechts neben einem Kanalnamen und dann auf **Connectors**.

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit ausgewähltem Kanalnamen und ausgewählter Option „Connectors“](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Benutzer können aus einer Vielfalt verfügbarer Connectors auswählen und dann auf **Hinzufügen** klicken.

    ![Screenshot des Dialogfelds „Connectors“ mit den Connectors, die hinzugefügt werden können](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Entwickeln von benutzerdefinierten Connectors
-----------------------------

Sie können ganz leicht benutzerdefinierte Connectors entwickeln, die in Ihre branchenspezifischen Anwendungen integriert werden können. Sie können den integrierten Connector **Incoming Webhook** (Eingehender Webhook) verwenden, um einen Endpunkt für einen Kanal zu erstellen, der mithilfe von HTTP-Post-Methoden Daten aus beliebigen Anwendungen abruft.

1.  Fügen Sie den **eingehenden Webhook** wie jeden anderen Connector hinzu.

    ![Screenshot der Option zum Hinzufügen des Connectors „Incoming Webhook“ (Eingehender Webhook)](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Um einen Webhook zu erstellen, geben Sie einen **Namen** an, aktualisieren Sie bei Bedarf das Webhook-Image, und klicken Sie auf **Erstellen**.

    ![Screenshot der Konfigurationsseite für den Connector „Incoming Webhook“ (Eingehender Webhook) ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Anwendungen, die Daten mithilfe von Push in diesen Kanal übertragen, benötigen die URL des Webhook-Connectors. Eine **eindeutige URL** wird erstellt, wenn Sie den **Webhook** erstellen. Geben Sie Ihren Entwicklern diese URL, damit sie bei Bedarf ihre Anwendungen für das Übertragen von Anwendungen mithilfe von Push konfigurieren können.

    ![Screenshot der eindeutigen URL des Webhooks](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Wenn eine externe Anwendung mithilfe von Push Daten an einen Connector überträgt, wird die Nachricht in der Kanalunterhaltungsliste als spezielle Nachricht, das heißt als **Connectorkartennachricht**, angezeigt.

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Connectorkartennachricht](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Entwickler können ihre Anwendungen für das Erstellen dieser Karten konfigurieren, indem sie eine HTTP-Anforderung mit einer einfachen JSON-Nutzlast an eine Webhook-Adresse von Microsoft Teams senden, die eine vom Assistenten bereitgestellte eindeutige URL dieses Endpunkts darstellt. Ihre Entwickler finden im Microsoft Developer Network unter [Erste Schritte mit Office 365-Connectors für Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors) detaillierte Anleitungen und Connector-Beispiele. Als weitere Ressourcen stehen [Verbinden von Apps mit Ihren Gruppen in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) und [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) zur Verfügung.
