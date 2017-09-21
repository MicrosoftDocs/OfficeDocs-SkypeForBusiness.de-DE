---
title: "Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: tutorial
ms.service: msteams
description: "Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bfd68ee3671d7f0cc073d35c79013f0d6c3d7f26
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
=======================================================

Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden. Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, Wunderlist, GitHub und VSTS innerhalb des Chatstroms in ihrem Team erhalten.

Jedes Mitglied eines Teams kann das Team über die Connectors mit beliebten Clouddiensten verbinden, und alle Teammitglieder werden über Aktivitäten aus diesem Dienst benachrichtigt. Wenn ein Benutzer aus einem Team entfernt wird, funktionieren Connectors, die dieser Benutzer zum Team hinzugefügt hat, nicht mehr. Geplante Besprechungen funktionieren weiterhin, da sie im Gruppenkalender enthalten sind.

Office 365-Connectors können für Microsoft Teams- und Office 365-Gruppen verwendet werden, sodass alle Mitglieder leichter auf dem Laufenden bleiben und relevante Informationen schnell erhalten können. Da Microsoft Teams und Exchange das gleiche Connector-Modell nutzen, können Sie auf beiden Plattformen die gleichen Connectors verwenden.

Zurzeit können Connectors mit den Microsoft Teams-Desktopclients und -Webclients hinzugefügt werden. Von diesen Connectors gepostete Informationen können jedoch mit **allen Clients**, auch den mobilen Clients, angezeigt werden.

1.  Um einen Connector zu einem Kanal hinzuzufügen, klicken Sie auf das **Auslassungszeichen (…)** rechts neben einem Kanalnamen und dann auf **Connectors**.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Benutzer können aus einer Vielfalt verfügbarer Connectors auswählen und dann auf **Hinzufügen** klicken.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Entwickeln von benutzerdefinierten Connectors
-----------------------------

Sie können ganz leicht benutzerdefinierte Connectors entwickeln, die in Ihre branchenspezifischen Anwendungen integriert werden können. Sie können den integrierten Connector **Incoming Webhook** (Eingehender Webhook) verwenden, um einen Endpunkt für einen Kanal zu erstellen, der mithilfe von HTTP-Post-Methoden Daten aus beliebigen Anwendungen abruft.

1.  Fügen Sie den **eingehenden Webhook** wie jeden anderen Connector hinzu.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Um einen Webhook zu erstellen, geben Sie einen **Namen** an, aktualisieren Sie bei Bedarf das Webhook-Image, und klicken Sie auf **Erstellen**.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Anwendungen, die Daten mithilfe von Push in diesen Kanal übertragen, benötigen die URL des Webhook-Connectors. Eine **eindeutige URL** wird erstellt, wenn Sie den **Webhook** erstellen. Geben Sie Ihren Entwicklern diese URL, damit sie bei Bedarf ihre Anwendungen für das Übertragen von Anwendungen mithilfe von Push konfigurieren können.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Wenn eine externe Anwendung mithilfe von Push Daten an einen Connector überträgt, wird die Nachricht in der Kanalunterhaltungsliste als spezielle Nachricht, das heißt als **Connectorkartennachricht**, angezeigt.

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Entwickler können ihre Anwendungen für das Erstellen dieser Karten konfigurieren, indem sie eine HTTP-Anforderung mit einer einfachen JSON-Nutzlast an eine Webhook-Adresse von Microsoft Teams senden, die eine vom Assistenten bereitgestellte eindeutige URL dieses Endpunkts darstellt. Ihre Entwickler finden im Microsoft Developer Network unter [Erste Schritte mit Office 365-Connectors für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783) detaillierte Anleitungen und Connector-Beispiele. Als weitere Ressourcen stehen [Verbinden von Apps mit Ihren Gruppen in Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) und [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) zur Verfügung.
