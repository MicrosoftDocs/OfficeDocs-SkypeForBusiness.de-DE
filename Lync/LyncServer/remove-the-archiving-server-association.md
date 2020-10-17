---
title: Entfernen der Zuordnung des Archivierungsservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3d9de311668bd43d913b0f746470235060bafe3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499972"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="87dde-102">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="87dde-102">Remove the Archiving server association</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87dde-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="87dde-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="87dde-104">Zum Entfernen eines Archivierungsserver müssen Sie die Abhängigkeit von der zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="87dde-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="87dde-105">Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="87dde-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="87dde-106">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="87dde-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="87dde-107">So entfernen Sie die Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="87dde-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="87dde-108">Öffnen Sie die lync Server 2013 Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="87dde-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="87dde-109">Navigieren Sie zum Knoten lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="87dde-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="87dde-110">Erweitern Sie im Topologie-Generator die **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**basierend auf der Definition des Archivierungsserver.</span><span class="sxs-lookup"><span data-stu-id="87dde-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="87dde-111">Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen der Zweigstelle, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="87dde-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87dde-112"><STRONG>Survivable Branch Appliances</STRONG> in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="87dde-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="87dde-113">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, das dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="87dde-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="87dde-114">Deaktivieren Sie in **Eigenschaften bearbeiten**, unter **Allgemein**, unter **Zuordnungen** das Kontrollkästchen **Archivierungsserver zuordnen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87dde-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="87dde-115">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem zu entfernenden Archivierungsserver zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="87dde-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="87dde-116">Klicken Sie mit der rechten Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="87dde-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="87dde-117">Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87dde-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="87dde-118">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="87dde-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

