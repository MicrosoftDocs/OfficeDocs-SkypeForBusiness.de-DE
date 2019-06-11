---
title: Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="85f30-102">Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)</span><span class="sxs-lookup"><span data-stu-id="85f30-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85f30-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="85f30-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="85f30-104">Führen Sie das folgende Verfahren aus, um den Vermittlungsserver, der sich auf dem Standard Edition-Server oder-Front-End-Pool befindet, zu einem eigenständigen Vermittlungsserver für eine Bereitstellung mit einem einzelnen Standort zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="85f30-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="85f30-105">So wechseln Sie einen kombinierten Vermittlungsserver zu einem eigenständigen Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="85f30-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="85f30-106">Öffnen Sie eine vorhandene Topologie aus dem Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="85f30-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="85f30-107">Navigieren Sie im linken Bereich zu **Mediations Pools**.</span><span class="sxs-lookup"><span data-stu-id="85f30-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="85f30-108">Klicken Sie mit der rechten Maustaste auf **Mediation Pools** , und wählen Sie **neuer Vermittlungs Server**aus.</span><span class="sxs-lookup"><span data-stu-id="85f30-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="85f30-109">Geben Sie auf der Seite **neuen Mediations Pool definieren** den FQDN des neuen Vermittlungs Server Pools an.</span><span class="sxs-lookup"><span data-stu-id="85f30-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="85f30-110">Wählen Sie außerdem aus, ob dieser Pool ein Einzelserver-oder ein Pool mit mehreren Servern sein soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="85f30-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="85f30-111">Wählen Sie den Front-End-Serverpool des nächsten Hop aus, an den der neue Vermittlungsserver eingehende Anrufe weiterleiten soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="85f30-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="85f30-112">Wählen Sie den von dem Vermittlungs Server zu verwendenden Edge-Pool aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="85f30-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="85f30-113">Ordnen Sie auf der Seite **PSTN-Gateways angeben** das vorherige PSTN-Gateway dem Vermittlungs Server zu.</span><span class="sxs-lookup"><span data-stu-id="85f30-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="85f30-114">Wählen Sie das Gateway aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="85f30-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="85f30-115">Klicken Sie auf **Fertig stellen** , um den Assistenten zum **Definieren eines neuen Mediations Pools** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="85f30-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="85f30-116">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="85f30-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="85f30-117">Wählen Sie im Bereich **Aktionen** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="85f30-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="85f30-118">Führen Sie die Schritte unter [Installieren des Servers für Mediations Dateien in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Vermittlungsserver zu installieren.</span><span class="sxs-lookup"><span data-stu-id="85f30-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="85f30-119">Nachdem die Dateien auf dem Vermittlungs Server installiert wurden, kehren Sie zu Topology Builder zurück, und navigieren Sie im linken Bereich zum Pool.</span><span class="sxs-lookup"><span data-stu-id="85f30-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="85f30-120">Klicken Sie mit der rechten Maustaste auf den Pool, und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="85f30-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="85f30-121">Deaktivieren Sie unter **Mediation Server**das Kontrollkästchen für **Mediation Server aktiviert** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="85f30-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="85f30-122">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="85f30-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="85f30-123">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="85f30-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

