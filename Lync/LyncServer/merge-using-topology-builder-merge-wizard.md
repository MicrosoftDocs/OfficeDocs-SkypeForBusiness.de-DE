---
title: Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="6a4dd-102">Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="6a4dd-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a4dd-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6a4dd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="6a4dd-104">Laden Sie die vorhandene Bereitstellung mithilfe des Topologie-Generators herunter.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="6a4dd-105">Klicken Sie im Menü **Aktion** auf **Office Communications Server 2007 R2 zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="6a4dd-106">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-106">Click **Next**.</span></span>

4.  <span data-ttu-id="6a4dd-107">Klicken Sie auf der Seite **Edgesetup angeben** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="6a4dd-108">![Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"")</span><span class="sxs-lookup"><span data-stu-id="6a4dd-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="6a4dd-p101">Geben Sie in **Edgesetup angeben** den Typ der Edgeserverkonfiguration ein, und klicken Sie auf **Weiter**. In diesem Beispiel wird die Option **Einzelner Edgeserver** verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a4dd-p102"><STRONG>Erweiterte Edgebereitstellung</STRONG> ist keine unterstützte Konfiguration. Ein <STRONG>Erweiterter Edgeserver</STRONG> muss zuerst in einen <STRONG>Einzelnen Edgeserver</STRONG> oder ein <STRONG>Konsolidiertes Edge mit Lastenausgleich</STRONG> umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="6a4dd-113">Geben Sie unter **interne Edge-Einstellungen angeben** die relevanten Informationen für den internen FQDN des Edgepool und die Ports bei Bedarf ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="6a4dd-114">![Dialogfeld "interne Edge-Einstellungen angeben"](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Dialogfeld "interne Edge-Einstellungen angeben"")</span><span class="sxs-lookup"><span data-stu-id="6a4dd-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="6a4dd-115">Geben Sie in **Externen Edge angeben** die FQDN-Informationen für Webkonferenzen für Ihren Edgeserver ein.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a4dd-p103">Führen Sie den nächsten Schritt dieses Verfahrens aus, bevor Sie auf <STRONG>Weiter</STRONG> klicken. Dieser Schritt darf auf keinen Fall ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="6a4dd-118">Aktivieren Sie das Kontrollkästchen **diese Edgepool wird für Verbund-und öffentliche Instant Messaging-Konnektivität verwendet** , wenn Sie die Legacy Office Communications Server 2007 R2 Edgeserver für den Verbund verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="6a4dd-119">Bei Bereitstellung mehrerer Edgeserver wird nur einer dieser Server für den Partnerverbund aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="6a4dd-120">Wenn Sie dieses Kontrollkästchen nicht aktivieren und den Partnerverbund zu einem späteren Zeitpunkt aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten des Topologie-Generators ausführen und Ihre Topologie erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="6a4dd-121">![Edgeserver Dialogfeld, Seite "externer Edge" angeben](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edgeserver Dialogfeld, Seite "externer Edge" angeben")</span><span class="sxs-lookup"><span data-stu-id="6a4dd-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="6a4dd-122">Geben Sie auf der Seite **Nächsten Hop angeben** den vollqualifizierten Domänennamen (FQDN) des nächsten Hop-Standorts in Ihrer Umgebung ein.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="6a4dd-123">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="6a4dd-124">![Edgeserver Dialogfeld: Seite "Nächster Hop angeben"](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edgeserver Dialogfeld: Seite "Nächster Hop angeben"")</span><span class="sxs-lookup"><span data-stu-id="6a4dd-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="6a4dd-125">Wenn Sie in " **Edge-Setup angeben**" alle Office Communications Server 2007 R2-Edgeserver hinzugefügt haben, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="6a4dd-126">Wenn Sie weitere Office Communications Server 2007 R2-Edgeserver hinzufügen möchten, wiederholen Sie dieses Verfahren ab Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="6a4dd-127">Wählen Sie unter **interner SIP-Port angeben** die Standardeinstellung aus (also, wenn Sie den standardmäßigen SIP-Port nicht geändert haben).</span><span class="sxs-lookup"><span data-stu-id="6a4dd-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="6a4dd-128">Ändern Sie den Port entsprechend, wenn Sie nicht den Standardport 5061 verwenden, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="6a4dd-129">Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter**, um mit dem Zusammenführen der Topologien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="6a4dd-130">Der Assistent überprüft, ob die Topologien erfolgreich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="6a4dd-131">Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="6a4dd-132">Im linken Bereich des Topologie-Generators sollte nun das **BackCompatSite**angezeigt werden, das angibt, dass Ihre Office Communications Server 2007 R2 Umgebung mit lync Server 2013 zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="6a4dd-133">![Topologie-Generator mit einer zusammengeführten Topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator mit einer zusammengeführten Topologie")</span><span class="sxs-lookup"><span data-stu-id="6a4dd-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="6a4dd-134">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="6a4dd-135">Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6a4dd-136">Es ist wichtig, dass Sie das nächste Thema <A href="import-policies-and-settings.md">Importieren von Richtlinien und Einstellungen</A>durchführen, um sicherzustellen, dass die Legacyrichtlinien Einstellungen in lync Server 2013 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a4dd-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

