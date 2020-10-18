---
title: 'Lync Server 2013: Vorbereiten der Gesamtstruktur'
description: 'Lync Server 2013: Ausführung der Gesamtstrukturvorbereitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577761"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="54cc4-103">Laufende Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54cc4-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54cc4-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="54cc4-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="54cc4-105">Sie können Setup oder lync Server-Verwaltungsshell-Cmdlets zum Vorbereiten der Gesamtstruktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="54cc4-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="54cc4-106">Das Cmdlet, das die Gesamtstruktur vorbereitet, ist **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="54cc4-107">Nach der Vorbereitung der Gesamtstruktur, müssen Sie vor der Domänenvorbereitung sicherstellen, dass die globalen Einstellungen repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="54cc4-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="54cc4-108">So verwenden Sie Setup zum Vorbereiten der Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="54cc4-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="54cc4-109">Melden Sie sich bei einem an eine Domäne angeschlossenen Computer als Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur-Stammdomäne an.</span><span class="sxs-lookup"><span data-stu-id="54cc4-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="54cc4-110">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="54cc4-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="54cc4-111">Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.</span><span class="sxs-lookup"><span data-stu-id="54cc4-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="54cc4-112">Klicken Sie in **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="54cc4-113">Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54cc4-114">Bei der Gesamtstrukturvorbereitung können Sie auswählen, wo die universellen Gruppen für lync Server 2013 platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="54cc4-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="54cc4-115">Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="54cc4-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="54cc4-116">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="54cc4-117">Erweitern Sie in der Spalte **Aktion** die Option **Gesamtstrukturvorbereitung**, suchen Sie nach einem **\<Success\>** Ausführungsergebnis am Ende jeder Aufgabe, um zu überprüfen, ob die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="54cc4-p103">Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Gesamtstruktur-Stammdomäne aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="54cc4-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="54cc4-120">So verwenden Sie Cmdlets zum Vorbereiten der Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="54cc4-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="54cc4-121">Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.</span><span class="sxs-lookup"><span data-stu-id="54cc4-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="54cc4-122">Installieren Sie lync Server Kernkomponenten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="54cc4-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="54cc4-123">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="54cc4-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="54cc4-124">Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="54cc4-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="54cc4-125">Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="54cc4-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="54cc4-126">Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="54cc4-127">Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="54cc4-128">Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="54cc4-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="54cc4-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="54cc4-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="54cc4-130">Ausführen</span><span class="sxs-lookup"><span data-stu-id="54cc4-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="54cc4-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="54cc4-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="54cc4-p106">Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet. Wenn zuvor universelle Gruppen in einer Domäne erstellt wurden, bei der es sich nicht um die Standarddomäne handelt, muss der Parameter "GroupDomain" explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="54cc4-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="54cc4-134">Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Stammdomäne der Gesamtstruktur aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen.</span><span class="sxs-lookup"><span data-stu-id="54cc4-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="54cc4-p107">Überprüfen Sie, ob die Vorbereitung der Gesamtstruktur erfolgreich war. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="54cc4-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="54cc4-137">Dieses Cmdlet gibt einen Wert von **LC \_ FORESTSETTINGS \_ Status \_ Ready** zurück, wenn die Gesamtstrukturvorbereitung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="54cc4-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54cc4-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54cc4-138">See Also</span></span>


[<span data-ttu-id="54cc4-139">Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54cc4-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="54cc4-140">Vorbereiten der Gesamtstruktur auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54cc4-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

