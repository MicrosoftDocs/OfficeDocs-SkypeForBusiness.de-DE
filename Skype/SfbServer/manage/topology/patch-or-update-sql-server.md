---
title: Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Zusammenfassung: Informieren Sie sich über die erforderlichen zusätzlichen Schritte nach dem Sie den Patch oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.'
ms.openlocfilehash: 8f5c9131e59ccedd7f590f696fe53aa6c18c7d22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server-2015"></a><span data-ttu-id="8d076-103">Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d076-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d076-104">**Zusammenfassung:** Erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.</span><span class="sxs-lookup"><span data-stu-id="8d076-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d076-105">Nach dem Patchen einer Back End-Server, der Teil einer AlwaysOn Availability Group ist, müssen Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8d076-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="8d076-106">Patchen oder Aktualisieren einer SQL Server, die Teil einer AlwaysOn Availability Group ist</span><span class="sxs-lookup"><span data-stu-id="8d076-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="8d076-107">Installieren des Updates auf Ihre Skype für Business Server oder Server.</span><span class="sxs-lookup"><span data-stu-id="8d076-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="8d076-108">Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype für Business-Verwaltungsshell (mit einem Konto an, entsprechend Berechtigung zum Anwenden von Änderungen auf die SQL-AlwaysOn-Datenbanken ist, angemeldet) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8d076-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="8d076-109">Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn Availability Group ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="8d076-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

