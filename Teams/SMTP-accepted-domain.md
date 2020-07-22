---
title: Hinzufügen der SMTP-Domäne "Teams" als zugelassene Absenderdomäne in Exchange Online
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
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Microsoft Teams-SMTP-Domäne als zulässige Absenderdomäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c60620a10bc5bb0cff37547313731ba214944ffc
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201139"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online 
=============================================================================

Unabhängig davon, ob Sie eine Microsoft 365-Gruppe in der Admin-Konsole oder mithilfe von Outlook erstellen, wird Exchange Online verwendet, um Benachrichtigungen über ein Teammitglied zu senden, das einer Gruppe hinzugefügt wird. Diese Nachrichten werden von Ihrem Mandanten generiert, da diese den standardmäßigen SMTP-FQDN der Domäne darstellen.

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams verwendet Microsoft Exchange Online, um Benachrichtigungen an Teammitglieder zu senden, wenn diese hinzugefügt wurden. Der Unterschied ist der Domänen-FQDN der SMTP-Nachricht: "@Email. Teams.Microsoft.com" für kommerzielle/geschäftliche Mandanten und "@gcc-Email.Teams.Microsoft.com" für Regierungs Pächter und kann durch Spamfilterung abgefangen werden.

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Um das beste Ergebnis und den nahtlosen Betrieb zu erzielen, sollten Sie in Ihrer Exchange Online-Spam Konfiguration die SMTP-Domäne "Microsoft Teams" zu Ihrer Liste "zugelassene Absenderdomänen" hinzufügen:

![Screenshot des Abschnitts "Zulassungslisten" der Spam Konfigurationseinstellungen](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
