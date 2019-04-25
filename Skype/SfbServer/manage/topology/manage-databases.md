---
title: Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Informationen Sie zum Hinzufügen von weitere Skype für Business Server-Datenbanken zu einer vorhandenen AlwaysOn Availability Group und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Sie den Patch oder aktualisieren Sie einen Back End-Server, der Teil einer AlwaysOn Availability Group in Skype für ist Business-Server.'
ms.openlocfilehash: 8d25e7d3aa1e840be7eb246e6aaa3065b65b7ff7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214694"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="9007e-103">Verwalten von Datenbanken mit einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="9007e-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="9007e-104">Verwenden Sie die Schritte in diesem Artikel zu einer vorhandenen AlwaysOn Availability Group in Skype für Business Server weitere Skype für Business Server-Datenbanken hinzu, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte nach dem Patchen oder aktualisieren Sie einen Back End-Server, die Teil einer AlwaysOn ist Availability Group in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="9007e-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="9007e-105">Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="9007e-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="9007e-106">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="9007e-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="9007e-107">Failover es auf das primäre Replikat.</span><span class="sxs-lookup"><span data-stu-id="9007e-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="9007e-108">Legen Sie die SQL Server-FQDN der AlwaysOn Availability Group im Topologie-Generator auf den vollqualifizierten Domänennamen des primären Knotens der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9007e-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="9007e-109">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9007e-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="9007e-110">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="9007e-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="9007e-111">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9007e-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="9007e-112">Geben Sie am unteren Rand der Seite in das Feld **SQL Server-FQDN** in den FQDN des primären Knoten die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="9007e-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="9007e-113">Veröffentlichen der Topologie.</span><span class="sxs-lookup"><span data-stu-id="9007e-113">Publish the topology.</span></span> <span data-ttu-id="9007e-114">Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="9007e-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="9007e-115">Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9007e-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="9007e-116">Verwenden Sie SQL Server Management Studio die AlwaysOn Availability Group die neue Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="9007e-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="9007e-117">Patchen oder Aktualisieren einer SQL Server in einer AlwaysOn-Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="9007e-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="9007e-118">Nach dem Patchen einer Back End-Server, der Teil einer AlwaysOn Availability Group ist, müssen Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="9007e-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="9007e-119">Installieren des Updates auf Ihre Skype für Business Server oder Server.</span><span class="sxs-lookup"><span data-stu-id="9007e-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="9007e-120">Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype für Business-Verwaltungsshell (mit einem Konto an, entsprechend Berechtigung zum Anwenden von Änderungen auf die SQL-AlwaysOn-Datenbanken ist, angemeldet) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9007e-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="9007e-121">Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (FQDN) Ihrer AlwaysOn Availability Group ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="9007e-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
