---
title: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellen, ändern und entfernen.'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274436"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="1e12d-103">Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e12d-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1e12d-104">**Zusammenfassung:** Erfahren Sie, wie Sie Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellen, ändern und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="1e12d-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1e12d-105">Szenarien definieren den Bereich (Global, Site, Pool oder Computer) und welche Anbieter im zentralisierten Protokollierungsdienst zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="1e12d-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="1e12d-106">Mithilfe von Szenarien können Sie die Ablaufverfolgung für Dienstanbieter aktivieren oder deaktivieren (z. B. bezüglich S4, SIPStack, IM und Anwesenheit).</span><span class="sxs-lookup"><span data-stu-id="1e12d-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="1e12d-107">Durch das Konfigurieren eines Szenarios können Sie alle Dienstanbieter für eine bestimmte logische Sammlung gruppieren, die sich mit einem bestimmten Problemzustand befassen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="1e12d-108">Wenn Sie feststellen, dass ein Szenario geändert werden muss, um die Anforderungen zur Problembehandlung und Protokollierung zu erfüllen, bietet Ihnen Skype for Business Server 2015 Debug Tools ein Windows PowerShell-Modul mit dem Namen "ClsScenarioEdit. psm1", das eine Funktion namedEdit-CsClsScenario enthält.</span><span class="sxs-lookup"><span data-stu-id="1e12d-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="1e12d-109">Dieses Modul soll dazu dienen, die Eigenschaften des betreffenden Szenarios zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1e12d-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="1e12d-110">Beispiele für die Funktionsweise des Moduls erhalten Sie in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1e12d-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="1e12d-111">Laden Sie die [Debug-Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) von Skype for Business Server 2015 herunter, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1e12d-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e12d-112">Für einen bestimmten Bereich – Website, Global, Pool oder Computer – können Sie maximal zwei Szenarien zu einem bestimmten Zeitpunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="1e12d-113">Um zu ermitteln, welche Szenarien zurzeit ausgeführt werden, verwenden Sie Windows PowerShell und [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1e12d-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="1e12d-114">Mithilfe von Windows PowerShell und der [CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)können Sie dynamisch ändern, welche Szenarien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="1e12d-115">Sie können ändern, welche Szenarien während einer Protokollierungssitzung ausgeführt werden, um die Daten, die Sie sammeln, und von welchen Anbietern anzupassen oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="1e12d-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="1e12d-116">Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die enthält eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="1e12d-117">Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="1e12d-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="1e12d-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e12d-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="1e12d-119">Nachfolgend wird beschrieben, wie Sie ein Szenario definieren, ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können.</span><span class="sxs-lookup"><span data-stu-id="1e12d-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="1e12d-120">Sie können die Skype for Business Server-Verwaltungsshell zum Ausgeben von Windows PowerShell-Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="1e12d-121">Wenn Sie Windows PowerShell verwenden, können Sie neue Szenarien für die Verwendung in ihren Protokollierungssitzungen definieren.</span><span class="sxs-lookup"><span data-stu-id="1e12d-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="1e12d-122">Wie im [zentralisierten Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)eingeführt, sind die Elemente eines Szenarios:</span><span class="sxs-lookup"><span data-stu-id="1e12d-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="1e12d-123">**Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll.</span><span class="sxs-lookup"><span data-stu-id="1e12d-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="1e12d-124">Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="1e12d-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="1e12d-125">Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, von denen der zentralisierte Protokollierungsdienst Protokolle sammeln kann.</span><span class="sxs-lookup"><span data-stu-id="1e12d-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="1e12d-126">Details zur Konfiguration von Anbietern finden Sie unter [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="1e12d-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="1e12d-127">**Identität** Die Parameter-Identity legt den Bereich und den Namen des Szenarios fest.</span><span class="sxs-lookup"><span data-stu-id="1e12d-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="1e12d-128">So können Sie beispielsweise einen Bereich von "Global" festlegen und das Szenario mit "LyssServiceScenario" identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1e12d-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="1e12d-129">Wenn Sie die beiden kombinieren, definieren Sie die Identität (beispielsweise "Global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="1e12d-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="1e12d-130">Optional können Sie die Parameter-Name und-Parent verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="1e12d-131">Sie definieren den Parameter „Name“, um das Szenario eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1e12d-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="1e12d-132">Wenn Sie „Name“ verwenden, müssen Sie auch „Parent“ verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="1e12d-133">Wenn Sie den Parameter Name und Parent verwenden, können Sie den Parameter **-Identity** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="1e12d-134">So erstellen Sie ein neues Szenario mit dem Cmdlet „New-CsClsScenario“</span><span class="sxs-lookup"><span data-stu-id="1e12d-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="1e12d-135">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-p108">Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifikation). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="1e12d-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="1e12d-139">Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.</span><span class="sxs-lookup"><span data-stu-id="1e12d-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="1e12d-140">Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="1e12d-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e12d-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="1e12d-142">Das alternative Format using-Name und-Parent:</span><span class="sxs-lookup"><span data-stu-id="1e12d-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="1e12d-143">So erstellen Sie ein neues Szenario mit mehreren Anbietern mithilfe des Cmdlets „New-CsClsScenario“</span><span class="sxs-lookup"><span data-stu-id="1e12d-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="1e12d-144">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-145">Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="1e12d-146">Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1e12d-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="1e12d-147">In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="1e12d-148">Die Variablennamen der Anbieter lauten „LyssProvider“, „ABServerProvider“ und „SIPStackProvider“.</span><span class="sxs-lookup"><span data-stu-id="1e12d-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="1e12d-149">Wenn Sie einem Szenario mehrere Anbieter definieren und zuweisen möchten, geben Sie Folgendes in einer Skype for Business Server-Verwaltungsshell oder Windows PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="1e12d-150">Wie es in Windows PowerShell bekannt ist, ist die Konvention zum Erstellen einer Hashtabelle mit Werten `@{<variable>=<value1>, <value2>, <value>…}` , die assplatting verwendet, bekannt.</span><span class="sxs-lookup"><span data-stu-id="1e12d-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="1e12d-151">Ausführliche Informationen zu splatting in Windows PowerShell finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)unter.</span><span class="sxs-lookup"><span data-stu-id="1e12d-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="1e12d-152">So ändern Sie ein vorhandenes Szenario mithilfe des Cmdlets „Set-CsClsScenario“</span><span class="sxs-lookup"><span data-stu-id="1e12d-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="1e12d-153">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-154">Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich.</span><span class="sxs-lookup"><span data-stu-id="1e12d-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="1e12d-155">Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft.</span><span class="sxs-lookup"><span data-stu-id="1e12d-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="1e12d-156">Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt nicht mehr das entfernte Szenario, sondern stattdessen das neue Szenario.</span><span class="sxs-lookup"><span data-stu-id="1e12d-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="1e12d-157">Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen.</span><span class="sxs-lookup"><span data-stu-id="1e12d-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="1e12d-158">Wenn Sie ein neues Szenario definieren möchten, gehen Sie folgendermaßen vor (vorausgesetzt, es wird ein bereits definierter Anbieter mit dem Namen "S4Provider" hinzugefügt):</span><span class="sxs-lookup"><span data-stu-id="1e12d-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="1e12d-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e12d-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="1e12d-p112">Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine kommagetrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzen. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:</span><span class="sxs-lookup"><span data-stu-id="1e12d-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="1e12d-163">Beispiel, bei dem die aktuelle aus „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ bestehende Gruppe durch „$LyssServiceProvider“ ersetzt wird:</span><span class="sxs-lookup"><span data-stu-id="1e12d-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="1e12d-164">Geben Sie Folgendes ein, um lediglich den Anbieter „$LyssProvider“ aus der aktuellen Gruppe mit „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ durch den Anbieter „$LyssServiceProvider“ zu ersetzen:</span><span class="sxs-lookup"><span data-stu-id="1e12d-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="1e12d-165">So entfernen Sie ein vorhandenes Szenario mithilfe des Cmdlets „Remove-CsClsScenario“</span><span class="sxs-lookup"><span data-stu-id="1e12d-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="1e12d-166">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-167">Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="1e12d-168">Beispiel für das Entfernen des Szenarios „site:Redmond/LyssServiceScenario“:</span><span class="sxs-lookup"><span data-stu-id="1e12d-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="1e12d-169">Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario. Die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="1e12d-170">So laden und entladen Sie das Cmdlet „Edit-CsClsScenario“ mithilfe des Moduls „ClsScenarioEdit.psm1“</span><span class="sxs-lookup"><span data-stu-id="1e12d-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="1e12d-171">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1e12d-172">Das Modul „ClsScenarioEdit.psm1“ wird als separater Webdownload zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="1e12d-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="1e12d-173">Das Modul ist Teil der Debug-Tools für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1e12d-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="1e12d-174">Die Debugtools werden standardmäßig im Ordner „C:\Programme\Skype for Business Server 2015\Debugging Tools“ installiert.</span><span class="sxs-lookup"><span data-stu-id="1e12d-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="1e12d-175">Geben Sie in der Windows PowerShell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="1e12d-176">Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1e12d-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="1e12d-177">Um zu überprüfen, ob das Modul geladen wurde und dass Edit-CsClsScenario verfügbar `Get-Help Edit-CsClsScenario`ist, geben Sie.</span><span class="sxs-lookup"><span data-stu-id="1e12d-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="1e12d-178">Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="1e12d-179">Geben Sie zum Entladen des Moduls Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="1e12d-180">Durch erfolgreiches Entladen des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1e12d-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="1e12d-181">Um zu bestätigen, dass das Modul entladen wird, geben `Get-Help Edit-CsClsScenario`Sie.</span><span class="sxs-lookup"><span data-stu-id="1e12d-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="1e12d-182">Windows PowerShell versucht, die Hilfe für das Cmdlet zu finden, und es wird ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e12d-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="1e12d-183">So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario</span><span class="sxs-lookup"><span data-stu-id="1e12d-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="1e12d-184">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-185">Geben Sie in der Windows PowerShell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e12d-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="1e12d-186">Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1e12d-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="1e12d-187">Um zu überprüfen, ob das Modul geladen wurde und dass Edit-CsClsScenario verfügbar `Get-Help Edit-CsClsScenario`ist, geben Sie.</span><span class="sxs-lookup"><span data-stu-id="1e12d-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="1e12d-188">Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="1e12d-189">Geben Sie Folgendes ein, um einen Anbieter aus dem Szenario „AlwaysOn“ zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="1e12d-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="1e12d-190">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e12d-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="1e12d-p117">Bei den Parametern „ScenarioName“ und „ProviderName“ handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):</span><span class="sxs-lookup"><span data-stu-id="1e12d-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="1e12d-194">Die Positions Platzierung der Parameterwerte gilt nur für Scenario und-Provider.</span><span class="sxs-lookup"><span data-stu-id="1e12d-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="1e12d-195">Alle anderen Parameter müssen explizit definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1e12d-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="1e12d-196">So fügen Sie ein Szenario mit dem Modul „Edit-ClsController“ hinzu</span><span class="sxs-lookup"><span data-stu-id="1e12d-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="1e12d-197">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e12d-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e12d-198">Geben Sie Folgendes ein, um einen Anbieter zum Szenario „AlwaysOn“ hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="1e12d-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="1e12d-199">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e12d-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="1e12d-200">Mögliche Typen für „-Loglevel“ sind „Fatal“, „Error“, „Warning“, „Info“, „Verbose“, „Debug“ oder „All“.</span><span class="sxs-lookup"><span data-stu-id="1e12d-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="1e12d-201">-Flags können beliebige der vom Anbieter unterstützten Flags sein, beispielsweise TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="1e12d-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="1e12d-202">-Flags können auch vom Wert "alle" sein</span><span class="sxs-lookup"><span data-stu-id="1e12d-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="1e12d-p120">Das vorherige Beispiel kann auch mithilfe der Positionsfunktion des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um „ChatServer“ zum Szenario „AlwaysOn“ hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="1e12d-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
