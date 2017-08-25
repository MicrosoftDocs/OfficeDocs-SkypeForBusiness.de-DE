---
title: "Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "Hier erfahren Sie, wie Sie die SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden."
ms.openlocfilehash: 5e006f8074bd7d5675d84502ccafb0adf29698e3
ms.sourcegitcommit: 41c623bc0fe9267000f296472a2ee2be8f65a43a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online 
=============================================================================

Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams verwendet Microsoft Exchange Online außerdem zum Senden von Benachrichtigungen an Teammitglieder, wenn diese hinzugefügt wurden. Der Unterschied liegt darin, dass der Domänen-FQDN der SMTP-Nachricht „@email.teams.microsoft.com“ lautet und von einem Spamfilter abgefangen werden könnte. Wie Sie im folgenden Bild sehen, betrachtet Outlook diese Nachricht als von einem externen Absender stammend. Daher gelten für die Nachricht die Standardsicherheitsfunktionen, sodass zum Beispiel Bilder und bestimmte Inhalte blockiert werden.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Die besten Ergebnisse und einen nahtlosen Betrieb können Sie erzielen, indem Sie die SMTP-Domäne von Microsoft Teams zu Ihrer Liste „Akzeptierte Domänen“ in der Exchange Online-Spamkonfiguration hinzufügen:

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
