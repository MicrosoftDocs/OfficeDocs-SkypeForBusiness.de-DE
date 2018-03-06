---
title: "Konfigurieren von Berechtigungen für Who"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Praktische Anleitungen für die Bereitstellung von Cloud-VoIP-Funktionen in Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="d06cf-103">Konfigurieren von Berechtigungen für Who</span><span class="sxs-lookup"><span data-stu-id="d06cf-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="d06cf-104">Benutzer können die Who-App für Microsoft Teams verwenden, um Fragen zu stellen und Personen in der Organisation danach zu suchen, woran sie arbeiten und mit wem sie zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d06cf-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="d06cf-105">Um sicherzustellen, dass die Benutzer Who optimal nutzen können, müssen Sie in Microsoft Graph die folgenden Mitgliederberechtigungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d06cf-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="d06cf-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="d06cf-106">Calendars.Read</span></span>

- <span data-ttu-id="d06cf-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="d06cf-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="d06cf-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="d06cf-108">Mail.Read</span></span>

- <span data-ttu-id="d06cf-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d06cf-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="d06cf-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="d06cf-110">People.Read</span></span>

- <span data-ttu-id="d06cf-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="d06cf-111">People.Read.All</span></span>

- <span data-ttu-id="d06cf-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="d06cf-112">Sites.Read.All</span></span>

- <span data-ttu-id="d06cf-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="d06cf-113">User.Read.All</span></span>

<span data-ttu-id="d06cf-114">Weitere Informationen zum Verwalten von Microsoft Graph-Berechtigungsbereichen finden Sie unter [Berechtigungsbereiche](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="d06cf-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="d06cf-115">Weitere Informationen zu Microsoft Graph-Berechtigungen finden Sie unter [Microsoft Graph-Berechtigungsreferenz](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="d06cf-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>