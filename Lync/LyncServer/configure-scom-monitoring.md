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
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="d7392-102">Konfigurieren der SCOM-Überwachung</span><span class="sxs-lookup"><span data-stu-id="d7392-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7392-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d7392-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d7392-104">Nach der Migration zu Microsoft lync Server 2013 müssen Sie einige Aufgaben ausführen, um lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d7392-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="d7392-105">Wenden Sie lync Server 2010-Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="d7392-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="d7392-106">Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.</span><span class="sxs-lookup"><span data-stu-id="d7392-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="d7392-107">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für die zentrale Ermittlung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="d7392-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="d7392-108">Nachfolgend finden Sie Anweisungen zur Durchführung der einzelnen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="d7392-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="d7392-109">**Wenden Sie lync Server 2010-Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.**</span><span class="sxs-lookup"><span data-stu-id="d7392-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="d7392-110">Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und als Knoten für die Kandidaten Ermittlung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="d7392-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="d7392-111">Wenden Sie lync Server 2010-Updates auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="d7392-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="d7392-112">Lesen Sie das Thema [Anwenden von lync Server 2010-Updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="d7392-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="d7392-113">**Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.**</span><span class="sxs-lookup"><span data-stu-id="d7392-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="d7392-114">Öffnen Sie auf dem Server, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde, ein Windows PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="d7392-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="d7392-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d7392-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="d7392-116">Wenn Sie die Registrierung bearbeiten, tritt möglicherweise ein Fehler auf, dass der Befehl fehlgeschlagen ist, wenn der Registrierungsschlüssel bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d7392-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="d7392-117">Wenn Sie dies erleben, können Sie den Fehler bedenkenlos ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d7392-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="d7392-118">**Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für den Central Discovery Watcher-Knoten außer Kraft setzt.**</span><span class="sxs-lookup"><span data-stu-id="d7392-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="d7392-119">Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte** , und wählen Sie dann **Objektermittlungen**aus.</span><span class="sxs-lookup"><span data-stu-id="d7392-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="d7392-120">Klicken Sie auf **Bereich ändern...**</span><span class="sxs-lookup"><span data-stu-id="d7392-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="d7392-121">Wählen Sie auf der Seite **Objekte des Bereichs Management Packs** die Option **ls Discovery Candidate**aus.</span><span class="sxs-lookup"><span data-stu-id="d7392-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="d7392-122">Überschreiben Sie den Wert für den **effektiven ls-Ermittlungs Kandidaten** auf den Namen des Kandidaten Servers, der im vorherigen Verfahren gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="d7392-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="d7392-123">Um Ihre Änderungen abzuschließen, starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server erneut.</span><span class="sxs-lookup"><span data-stu-id="d7392-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

