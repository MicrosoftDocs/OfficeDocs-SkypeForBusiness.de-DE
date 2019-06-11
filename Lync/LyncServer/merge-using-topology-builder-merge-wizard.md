---
title: Zusammenführen mit dem Zusammenführungs-Assistenten für Topologie-Generator
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="a6a6c-102">Zusammenführen mit dem Zusammenführungs-Assistenten für Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="a6a6c-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6a6c-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a6a6c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="a6a6c-104">Laden Sie die vorhandene Bereitstellung mithilfe von Topology Builder herunter.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="a6a6c-105">Wählen Sie im Menü **Aktion** die Option **Office Communications Server 2007 R2 zusammenführen**aus.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="a6a6c-106">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-106">Click **Next**.</span></span>

4.  <span data-ttu-id="a6a6c-107">Klicken Sie unter **Edge-Setup angeben**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="a6a6c-108">![Assistenten für die Zusammenführungs Topologie, Seite "Edge-Setup" angeben] (images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistenten für die Zusammenführungs Topologie, Seite \"Edge-Setup\" angeben")</span><span class="sxs-lookup"><span data-stu-id="a6a6c-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="a6a6c-109">Geben Sie im Feld **Edge-Typ angeben**den Typ der Edgeserver-Konfiguration ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="a6a6c-110">In diesem Beispiel wird die **Single Edge Server** -Option verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6a6c-111"><STRONG>Erweiterte Edge-Bereitstellung</STRONG> ist keine unterstützte Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="a6a6c-112">Ein <STRONG>Erweiterter Edgeserver</STRONG> muss zuerst in einen <STRONG>einzelnen Edgeserver</STRONG> oder einen konsolidierten Edgeserver mit <STRONG>Lastenausgleich</STRONG> konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="a6a6c-113">Geben Sie unter Einstellungen für den **internen Rand angeben** die relevanten Informationen für den internen FQDN und die Ports Ihres Edge-Pools ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="a6a6c-114">![Dialogfeld ' Einstellungen für interne Kanten angeben '] (images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Dialogfeld ' Einstellungen für interne Kanten angeben '")</span><span class="sxs-lookup"><span data-stu-id="a6a6c-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="a6a6c-115">Geben Sie im Feld **externen Rand angeben**die FQDN-Informationen für Webkonferenzen für Ihren Edgeserver ein.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6a6c-116">Bevor Sie auf <STRONG>weiter</STRONG>klicken, führen Sie den nächsten Schritt in diesem Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="a6a6c-117">Es ist sehr wichtig, dass Sie diesen Schritt nicht verpassen.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="a6a6c-118">Aktivieren Sie das Kontrollkästchen **dieser Edge-Pool wird für Verbund-und öffentliche Chat Verbindungen verwendet** , wenn Sie beabsichtigen, den Legacy Office Communications Server 2007 R2-Edgeserver für den Verbund zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="a6a6c-119">Wenn Sie mehrere Edgeserver bereitgestellt haben, wird nur einer dieser Server für den Verbund aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="a6a6c-120">Wenn Sie dieses Kontrollkästchen nicht aktivieren und später entscheiden, dass Sie den Verbund aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten für Topologie-Generator ausführen und die Topologie erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="a6a6c-121">![Dialogfeld ' Edgeserver ', Seite ' externe Kante angeben '] (images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Dialogfeld ' Edgeserver ', Seite ' externe Kante angeben '")</span><span class="sxs-lookup"><span data-stu-id="a6a6c-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="a6a6c-122">Geben Sie in **Nächster Hop angeben**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des nächsten Hop-Standorts in Ihrer Umgebung ein.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="a6a6c-123">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="a6a6c-124">![Dialogfeld ' Edgeserver ', Seite ' nächster Hop angeben '] (images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Dialogfeld ' Edgeserver ', Seite ' nächster Hop angeben '")</span><span class="sxs-lookup"><span data-stu-id="a6a6c-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="a6a6c-125">Wenn alle Ihre Office Communications Server 2007 R2-Edgeserver hinzugefügt wurden, klicken Sie unter **Edge-Setup angeben**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="a6a6c-126">Wenn Sie weitere Office Communications Server 2007 R2-Edgeserver hinzufügen möchten, wiederholen Sie diesen Vorgang ab Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="a6a6c-127">Wählen Sie unter **interner SIP-Port angeben** die Standardeinstellung aus (das heißt, wenn Sie den standardmäßigen SIP-Port nicht geändert haben).</span><span class="sxs-lookup"><span data-stu-id="a6a6c-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="a6a6c-128">Ändern Sie die nach Bedarf, wenn Sie keinen Standardport von 5061 verwenden, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="a6a6c-129">Klicken Sie in **Zusammenfassung**auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="a6a6c-130">Die Seite des Assistenten überprüft, ob das Zusammenführen der Topologien erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="a6a6c-131">Überprüfen Sie in der Spalte **Status** , ob der Wert **erfolgreich**ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="a6a6c-132">Im linken Bereich des Topologie-Generators sollte nun der **BackCompatSite**angezeigt werden, der angibt, dass Ihre Office Communications Server 2007 R2-Umgebung mit lync Server 2013 zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="a6a6c-133">![Topologie-Generator mit einer zusammengeführten Topologie] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator mit einer zusammengeführten Topologie")</span><span class="sxs-lookup"><span data-stu-id="a6a6c-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="a6a6c-134">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="a6a6c-135">Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6a6c-136">Es ist wichtig, dass Sie das nächste Thema durchführen, <A href="import-policies-and-settings.md">Richtlinien und Einstellungen importieren</A>, um sicherzustellen, dass die Legacyrichtlinien Einstellungen in lync Server 2013 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6a6c-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

