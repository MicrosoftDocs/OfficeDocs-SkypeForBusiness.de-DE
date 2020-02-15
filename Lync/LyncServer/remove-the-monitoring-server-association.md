---
title: Entfernen der Monitoring Server-Zuordnung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746558cc47a7ed5ef7f59abe4e4f0771cc514d47
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="0a276-102">Entfernen der Monitoring Server-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="0a276-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a276-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0a276-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0a276-104">Um die Monitoring Server zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0a276-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="0a276-105">Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0a276-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="0a276-106">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="0a276-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="0a276-107">So entfernen Sie die Monitoring Server-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="0a276-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="0a276-108">Öffnen Sie die lync Server 2013 Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="0a276-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="0a276-109">Navigieren Sie zum Knoten lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0a276-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="0a276-110">Erweitern Sie im Topologie-Generator die **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**basierend auf der Definition des Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="0a276-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="0a276-111">Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen der Zweigstelle, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="0a276-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a276-112"><STRONG>Survivable Branch Appliances</STRONG> in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="0a276-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="0a276-113">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, das dem Monitoring Server zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0a276-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="0a276-114">Deaktivieren Sie in **Eigenschaften bearbeiten**, unter **Allgemein**, unter **Zuordnungen** das Kontrollkästchen **Monitoring Server zuordnen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a276-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="0a276-115">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Monitoring Server zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0a276-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="0a276-116">Klicken Sie mit der rechten Maustaste auf den Monitoring Server, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0a276-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="0a276-117">Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a276-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="0a276-118">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="0a276-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

