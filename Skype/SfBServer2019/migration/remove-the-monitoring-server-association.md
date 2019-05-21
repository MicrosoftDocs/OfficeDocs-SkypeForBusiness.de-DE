---
title: Entfernen der Zuordnung der Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301097"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="5aebb-105">Entfernen der Zuordnung der Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="5aebb-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="5aebb-106">Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5aebb-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="5aebb-107">Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5aebb-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="5aebb-108">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5aebb-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="5aebb-109">So entfernen Sie die Monitoring Server-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="5aebb-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="5aebb-110">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="5aebb-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="5aebb-111">Navigieren Sie zum Knoten Legacy Installationen.</span><span class="sxs-lookup"><span data-stu-id="5aebb-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="5aebb-112">Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**, je nachdem, wo der Monitoring Server definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5aebb-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="5aebb-113">Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="5aebb-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5aebb-114">**Survivable-Branch** -Appliances auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="5aebb-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="5aebb-115">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Überwachungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5aebb-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="5aebb-116">Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemeine** > **Zuordnungen**das Kontrollkästchen **Überwachungs Server zuordnen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5aebb-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5aebb-117">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Überwachungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5aebb-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="5aebb-118">Klicken Sie mit der rechten Maustaste auf den Überwachungs Server, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="5aebb-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="5aebb-119">Klicken Sie unter **abhängige Speicher löschen**auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5aebb-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="5aebb-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Bereitstellungs-Assistenten von Skype for Business Server nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="5aebb-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

