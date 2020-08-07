---
title: Hinzufügen der SMTP-Domäne "Teams" als zugelassene Absenderdomäne in Exchange Online
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Microsoft Teams-SMTP-Domäne als zulässige Absenderdomäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582052"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="2ecc7-103">Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ecc7-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="2ecc7-p101">Unabhängig davon, ob Sie eine Microsoft 365-Gruppe in der Admin-Konsole oder mithilfe von Outlook erstellen, wird Exchange Online verwendet, um Benachrichtigungen über ein Teammitglied zu senden, das einer Gruppe hinzugefügt wird. Diese Nachrichten werden von Ihrem Mandanten generiert, da diese den standardmäßigen SMTP-FQDN der Domäne darstellen.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-p101">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="2ecc7-107">Teams verwendet Microsoft Exchange Online, um Benachrichtigungen an Teammitglieder zu senden, wenn diese hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="2ecc7-108">Der Unterschied ist der Domänen-FQDN der SMTP-Nachricht: "@Email. Teams.Microsoft.com" für kommerzielle/geschäftliche Mandanten und "@gcc-Email.Teams.Microsoft.com" für Regierungs Pächter und kann durch Spamfilterung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="2ecc7-110">Um das beste Ergebnis und den nahtlosen Betrieb zu erzielen, sollten Sie in Ihrer Exchange Online-Spam Konfiguration die SMTP-Domäne "Microsoft Teams" zu Ihrer Liste "zugelassene Absenderdomänen" hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2ecc7-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Screenshot des Abschnitts "Zulassungslisten" der Spam Konfigurationseinstellungen](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
