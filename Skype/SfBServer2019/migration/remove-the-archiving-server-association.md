---
title: Entfernen der Zuordnung des Archivierungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie einen Archivierungsserver entfernen möchten, müssen Sie ändern oder löschen die Abhängigkeit von der neu zugeordnete Front-End-Pool Front-End-Server, Survivable Branch Appliance und Survivable Branch Server. Sie bearbeiten die Eigenschaften des Front-End-Pools, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit deaktivieren, und Sie den Server im Topologie-Generator löschen, werden Sie benachrichtigt, dass das Store-Objekt zugeordnete Datenbank im Topologie-Generator ebenfalls gelöscht werden.
ms.openlocfilehash: 15e6b33decb11ce7ed4550b0d84cc346a0baf073
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884400"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="e5ef4-105">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="e5ef4-105">Remove the Archiving server association</span></span>

<span data-ttu-id="e5ef4-106">Wenn Sie einen Archivierungsserver entfernen möchten, müssen Sie ändern oder löschen die Abhängigkeit von den zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="e5ef4-107">Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="e5ef4-108">Nachdem Sie die Abhängigkeit deaktivieren und den Server im Topologie-Generator löschen, werden Sie benachrichtigt, dass das Store-Objekt zugeordnete Datenbank im Topologie-Generator ebenfalls gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="e5ef4-109">So entfernen Sie die Archivierungsserver-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="e5ef4-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="e5ef4-110">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e5ef4-111">Navigieren Sie zu der Knoten legacy installieren.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="e5ef4-112">Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigniederlassungen**, je nachdem, wo der Archivierungsserver definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="e5ef4-113">Wenn Sie einen Survivable Branch Server zugeordnete verfügen, erweitern Sie **Zweigniederlassungen**, erweitern Sie Namen des Zweigniederlassung und dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5ef4-114">**Survivable Branch Appliances** auf der Benutzeroberfläche gilt für Survivable Branch Server- und Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="e5ef4-115">Mit der rechten Maustaste die Pools, Server oder Gerät, das den Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="e5ef4-116">**Bearbeiten von Eigenschaften**unter **Allgemein** > **Zuordnungen**, deaktivieren Sie das Kontrollkästchen **Archivierungsserver zuordnen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e5ef4-117">Wiederholen Sie den vorherigen Schritt für jeden Pool, Server oder Geräte, die zu entfernende Archivierungsserver zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="e5ef4-118">Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="e5ef4-119">**Abhängige Speicher löschen**klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="e5ef4-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann die Skype für Business Server-Bereitstellungs-Assistenten aus, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="e5ef4-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

