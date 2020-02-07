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
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Microsoft Teams-SMTP-Domäne als zulässige Absenderdomäne in Exchange Online hinzufügen, um Benachrichtigungen an Teammitglieder zu senden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3455c56ab3d51b83d2d5bc27d41824b6fe16ae9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834765"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Hinzufügen der SMTP-Domäne von Microsoft Teams als akzeptierte Senderdomäne in Exchange Online 
=============================================================================

Unabhängig davon, ob Sie eine Office 365-Gruppe in der Administratorkonsole oder über Outlook erstellen, werden Benachrichtigungen über zu einer Gruppe hinzugefügte Teammitglieder mit Exchange Online gesendet. Diese Nachrichten werden von Ihrem Mandanten generiert, da sie den standardmäßigen SMTP-FQDN Ihrer Domäne darstellen.

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams verwendet Microsoft Exchange Online, um Benachrichtigungen an Teammitglieder zu senden, wenn diese hinzugefügt wurden. Der Unterschied ist der Domänen-FQDN der SMTP-Nachricht: "@Email. Teams.Microsoft.com" für kommerzielle/geschäftliche Mandanten und "@gcc-Email.Teams.com" für Regierungs Pächter und kann durch Spamfilterung abgefangen werden.

![Screenshot eines Nachrichtenkopfs mit einem Benutzer, der zu einer Gruppe hinzugefügt wurde.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Um das beste Ergebnis und den nahtlosen Betrieb zu erzielen, sollten Sie in Ihrer Exchange Online-Spam Konfiguration die SMTP-Domäne "Microsoft Teams" zu Ihrer Liste "zugelassene Absenderdomänen" hinzufügen:

![Screenshot des Abschnitts "Zulassungslisten" der Spam Konfigurationseinstellungen](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
