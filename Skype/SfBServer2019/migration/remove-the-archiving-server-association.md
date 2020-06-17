---
title: Entfernen der Zuordnung des Archivierungsservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Zum Entfernen eines Archivierungsserver müssen Sie die Abhängigkeit von der zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752137"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="276a5-105">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="276a5-105">Remove the Archiving server association</span></span>

<span data-ttu-id="276a5-106">Zum Entfernen eines Archivierungsserver müssen Sie die Abhängigkeit von der zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="276a5-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="276a5-107">Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="276a5-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="276a5-108">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="276a5-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="276a5-109">So entfernen Sie die Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="276a5-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="276a5-110">Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="276a5-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="276a5-111">Navigieren Sie zum Knoten Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="276a5-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="276a5-112">Erweitern Sie im Topologie-Generator die **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**, je nachdem, wo die Archivierungsserver definiert ist.</span><span class="sxs-lookup"><span data-stu-id="276a5-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="276a5-113">Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen der Zweigstelle, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="276a5-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="276a5-114">**Survivable Branch Appliances** in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="276a5-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="276a5-115">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, das dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="276a5-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="276a5-116">Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemeine**  >  **Zuordnungen**das Kontrollkästchen **Archivierungsserver zuordnen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="276a5-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="276a5-117">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem zu entfernenden Archivierungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="276a5-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="276a5-118">Klicken Sie mit der rechten Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="276a5-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="276a5-119">Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="276a5-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="276a5-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die Skype for Business Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="276a5-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

