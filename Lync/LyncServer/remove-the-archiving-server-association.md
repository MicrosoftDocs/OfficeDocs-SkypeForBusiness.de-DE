---
title: Entfernen der Zuordnung des Archivierungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="ea74d-102">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="ea74d-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea74d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ea74d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ea74d-104">Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ea74d-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="ea74d-105">Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ea74d-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="ea74d-106">Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ea74d-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="ea74d-107">So entfernen Sie die Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="ea74d-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="ea74d-108">Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="ea74d-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="ea74d-109">Navigieren Sie zum lync Server 2010-Knoten.</span><span class="sxs-lookup"><span data-stu-id="ea74d-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ea74d-110">Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellen**, basierend auf der Definition des Archivierungsservers.</span><span class="sxs-lookup"><span data-stu-id="ea74d-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="ea74d-111">Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="ea74d-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea74d-112"><STRONG>Survivable-Branch</STRONG> -Appliances auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="ea74d-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="ea74d-113">Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ea74d-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ea74d-114">Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemein**unter **Zuordnungen**das Kontrollkästchen **Archivierungs Server zuordnen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea74d-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ea74d-115">Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Archivierungsserver zugeordnet sind, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea74d-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="ea74d-116">Klicken Sie mit der rechten Maustaste auf den Archivierungs Server, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ea74d-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="ea74d-117">Klicken Sie unter **abhängige Speicher löschen**auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea74d-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="ea74d-118">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den lync Server-Bereitstellungs-Assistenten nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="ea74d-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

