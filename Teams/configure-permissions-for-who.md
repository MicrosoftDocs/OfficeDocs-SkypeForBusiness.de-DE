---
title: Konfigurieren von Berechtigungen für Who
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860215"
---
<a name="configure-permissions-for-who"></a>Konfigurieren von Berechtigungen für Who
=============================

Benutzer können die Who-App für Microsoft Teams verwenden, um Fragen zu stellen und Personen in der Organisation danach zu suchen, woran sie arbeiten und mit wem sie zusammenarbeiten.

Um sicherzustellen, dass die Benutzer Who optimal nutzen können, müssen Sie in Microsoft Graph die folgenden Mitgliederberechtigungen aktivieren.

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

Weitere Informationen zum Verwalten von Microsoft Graph-Berechtigungsbereichen finden Sie unter [Berechtigungsbereiche](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Weitere Informationen zu Microsoft Graph-Berechtigungen finden Sie unter [Microsoft Graph-Berechtigungsreferenz](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).