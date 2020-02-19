---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73fccbc093365565fdc4062715b517e62eed3e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="f7ef0-102">Konfigurieren der SCOM-Überwachung</span><span class="sxs-lookup"><span data-stu-id="f7ef0-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7ef0-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f7ef0-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f7ef0-104">Nach der Migration zu Microsoft lync Server 2013 müssen Sie einige Aufgaben ausführen, um lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="f7ef0-105">Wenden Sie lync Server 2010 Updates auf einen Server an, der zur Verwaltung der zentralen Ermittlungslogik gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="f7ef0-106">Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="f7ef0-107">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Kandidaten-zentral Suche außer Kraft gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="f7ef0-108">Anweisungen für diese Aufgaben finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="f7ef0-109">**Wenden Sie lync Server 2010 Updates auf einen Server an, der zur Verwaltung der zentralen Ermittlungslogik gewählt wurde.**</span><span class="sxs-lookup"><span data-stu-id="f7ef0-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="f7ef0-110">Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="f7ef0-111">Wenden Sie lync Server 2010 Updates auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="f7ef0-112">Siehe das Thema [Apply lync Server 2010 Updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="f7ef0-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="f7ef0-113">**Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.**</span><span class="sxs-lookup"><span data-stu-id="f7ef0-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="f7ef0-114">Öffnen Sie auf dem Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde, ein Windows PowerShell Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="f7ef0-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f7ef0-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="f7ef0-p102">Bei jeder Bearbeitung der Registrierung kann eine Fehlermeldung angezeigt werden, dass der Befehl nicht ausgeführt wurde, wenn der Registrierungsschlüssel bereits vorhanden ist. Falls dies der Fall ist, können Sie die Fehlermeldung getrost ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="f7ef0-118">**Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Candidate Central Discovery Watcher außer Kraft gesetzt wird.**</span><span class="sxs-lookup"><span data-stu-id="f7ef0-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="f7ef0-119">Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="f7ef0-120">Klicken Sie auf **Bereich ändern**.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="f7ef0-121">Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="f7ef0-122">Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="f7ef0-123">Starten Sie zuletzt den Integritätsdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu, um Ihre Änderungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f7ef0-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

