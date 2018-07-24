---
title: Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7298254b-bc33-450e-846a-2612f6dc7006
description: 'Zusammenfassung: Informieren Sie sich über die erforderlichen zusätzlichen Schritte nach dem Sie den Patch oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.'
ms.openlocfilehash: 7227bdc61e7accbdd6f6e760e1a33d9a2b76eb30
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982986"
---
# <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="65589-103">Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="65589-103">Patch or update a SQL Server in an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="65589-104">**Zusammenfassung:** Erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für Business Server ist.</span><span class="sxs-lookup"><span data-stu-id="65589-104">**Summary:** Find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
<span data-ttu-id="65589-105">Nach dem Patchen einer Back End-Server, der Teil einer AlwaysOn Availability Group ist, müssen Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="65589-105">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>
  
### <a name="patching-or-updating-a-sql-server-that-is-part-of-an-alwayson-availability-group"></a><span data-ttu-id="65589-106">Patchen oder Aktualisieren einer SQL Server, die Teil einer AlwaysOn Availability Group ist</span><span class="sxs-lookup"><span data-stu-id="65589-106">Patching or updating a SQL Server that is part of an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="65589-107">Installieren des Updates auf Ihre Skype für Business Server oder Server.</span><span class="sxs-lookup"><span data-stu-id="65589-107">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="65589-108">Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype für Business-Verwaltungsshell (mit einem Konto an, entsprechend Berechtigung zum Anwenden von Änderungen auf die SQL-AlwaysOn-Datenbanken ist, angemeldet) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="65589-108">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="65589-109">Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn Availability Group ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="65589-109">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
    

