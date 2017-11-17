---
title: "Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie die SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: eed3eb36ae53b7306c0a46e1bccb14286b5af3a8
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online 
=============================================================================

Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams verwenden Microsoft Exchange Online auch zum Senden von Benachrichtigungen zu Teammitgliedern, wenn diese hinzugefügt wurden. Der Unterschied liegt darin, dass der Domänen-FQDN der SMTP-Nachricht „@email.teams.microsoft.com“ lautet und von einem Spamfilter abgefangen werden könnte. Wie Sie im folgenden Bild sehen, betrachtet Outlook diese Nachricht als von einem externen Absender stammend. Daher gelten für die Nachricht die Standardsicherheitsfunktionen, sodass zum Beispiel Bilder und bestimmte Inhalte blockiert werden.

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Die besten Ergebnisse und einen nahtlosen Betrieb können Sie erzielen, indem Sie die SMTP-Domäne von Microsoft Teams zu Ihrer Liste „Akzeptierte Domänen“ in der Exchange Online-Spamkonfiguration hinzufügen:

![Screenshot des Abschnitts „Zulassungslisten“ in den Konfigurationseinstellungen für Spam in Exchange Online](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
