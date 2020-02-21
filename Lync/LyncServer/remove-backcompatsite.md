---
title: Entfernen von "BackCompatSite"
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d41d333e834dba34da2a1a04854571d721e94e38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="d5fc4-102">Entfernen von "BackCompatSite"</span><span class="sxs-lookup"><span data-stu-id="d5fc4-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5fc4-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d5fc4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d5fc4-104">Nach dem Deaktivieren aller Pools und dem Deinstallieren aller Edgeserver führen Sie den Zusammenführungs-Assistenten des Topologie-Generators aus, um **BackCompatSite** zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="d5fc4-105">So entfernen Sie "BackCompatSite" aus dem Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="d5fc4-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="d5fc4-106">Öffnen Sie im Topologie-Generator eine vorhandene Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="d5fc4-107">Klicken Sie im Menü **Aktion** auf **Topologie von Office Communications Server 2007 R2 zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="d5fc4-108">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="d5fc4-109">Stellen Sie auf der Seite **Legacy Edge angeben** sicher, dass die Liste der Edgeserver leer ist.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="d5fc4-110">Wenn die Liste nicht leer ist, verwenden Sie die **Entfernen** -Schaltfläche, um alle Legacy-Edgeserver zu entfernen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="d5fc4-111">![Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"")</span><span class="sxs-lookup"><span data-stu-id="d5fc4-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="d5fc4-112">Klicken Sie auf der Seite **Internen SIP-Port angeben** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="d5fc4-113">Klicken Sie auf der Seite **Zusammenfassung** auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen, um die Legacy Website zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="d5fc4-114">Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet, und klicken Sie zum Schließen des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="d5fc4-115">Erweitern Sie im linken Bereich des Topologie-Generators die Option "BackCompatSite", und stellen Sie sicher, dass keine Server aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="d5fc4-116">Klicken Sie mit der rechten Maustaste auf **BackCompatSite**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="d5fc4-117">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten **Lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="d5fc4-118">Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="d5fc4-119">Klicken Sie nach dem Abschließen des **Veröffentlichungs-Assistenten** auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d5fc4-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

