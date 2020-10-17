---
title: 'Lync Server 2013: Ausführung der Schemavorbereitung'
description: 'Lync Server 2013: Schemavorbereitung wird durchführen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0991bbff7f54f8b8b9eb01fc87f752e00f3dcbfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569361"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="9c890-103">Durchführen Active Directory Schemavorbereitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c890-103">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c890-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9c890-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9c890-105">Sie können Setup oder lync Server-Verwaltungsshell-Cmdlets verwenden, um das Active Directory Schema vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="9c890-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="9c890-106">Das Cmdlet für die Erweiterung des Active Directory-Schemas ist **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="9c890-106">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c890-107">Das Schema Vorbereitungs-Cmdlet (<STRONG>install-CsAdServerSchema</STRONG>) muss auf den Schemamaster zugreifen, der erfordert, dass der Remoteregistrierungsdienst aktiv ist und dass der Remote Registrierungsschlüssel aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9c890-107">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="9c890-108">Wenn der Remoteregistrierungsdienst auf dem Schemamaster nicht aktiviert werden kann, können Sie das Cmdlet lokal auf dem Schemamaster ausführen.</span><span class="sxs-lookup"><span data-stu-id="9c890-108">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="9c890-109">Ausführliche Informationen zum Remotezugriff auf die Registrierung finden Sie im Microsoft Knowledge Base-Artikel 314837, "Verwalten des Remotezugriffs auf die Registrierung" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .</span><span class="sxs-lookup"><span data-stu-id="9c890-109">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="9c890-110">Stellen Sie nach Abschluss der Schemavorbereitung manuell sicher, dass die Schemapartition repliziert wurde, bevor Sie mit der Vorbereitung der Gesamtstruktur fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9c890-110">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="9c890-111">Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9c890-111">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="9c890-112">So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Setup vor</span><span class="sxs-lookup"><span data-stu-id="9c890-112">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="9c890-113">Melden Sie sich bei einem Server in der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten auf dem Schemamaster an.</span><span class="sxs-lookup"><span data-stu-id="9c890-113">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="9c890-114">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="9c890-114">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="9c890-115">Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9c890-115">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="9c890-116">Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9c890-116">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="9c890-117">Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="9c890-117">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="9c890-118">Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c890-118">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="9c890-119">Das Installationsprogramm installiert die lync Server Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="9c890-119">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="9c890-120">Wenn der Bereitstellungs-Assistent bereit ist, klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.</span><span class="sxs-lookup"><span data-stu-id="9c890-120">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="9c890-121">Klicken Sie unter **Schritt 1: Schema vorbereiten** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9c890-121">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="9c890-122">Klicken Sie auf der Seite **Schema vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9c890-122">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="9c890-123">Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9c890-123">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="9c890-124">Erweitern Sie in der Spalte **Aktion** die Option **Schema prep**, suchen Sie nach dem **\<Success\>** Ausführungsergebnis am Ende jeder Aufgabe, um zu überprüfen, ob die Schema Vorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9c890-124">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="9c890-125">Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.</span><span class="sxs-lookup"><span data-stu-id="9c890-125">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="9c890-126">Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="9c890-126">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="9c890-127">Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9c890-127">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="9c890-128">So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Cmdlets vor</span><span class="sxs-lookup"><span data-stu-id="9c890-128">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="9c890-129">Melden Sie sich bei einem Computer der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten für den Schemamaster an.</span><span class="sxs-lookup"><span data-stu-id="9c890-129">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="9c890-130">Installieren Sie lync Server Kernkomponenten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9c890-130">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="9c890-131">Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup.exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="9c890-131">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="9c890-132">Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9c890-132">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="9c890-133">Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9c890-133">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="9c890-134">Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="9c890-134">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="9c890-135">Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c890-135">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="9c890-136">Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.</span><span class="sxs-lookup"><span data-stu-id="9c890-136">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="9c890-137">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9c890-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9c890-138">Ausführen</span><span class="sxs-lookup"><span data-stu-id="9c890-138">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="9c890-139">Wenn Sie den LDF-Parameter nicht angeben, ist der Standardwert der lync Server 2013 Installationspfad, der aus der Registrierung gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="9c890-139">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="9c890-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9c890-140">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="9c890-141">Überprüfen Sie mit dem folgenden Cmdlet, ob die Schemavorbereitung erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9c890-141">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="9c890-142">Dieses Cmdlet gibt den Wert des **Schema \_ Versions \_ Status \_ Current** zurück, wenn die Schemavorbereitung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="9c890-142">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="9c890-143">Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.</span><span class="sxs-lookup"><span data-stu-id="9c890-143">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="9c890-144">Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="9c890-144">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="9c890-145">Ausführliche Informationen finden Sie unter [überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9c890-145">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c890-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c890-146">See Also</span></span>


[<span data-ttu-id="9c890-147">Überprüfen Active Directory Schemareplikation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c890-147">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="9c890-148">Vorbereiten des Active Directory Schemas in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c890-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

