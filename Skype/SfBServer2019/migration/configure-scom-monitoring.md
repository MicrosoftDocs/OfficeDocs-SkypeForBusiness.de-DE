---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype für Business Server 2019, müssen Sie einige Aufgaben zum Konfigurieren von Skype für Business Server 2019 arbeiten mit System Center Operations Manager ausführen.
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238723"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="c447c-103">Konfigurieren der SCOM-Überwachung</span><span class="sxs-lookup"><span data-stu-id="c447c-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="c447c-104">Nach der Migration zu Skype für Business Server 2019, müssen Sie einige Aufgaben zum Konfigurieren von Skype für Business Server 2019 arbeiten mit System Center Operations Manager ausführen.</span><span class="sxs-lookup"><span data-stu-id="c447c-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="c447c-105">Anwenden von Updates auf einem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c447c-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="c447c-106">Aktualisieren Sie die zentrale Erkennung Serverregistrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c447c-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="c447c-107">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so die Knoten des Kandidaten zentrale Erkennung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c447c-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="c447c-108">Anweisungen zum Ausführen aller dieser Aufgaben finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="c447c-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="c447c-109">Anwenden von Updates auf einem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c447c-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="c447c-110">Wählen Sie einen Server, der die System Center Operations Manager-Agentdateien installiert und wird als kandidatenermittlungsknoten konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c447c-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="c447c-111">Anwenden von Updates auf diesem Server.</span><span class="sxs-lookup"><span data-stu-id="c447c-111">Apply updates to this server.</span></span> <span data-ttu-id="c447c-112">Finden Sie im Thema [Anwenden von Updates](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="c447c-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="c447c-113">Aktualisieren Sie die zentrale Erkennung Serverregistrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c447c-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="c447c-114">Öffnen Sie auf dem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten ein Windows PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="c447c-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="c447c-115">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c447c-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="c447c-116">Wenn Sie die Registrierung bearbeiten, können Fehler auftreten, den der Befehl nicht ordnungsgemäß, wenn der Registrierungsschlüssel bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c447c-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="c447c-117">Wenn dies auftritt, können Sie den Fehler ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c447c-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="c447c-118">Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so Watcher-Knoten des Kandidaten zentrale Erkennung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c447c-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="c447c-119">Auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, erweitern Sie die **Management Pack-Objekte** , und wählen Sie **Objektermittlungen**aus.</span><span class="sxs-lookup"><span data-stu-id="c447c-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="c447c-120">Klicken Sie auf **Bereich ändern**</span><span class="sxs-lookup"><span data-stu-id="c447c-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="c447c-121">Wählen Sie auf der Seite **Bereich Management Pack-Objekte** **LS-Ermittlungskandidat**aus.</span><span class="sxs-lookup"><span data-stu-id="c447c-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="c447c-122">Überschreiben der **LS Discovery Candidate Effektivwert** auf den Namen des Servers Candidate zuvor im Verfahren festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c447c-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="c447c-123">Um Ihre Änderungen abzuschließen, starten Sie den Healthdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu.</span><span class="sxs-lookup"><span data-stu-id="c447c-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

