---
title: 'Lync Server 2013: Ausführung der Domänenvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe361e46753b66a8efdc860ceae406ab3734fee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="d09d9-102">Ausführung der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09d9-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d09d9-103">_**Letztes Änderungsstand des Themas:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="d09d9-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="d09d9-104">Sie können Setup-oder lync Server-Verwaltungsshell-Cmdlets zum Vorbereiten von Domänen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d09d9-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="d09d9-105">Das Cmdlet, das eine Domäne vorbereitet, ist **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="d09d9-106">Die Domänenvorbereitung ist der letzte Schritt bei der Vorbereitung Active Directory-Domänendienste auf lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d09d9-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="d09d9-107">So verwenden Sie Setup zum Vorbereiten von Domänen</span><span class="sxs-lookup"><span data-stu-id="d09d9-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="d09d9-108">Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.</span><span class="sxs-lookup"><span data-stu-id="d09d9-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="d09d9-109">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="d09d9-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="d09d9-110">Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.</span><span class="sxs-lookup"><span data-stu-id="d09d9-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="d09d9-111">Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="d09d9-112">Klicken Sie auf der Seite **Domäne vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="d09d9-113">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="d09d9-114">Erweitern Sie in der Spalte **Aktion** den Knoten **Domänenvorbereitung**, suchen Sie nach einem \*\* \<\> \*\* Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="d09d9-115">Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In "Active Directory-Standorte und -Dienste" für den Domänencontroller des Gesamtstrukturstamms aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="d09d9-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="d09d9-116">So verwenden Sie Cmdlets zum Vorbereiten der Domäne</span><span class="sxs-lookup"><span data-stu-id="d09d9-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="d09d9-117">Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.</span><span class="sxs-lookup"><span data-stu-id="d09d9-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="d09d9-118">Installieren Sie lync Server Kernkomponenten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d09d9-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="d09d9-119">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="d09d9-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="d09d9-120">Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d09d9-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="d09d9-121">Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d09d9-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="d09d9-122">Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="d09d9-123">Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="d09d9-124">Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="d09d9-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="d09d9-125">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d09d9-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="d09d9-126">Ausführen</span><span class="sxs-lookup"><span data-stu-id="d09d9-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="d09d9-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d09d9-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="d09d9-128">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="d09d9-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="d09d9-p104">Überprüfen Sie, ob die Domänenvorbereitung erfolgreich war. Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d09d9-p104">Verify that domain preparation was successful. Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="d09d9-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d09d9-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d09d9-132">Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="d09d9-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="d09d9-133">Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="d09d9-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="d09d9-134">Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="d09d9-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="d09d9-135">Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänen&nbsp;Controller in AD DS.</span><span class="sxs-lookup"><span data-stu-id="d09d9-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="d09d9-136">Wenn Sie den Parameter **Domain** nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="d09d9-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="d09d9-137">Dieses Cmdlet gibt einen Wert von **LC\_DOMAINSETTINGS\_Status\_Ready** zurück, wenn die Domänenvorbereitung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d09d9-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d09d9-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d09d9-138">See Also</span></span>


[<span data-ttu-id="d09d9-139">Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09d9-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="d09d9-140">Vorbereiten von Domänen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09d9-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

