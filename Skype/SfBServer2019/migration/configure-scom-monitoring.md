---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754045"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="82f47-103">Konfigurieren der SCOM-Überwachung</span><span class="sxs-lookup"><span data-stu-id="82f47-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="82f47-104">Nach der Migration zu Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="82f47-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="82f47-105">Wenden Sie Updates auf einen Server an, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="82f47-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="82f47-106">Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.</span><span class="sxs-lookup"><span data-stu-id="82f47-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="82f47-107">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Kandidaten-zentral Suche außer Kraft gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="82f47-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="82f47-108">Anweisungen für diese Aufgaben finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="82f47-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="82f47-109">Wenden Sie Updates auf einen Server an, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="82f47-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="82f47-110">Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="82f47-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="82f47-111">Wenden Sie Updates auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="82f47-111">Apply updates to this server.</span></span> <span data-ttu-id="82f47-112">Siehe das Thema [Apply Updates](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="82f47-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="82f47-113">Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.</span><span class="sxs-lookup"><span data-stu-id="82f47-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="82f47-114">Öffnen Sie auf dem Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde, ein Windows PowerShell Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="82f47-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="82f47-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="82f47-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="82f47-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="82f47-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="82f47-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="82f47-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="82f47-118">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Candidate Central Discovery Watcher außer Kraft gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="82f47-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="82f47-119">Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.</span><span class="sxs-lookup"><span data-stu-id="82f47-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="82f47-120">Klicken Sie auf **Bereich ändern** .</span><span class="sxs-lookup"><span data-stu-id="82f47-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="82f47-121">Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.</span><span class="sxs-lookup"><span data-stu-id="82f47-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="82f47-122">Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers.</span><span class="sxs-lookup"><span data-stu-id="82f47-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="82f47-123">Starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server neu, um die Änderungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="82f47-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

