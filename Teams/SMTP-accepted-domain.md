---
title: Fügen Sie die Microsoft-Teams SMTP-Domäne als Absenderdomäne zulässigen in Exchange Online hinzu
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: anprakas
search.appverid: MET150
description: Informationen Sie zum Microsoft-Teams SMTP-Domäne als Absenderdomäne zulässigen in Exchange Online zusätzliche zum Senden von Benachrichtigungen an die Teammitglieder.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f94b18994e277b90f96bc4fdbdefaa0b1f7a72e8
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789050"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="7bc6c-103">Fügen Sie die Microsoft-Teams SMTP-Domäne als Absenderdomäne zulässigen in Exchange Online hinzu</span><span class="sxs-lookup"><span data-stu-id="7bc6c-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="7bc6c-p101">Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.</span><span class="sxs-lookup"><span data-stu-id="7bc6c-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="7bc6c-107">Teams verwendet Microsoft Exchange Online sowie zum Senden von Benachrichtigungen an die Teammitglieder, wenn sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="7bc6c-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="7bc6c-108">Der Unterschied wird der vollqualifizierte Domänenname der SMTP-Nachricht ist für Werbung/Business Mandanten "@email.teams.microsoft.com" und "@GCC-email.teams.com" für Behörden Mandanten und Spamfilterung abgefangen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="7bc6c-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commerical/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot eines Beispiels für die Überschrift einer Outlook-E-Mail-Nachricht, aus der hervorgeht, dass ein Benutzer zu einer Gruppe hinzugefügt wurde](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="7bc6c-110">Berücksichtigen Sie für beste Suchergebnisse und nahtlos Vorgang die Microsoft-Teams SMTP-Domäne der Liste "zulässige Absenderdomänen" in Ihrer Exchange Online-Spam-Konfiguration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7bc6c-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Screenshot des Abschnitts „Zulassungslisten“ in den Konfigurationseinstellungen für Spam in Exchange Online](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
