---
title: "Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: solution
ms.service: msteams
description: "Hier erfahren Sie, wie Sie die SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b7cd8ce2a874afee524da36c84248703155ec117
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="c7d12-103">Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Domäne in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c7d12-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="c7d12-p101">Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.</span><span class="sxs-lookup"><span data-stu-id="c7d12-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="c7d12-p102">Teams verwenden Microsoft Exchange Online auch zum Senden von Benachrichtigungen zu Teammitgliedern, wenn diese hinzugefügt wurden. Der Unterschied liegt darin, dass der Domänen-FQDN der SMTP-Nachricht „@email.teams.microsoft.com“ lautet und von einem Spamfilter abgefangen werden könnte. Wie Sie im folgenden Bild sehen, betrachtet Outlook diese Nachricht als von einem externen Absender stammend. Daher gelten für die Nachricht die Standardsicherheitsfunktionen, sodass zum Beispiel Bilder und bestimmte Inhalte blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="c7d12-p102">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added. The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering. As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="c7d12-109">Die besten Ergebnisse und einen nahtlosen Betrieb können Sie erzielen, indem Sie die SMTP-Domäne von Microsoft Teams zu Ihrer Liste „Akzeptierte Domänen“ in der Exchange Online-Spamkonfiguration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c7d12-109">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
