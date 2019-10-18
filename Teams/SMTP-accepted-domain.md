---
title: Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Erfahren Sie, wie Sie die Microsoft Teams-SMTP-Domäne als zulässige Absenderdomäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae8be5c4b596b8815b8677b6214163924cbb183
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567128"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="464ad-103">Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="464ad-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="464ad-p101">Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.</span><span class="sxs-lookup"><span data-stu-id="464ad-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="464ad-107">Teams verwendet Microsoft Exchange Online, um Benachrichtigungen an Teammitglieder zu senden, wenn diese hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="464ad-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="464ad-108">Der Unterschied ist der Domänen-FQDN der SMTP-Nachricht: "@Email. Teams.Microsoft.com" für kommerzielle/geschäftliche Mandanten und "@gcc-Email.Teams.com" für Regierungs Pächter und kann durch Spamfilterung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="464ad-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="464ad-110">Um das beste Ergebnis und den nahtlosen Betrieb zu erzielen, sollten Sie in Ihrer Exchange Online-Spam Konfiguration die SMTP-Domäne "Microsoft Teams" zu Ihrer Liste "zugelassene Absenderdomänen" hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="464ad-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Screenshot des Abschnitts "Zulassungslisten" der Spam Konfigurationseinstellungen](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
