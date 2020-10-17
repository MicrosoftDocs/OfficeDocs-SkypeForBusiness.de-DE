---
title: Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20397cf75b5f1f33004865b7c3ac364b45ed2c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514932"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="6773f-102">Übergang einer verbundenen Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)</span><span class="sxs-lookup"><span data-stu-id="6773f-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6773f-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6773f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6773f-104">Führen Sie das folgende Verfahren aus, um einen Vermittlungsserver, der mit einem Standard Edition-Server oder Front-End-Pool verbunden ist, auf einen eigenständigen Vermittlungsserver für eine Bereitstellung mit einem einzigen Standort umzustellen.</span><span class="sxs-lookup"><span data-stu-id="6773f-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="6773f-105">So stellen Sie einen verbundenen Vermittlungsserver auf einen eigenständigen Vermittlungsserver um</span><span class="sxs-lookup"><span data-stu-id="6773f-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="6773f-106">Öffen Sie über den Topologie-Generator eine vorhandene Topologie.</span><span class="sxs-lookup"><span data-stu-id="6773f-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="6773f-107">Navigieren Sie im linken Bereich zu **Vermittlungspools**.</span><span class="sxs-lookup"><span data-stu-id="6773f-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="6773f-108">Klicken Sie mit der rechten Maustaste auf **Vermittungspools**, und klicken Sie dann auf **Neuer Vermittlungsserver**.</span><span class="sxs-lookup"><span data-stu-id="6773f-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="6773f-p101">Geben Sie auf der Seite **Neuen Vermittlungspool definieren** den vollqualifizierten Domänennamen (FQDN) des neuen Vermittlungsserverpools ein. Geben Sie außerdem an, ob dieser Pool einen einzelnen oder mehrere Server enthalten soll, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6773f-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="6773f-111">Wählen Sie den nächsten Front-End-Server-Hoppool aus, an den der neue Vermittlungsserver eingehende Anrufe weiterleiten soll, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6773f-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="6773f-112">Wählen Sie den Edgepool aus, der von dem neuen Vermittlungsserver verwendet werden soll, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6773f-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="6773f-p102">Ordnen Sie auf der Seite **PSTN-Gateways angeben** das vorherige PSTN-Gateway dem Vermittlungsserver zu. Wählen Sie das Gateway aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6773f-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="6773f-115">Klicken Sie auf **Fertig stellen**, um den Assistenten zum Definieren eines neuen Vermittlungspools \*\*\*\* zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6773f-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="6773f-116">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="6773f-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="6773f-117">Klicken Sie im Bereich **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="6773f-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="6773f-118">Führen Sie die Schritte unter [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Vermittlungsserver zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6773f-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="6773f-119">Nachdem die Dateien auf dem Vermittlungsserver installiert worden sind, kehren Sie zum Topologie-Generator zurück, und navigieren Sie im linken Bereich zu dem Pool.</span><span class="sxs-lookup"><span data-stu-id="6773f-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="6773f-120">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6773f-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="6773f-121">Deaktivieren Sie unter **Vermittlungsserver** das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6773f-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="6773f-122">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="6773f-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="6773f-123">Wählen Sie im Menü **Aktion\*\*\*\*Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="6773f-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

