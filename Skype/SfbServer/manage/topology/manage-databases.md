---
title: Verwalten von Datenbanken mit einer AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: erfahren Sie, wie Sie weitere Skype for Business Server-Datenbanken zu einer vorhandenen AlwaysOn-verfügbarkeitsgruppe hinzufügen, und erfahren Sie mehr über die erforderlichen zusätzlichen Schritte, nachdem Sie einen Back-End-Server, der Teil einer AlwaysOn-verfügbarkeitsgruppe ist, in Skype for installieren oder aktualisieren. Business Server.'
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991540"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="fe84a-103">Verwalten von Datenbanken mit einer AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fe84a-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="fe84a-104">Führen Sie die Schritte in diesem Artikel aus, um weitere Skype for Business Server-Datenbanken zu einer vorhandenen AlwaysOn-verfügbarkeitsgruppe in Skype for Business Server hinzuzufügen, und informieren Sie sich über die erforderlichen zusätzlichen Schritte, nachdem Sie einen Back-End-Server, der Teil eines AlwaysOn ist, Patchen oder aktualisieren. Verfügbarkeitsgruppe in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fe84a-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="fe84a-105">Hinzufügen von Datenbanken zu einer AlwaysOn-verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fe84a-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="fe84a-106">Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AlwaysOn-verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="fe84a-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="fe84a-107">Führen Sie einen Failover für das primäre Replikat durch.</span><span class="sxs-lookup"><span data-stu-id="fe84a-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="fe84a-108">Setzen Sie im Topologie-Generator den SQL Server-FQDN der AlwaysOn-verfügbarkeitsgruppe auf den FQDN des primären Knotens dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="fe84a-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="fe84a-109">Öffnen Sie den Topologie-Generator, wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe84a-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="fe84a-110">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="fe84a-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="fe84a-111">Klicken Sie mit der rechten Maustaste auf den SQL Store der neuen AlwaysOn-verfügbarkeitsgruppe, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fe84a-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="fe84a-112">Geben Sie unten auf der Seite im Feld **SQL Server-FQDN** den FQDN des primären Knotens der AlwaysOn-verfügbarkeitsgruppe ein.</span><span class="sxs-lookup"><span data-stu-id="fe84a-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="fe84a-113">Veröffentlichen der Topologie.</span><span class="sxs-lookup"><span data-stu-id="fe84a-113">Publish the topology.</span></span> <span data-ttu-id="fe84a-114">Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="fe84a-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="fe84a-115">Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fe84a-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="fe84a-116">Verwenden Sie SQL Server Management Studio, um die neue Datenbank zur AlwaysOn-verfügbarkeitsgruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe84a-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="fe84a-117">Patchen oder Aktualisieren eines SQL-Servers in einer AlwaysOn-verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="fe84a-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="fe84a-118">Nachdem Sie einen Back-End-Server gepatcht haben, der Teil einer AlwaysOn-verfügbarkeitsgruppe ist, müssen Sie die Topologie erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fe84a-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="fe84a-119">Installieren Sie das Update auf Ihrem Skype for Business-Server oder-Server.</span><span class="sxs-lookup"><span data-stu-id="fe84a-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="fe84a-120">Führen Sie den folgenden PowerShell-Befehl in Ihrer Skype for Business-Verwaltungsshell aus (angemeldet mit einem Konto, das entsprechend berechtigt ist, Änderungen auf die SQL AlwaysOn-Datenbanken anzuwenden) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fe84a-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="fe84a-121">Wobei [sqlpool.contoso.com] durch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer AlwaysOn-verfügbarkeitsgruppe ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="fe84a-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
