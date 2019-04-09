---
title: Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Informationen Sie zum Microsoft-Teams SMTP-Domäne als Absenderdomäne zulässigen in Exchange Online zusätzliche zum Senden von Benachrichtigungen an die Teammitglieder.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4a1a94bec69b1c7953dea6802d62058b04700bb
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516807"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="e113e-103">Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e113e-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="e113e-p101">Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.</span><span class="sxs-lookup"><span data-stu-id="e113e-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="e113e-107">Teams verwendet Microsoft Exchange Online sowie zum Senden von Benachrichtigungen an die Teammitglieder, wenn sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e113e-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="e113e-108">Der Unterschied wird der vollqualifizierte Domänenname der SMTP-Nachricht ist für kommerzielle/Business Mandanten "@email.teams.microsoft.com" und "@GCC-email.teams.com" für Behörden Mandanten und Spamfilterung abgefangen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="e113e-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="e113e-110">Berücksichtigen Sie für beste Suchergebnisse und nahtlos Vorgang die Microsoft-Teams SMTP-Domäne der Liste "zulässige Absenderdomänen" in Ihrer Exchange Online-Spam-Konfiguration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e113e-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Screenshot des Abschnitts „Zulassungslisten“ in den Konfigurationseinstellungen für Spam in Exchange Online](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
