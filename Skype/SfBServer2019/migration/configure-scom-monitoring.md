---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
ms.openlocfilehash: 098265f5b17ab4d25164495965b3d20a122f61fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239344"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="eb103-103">Konfigurieren der SCOM-Überwachung</span><span class="sxs-lookup"><span data-stu-id="eb103-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="eb103-104">Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb103-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="eb103-105">Wenden Sie Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb103-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="eb103-106">Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.</span><span class="sxs-lookup"><span data-stu-id="eb103-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="eb103-107">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für die zentrale Ermittlung außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="eb103-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="eb103-108">Nachfolgend finden Sie Anweisungen zur Durchführung der einzelnen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="eb103-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="eb103-109">Wenden Sie Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb103-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="eb103-110">Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und als Knoten für die Kandidaten Ermittlung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="eb103-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="eb103-111">Wenden Sie Updates auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="eb103-111">Apply updates to this server.</span></span> <span data-ttu-id="eb103-112">Lesen Sie das Thema [Anwenden von Updates](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="eb103-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="eb103-113">Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.</span><span class="sxs-lookup"><span data-stu-id="eb103-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="eb103-114">Öffnen Sie auf dem Server, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde, ein Windows PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="eb103-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="eb103-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="eb103-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="eb103-116">Wenn Sie die Registrierung bearbeiten, tritt möglicherweise ein Fehler auf, dass der Befehl fehlgeschlagen ist, wenn der Registrierungsschlüssel bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="eb103-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="eb103-117">Wenn Sie dies erleben, können Sie den Fehler bedenkenlos ignorieren.</span><span class="sxs-lookup"><span data-stu-id="eb103-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="eb103-118">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für den Central Discovery Watcher-Knoten außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="eb103-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="eb103-119">Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte** , und wählen Sie dann **Objektermittlungen**aus.</span><span class="sxs-lookup"><span data-stu-id="eb103-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="eb103-120">Klicken Sie auf **Bereich ändern** .</span><span class="sxs-lookup"><span data-stu-id="eb103-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="eb103-121">Wählen Sie auf der Seite **Objekte des Bereichs Management Packs** die Option **ls Discovery Candidate**aus.</span><span class="sxs-lookup"><span data-stu-id="eb103-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="eb103-122">Überschreiben Sie den Wert für den **effektiven ls-Ermittlungs Kandidaten** auf den Namen des Kandidaten Servers, der im vorherigen Verfahren gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb103-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="eb103-123">Um Ihre Änderungen abzuschließen, starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server neu.</span><span class="sxs-lookup"><span data-stu-id="eb103-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

