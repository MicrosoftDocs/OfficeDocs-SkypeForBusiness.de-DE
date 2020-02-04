---
title: Entfernen der Zuordnung der Monitoring Server
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
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="95934-102">Entfernen der Zuordnung der Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="95934-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95934-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="95934-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="95934-104">Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95934-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="95934-105">Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="95934-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="95934-106">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="95934-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="95934-107">So entfernen Sie die Monitoring Server-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="95934-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="95934-108">Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="95934-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="95934-109">Navigieren Sie zum lync Server 2010-Knoten.</span><span class="sxs-lookup"><span data-stu-id="95934-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="95934-110">Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellen**, basierend auf der Definition des Überwachungsservers.</span><span class="sxs-lookup"><span data-stu-id="95934-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="95934-111">Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="95934-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95934-112"><STRONG>Survivable-Branch-Appliances</STRONG> auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="95934-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="95934-113">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Überwachungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="95934-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="95934-114">Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemein**unter **Zuordnungen**das Kontrollkästchen **Überwachungs Server zuordnen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="95934-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="95934-115">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Überwachungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="95934-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="95934-116">Klicken Sie mit der rechten Maustaste auf den Überwachungs Server, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="95934-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="95934-117">Klicken Sie unter **abhängige Speicher löschen**auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="95934-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="95934-118">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="95934-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

