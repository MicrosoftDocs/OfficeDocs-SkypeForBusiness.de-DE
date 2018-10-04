---
title: Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Erfahren Sie, wie eine vorhandene AlwaysOn Availability Group in Skype Weitere Skype für Business Server-Datenbanken für Business Server hinzuzufügen.'
ms.openlocfilehash: e5217ba16234ea96f205d8ee89b6d31ac6b2df6c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372060"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="ae65c-103">Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ae65c-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="ae65c-104">**Zusammenfassung:** Erfahren Sie, wie eine vorhandene AlwaysOn Availability Group in Skype Weitere Skype für Business Server-Datenbanken für Business Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ae65c-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="ae65c-105">Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="ae65c-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="ae65c-106">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="ae65c-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="ae65c-107">Failover es auf das primäre Replikat.</span><span class="sxs-lookup"><span data-stu-id="ae65c-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="ae65c-108">Legen Sie die SQL Server-FQDN der AlwaysOn Availability Group im Topologie-Generator auf den vollqualifizierten Domänennamen des primären Knotens der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ae65c-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="ae65c-109">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae65c-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="ae65c-110">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="ae65c-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="ae65c-111">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ae65c-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="ae65c-112">Geben Sie am unteren Rand der Seite in das Feld **SQL Server-FQDN** in den FQDN des primären Knoten die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="ae65c-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="ae65c-p103">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae65c-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="ae65c-116">Verwenden Sie SQL Server Management Studio die AlwaysOn Availability Group die neue Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae65c-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

