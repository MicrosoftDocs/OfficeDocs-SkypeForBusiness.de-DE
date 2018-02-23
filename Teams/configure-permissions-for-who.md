---
title: "Konfigurieren von Berechtigungen für Who"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
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

Weitere Informationen zum Verwalten von Microsoft Graph-Berechtigungsbereichen finden Sie unter [Berechtigungsbereiche](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).
 
Weitere Informationen zu Microsoft Graph-Berechtigungen finden Sie unter [Microsoft Graph-Berechtigungsreferenz](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).