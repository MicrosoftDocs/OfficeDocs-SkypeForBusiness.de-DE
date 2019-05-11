---
title: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Zusammenfassung: Erfahren Sie, wie der zentralisierte Protokollierungsdienst szenarioanbieter in Skype für Business Server 2015 zu konfigurieren.'
ms.openlocfilehash: 21c72e07365030f5bf016e4255acbf717d18a516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914968"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="52731-103">Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="52731-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52731-104">**Zusammenfassung:** Erfahren Sie, wie der zentralisierte Protokollierungsdienst szenarioanbieter in Skype für Business Server 2015 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="52731-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="52731-105">Die Konzepte und die Konfiguration der Anbieter in Centralized Logging Service ist der wichtigste zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="52731-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="52731-106">Theproviders direkt Skype für Business Server-Role Serverkomponenten in der Skype für Business Server Tracing Modell zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="52731-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="52731-107">Der Anbieter definiert die Komponenten einer Skype für Business Server 2015, die verfolgt werden, die Art der Nachrichten (z. B., schwerwiegende Fehler, oder Warnung) zu sammeln und die Kennzeichen (beispielsweise TF_Connection oder TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="52731-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="52731-108">Anbieter sind die nachverfolgbaren Komponenten in jedem Skype für Business Server-Rolle.</span><span class="sxs-lookup"><span data-stu-id="52731-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="52731-109">Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Chat oder Anwesenheit).</span><span class="sxs-lookup"><span data-stu-id="52731-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="52731-110">Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.</span><span class="sxs-lookup"><span data-stu-id="52731-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="52731-111">Um die Centralized Logging Service-Funktionen verwenden die Skype für Business Server-Verwaltungsshell ausgeführt werden soll, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, enthält eine der beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="52731-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="52731-112">Zum Zurückgeben einer Liste aller führen die rollenbasierten Zugriffssteuerung (RBAC) Rollen, die dieses Cmdlet zugewiesen wurden, (einschließlich alle benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), Sie folgenden Befehl aus der Skype für Business Server-Verwaltungsshell oder die Windows PowerShell auffordern:</span><span class="sxs-lookup"><span data-stu-id="52731-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="52731-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52731-113">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="52731-114">Der Rest dieses Themas befasst sich wie Anbieter definieren, ändern einen Anbieter und was eine Definition Anbieter zur Optimierung der Problembehandlung enthält.</span><span class="sxs-lookup"><span data-stu-id="52731-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="52731-115">Es gibt zwei Methoden zum Centralized Logging Service-Befehlen aus.</span><span class="sxs-lookup"><span data-stu-id="52731-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="52731-116">Sie können die CLSController.exe verwenden, die standardmäßig im Verzeichnis C:\Program Files\Common Files\Skype für 2015\CLSAgent Business Server gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="52731-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="52731-117">Oder Sie können die Skype für Business Server-Verwaltungsshell verwenden, um Windows PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="52731-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="52731-118">Mithilfe von Windows PowerShell, können Sie neue Anbieter für die Verwendung in Ihrer protokollierungssitzungen definieren, haben vollständige Kontrolle über ihre Erstellung was sie sammeln und auf welcher Ebene sie Sammeln von Daten.</span><span class="sxs-lookup"><span data-stu-id="52731-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="52731-p104">Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="52731-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="52731-122">Anstatt Sie in den Details der Anbieter tief einsteigen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits definiert sind.</span><span class="sxs-lookup"><span data-stu-id="52731-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="52731-123">Die bereitgestellten Szenarien beschäftigen sich mit den meisten mögliche Probleme, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52731-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="52731-124">In seltenen Fällen müssen Sie erstellen und Anbietern zu definieren, und weisen Sie diese Szenarien.</span><span class="sxs-lookup"><span data-stu-id="52731-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="52731-125">Es wird dringend empfohlen, dass Sie mit jedes der Szenarien bereitgestellt werden, bevor Sie die Notwendigkeit zum Erstellen von neuen Anbieter und Szenarien untersuchen vertraut.</span><span class="sxs-lookup"><span data-stu-id="52731-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="52731-126">Solange Informationen zum Erstellen von Anbietern hier gefunden wird, machen Sie mit wie die Szenarien die Elemente der Anbieter nutzen, um Ablaufverfolgungsinformationen zu erfassen, werden Details zu den Anbieter selbst zu diesem Zeitpunkt nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="52731-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="52731-127">Eingeführt in [Centralized Logging Service in Skype für Business 2015](centralized-logging-service.md), sind die wichtigsten Elemente beim Definieren eines Anbieters für die Verwendung in einem Szenario:</span><span class="sxs-lookup"><span data-stu-id="52731-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="52731-128">**Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, dass OCSLogger feststellen, welche die Verfolgung Engine Protokolle erfassen sollten.</span><span class="sxs-lookup"><span data-stu-id="52731-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="52731-129">Der Anbieter sind die gleichen Komponenten und in vielen Fällen haben, die denselben Namen wie die Komponenten in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="52731-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="52731-130">Wenn Sie nicht mit OCSLogger vertraut sind, Server-Role sind bestimmte Komponenten, die der zentralisierte Protokollierungsdienst sammeln können Protokolle aus.</span><span class="sxs-lookup"><span data-stu-id="52731-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="52731-131">Im Fall von the Centralized Logging Service ist die CLSAgent der Architektur Teil der zentralisierte Protokollierungsdienst, die wie folgt die Protokollierung der Komponenten, die Sie in der Konfiguration der Anbieter definieren.</span><span class="sxs-lookup"><span data-stu-id="52731-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="52731-132">**Protokollierungsstufen** OCSLogger bereitgestellt, die Möglichkeit, eine Anzahl von Detailebenen für die gesammelten Daten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="52731-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="52731-133">Dieses Feature ist ein integraler Bestandteil der zentralisierte Protokollierungsdienst und Szenarios und wird von der **Type** -Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="52731-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="52731-134">Sie können aus den folgenden wählen:</span><span class="sxs-lookup"><span data-stu-id="52731-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="52731-135">**Alle** : Es werden Ablaufverfolgungsmeldungen Nachrichten vom Typ "schwerwiegend", Fehler, Warnung, verbose und Debuginfo in das Protokoll für den festgelegten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="52731-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="52731-136">**"Schwerwiegend"** Sammelt nur Ablaufverfolgungsmeldungen definiert als "Schwerwiegend".</span><span class="sxs-lookup"><span data-stu-id="52731-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="52731-137">**Fehler** Sammelt nur Ablaufverfolgungsmeldungen definiert als "Fehler" oder "Schwerwiegend".</span><span class="sxs-lookup"><span data-stu-id="52731-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="52731-138">**Warnung** : Es werden nur die Ablaufverfolgungsmeldungen vom Typ "Warnung", "Fehler" und "Schwerwiegend".</span><span class="sxs-lookup"><span data-stu-id="52731-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="52731-139">**Info** : Es werden nur die Ablaufverfolgungsmeldungen, die eine informationsmeldung für den festgelegten Anbieter plus Schwerwiegender Fehler und Warnung Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="52731-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="52731-140">**"Ausführlich"** Alle Trace Nachrichten vom Typ "schwerwiegend", Fehler, Warnung und ausführlich für den festgelegten Anbieter erfasst.</span><span class="sxs-lookup"><span data-stu-id="52731-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="52731-141">**Debuggen** im Wesentlichen eine Entsprechung eines ist "All" - sammelt Spuren von Typ Fatal, Fehler, Warnung, Info, ausführlich und Debuggen für den festgelegten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="52731-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="52731-142">**Flags** OCSLogger bereitgestellt, die Option Flags für jeden Anbieter auswählen, die die Art der Informationen definiert, die Sie von der Ablaufverfolgungsdateien abrufen können.</span><span class="sxs-lookup"><span data-stu-id="52731-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="52731-143">Sie können die folgenden Kennzeichen, basierend auf den Anbieter ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="52731-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="52731-144">**TF_Connection** Verbindung-bezogene Protokolleinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="52731-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="52731-145">Diese Protokolle enthalten Informationen über Verbindungen zu und von einer bestimmten Komponente.</span><span class="sxs-lookup"><span data-stu-id="52731-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="52731-146">Dies kann auch beträchtliche auf Netzwerkebene Informationen enthalten (d. h., für Komponenten ohne das Konzept einer Verbindung).</span><span class="sxs-lookup"><span data-stu-id="52731-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="52731-147">**TF_Security** Enthält alle Ereignisse/Protokolleinträge im Zusammenhang mit der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="52731-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="52731-148">Beispielsweise sind für SipStack, diese Sicherheitsereignisse wie Domäne Validierungsfehler und Client-Authentifizierung/Autorisierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="52731-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="52731-149">**TF_Diag** Diagnose-Ereignisse, die Sie verwenden können, um diagnostizieren oder eine Problembehandlung für die Komponente enthält.</span><span class="sxs-lookup"><span data-stu-id="52731-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="52731-150">Für SipStack sind diese beispielsweise Zertifikat Fehler oder Warnungen/Fehler DNS.</span><span class="sxs-lookup"><span data-stu-id="52731-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="52731-151">**Tl_protocol** Enthält für protokollmeldungen wie SIP- und Community-Codec-Paket kombiniert Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="52731-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="52731-152">**TF_Component** Aktiviert die Protokollierung auf den Komponenten, die als Bestandteil der Anbieter angegeben.</span><span class="sxs-lookup"><span data-stu-id="52731-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="52731-153">**Alle** Aller verfügbare Kennzeichen festgelegt für den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="52731-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="52731-154">Um Informationen zu vorhandenen Centralized Logging Service-szenarioanbieter prüfen</span><span class="sxs-lookup"><span data-stu-id="52731-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="52731-155">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="52731-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="52731-156">Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:</span><span class="sxs-lookup"><span data-stu-id="52731-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="52731-157">Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52731-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="52731-158">Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf.</span><span class="sxs-lookup"><span data-stu-id="52731-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="52731-159">Die angezeigten Informationen sind nicht genügend oder die Liste ist zu lang für das Standardformat für Windows PowerShell Listen, können Sie zusätzliche Informationen anzeigen, indem definieren eine anderes Seitenausgabe-Methode.</span><span class="sxs-lookup"><span data-stu-id="52731-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="52731-160">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52731-160">To do this, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="52731-161">Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, der Protokollierungstyp, die Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="52731-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="52731-162">So definieren Sie einen neuen Centralized Logging Service-szenarioanbieter</span><span class="sxs-lookup"><span data-stu-id="52731-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="52731-163">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="52731-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="52731-p113">Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52731-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="52731-166">Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter „Lyss“ erfasst werden soll, sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="52731-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="52731-167">Die - Ebene sammelt schwerwiegenden Fehler, Fehler, Warnung und Informationen Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="52731-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="52731-168">Die verwendeten Flags werden alle für den Anbieter Lyss definiert und gehören TF_Connection, TF_Diag und TF_Protocol.After der $LyssProvider-Variablen definiert ist, können Sie sie mit dem Cmdlet **New-CsClsScenario** das Erfassen von ablaufverfolgungen vom Anbieter Lyss.</span><span class="sxs-lookup"><span data-stu-id="52731-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="52731-169">Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="52731-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="52731-170">Hierbei ist „$LyssProvider“ die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="52731-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="52731-171">So ändern Sie eine vorhandene Centralized Logging Service-szenarioanbieter</span><span class="sxs-lookup"><span data-stu-id="52731-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="52731-172">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="52731-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="52731-173">Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="52731-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="52731-174">Aktualisieren Sie das Szenario anschließend mit der folgenden Eingabe, um den Anbieter zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="52731-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="52731-p115">Dieser Befehl bewirkt, dass beim Szenariostandort „Redmond/RedmondLyssInfo“ die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von „Get-CsClsScenario“ anzeigen. Weitere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="52731-p115">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it. You can view the new scenario by using Get-CsClsScenario. For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="52731-178">**New-ClsCsProvider** überprüft nicht, ob die Flags gültig sind.</span><span class="sxs-lookup"><span data-stu-id="52731-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="52731-179">Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION).</span><span class="sxs-lookup"><span data-stu-id="52731-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="52731-180">Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="52731-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="52731-181">Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="52731-181">If you want to add additional providers to this scenario, type the following:</span></span>

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="52731-182">Hierbei wurde jeder mit der „Add“-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.</span><span class="sxs-lookup"><span data-stu-id="52731-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="52731-183">So entfernen Sie einen Szenarioanbieter</span><span class="sxs-lookup"><span data-stu-id="52731-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="52731-184">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="52731-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="52731-185">Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="52731-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="52731-186">Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter „-Provider“ die Anweisung „Replace“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="52731-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="52731-187">Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung „Update“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="52731-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="52731-188">Beispiel: Der Anbieter „LyssProvider“ ist mit dem Protokollierungstyp „WPP“, der Protokollierungsebene „Debug“ und den gesetzten Flags „TF_CONNECTION“ und „TF_DIAG“ definiert.</span><span class="sxs-lookup"><span data-stu-id="52731-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="52731-189">So ändern Sie die Flags, die benötigten "All".</span><span class="sxs-lookup"><span data-stu-id="52731-189">You need to change the flags to "All".</span></span> <span data-ttu-id="52731-190">Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:</span><span class="sxs-lookup"><span data-stu-id="52731-190">To change the provider, type the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="52731-191">Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="52731-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="52731-192">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52731-192">For example:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="52731-193">Das Cmdlet **Remove-CsClsScenario** fordert Sie nicht zur Eingabe einer Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="52731-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="52731-194">Das Szenario wird einschließlich der zugewiesenen Anbieter gelöscht.</span><span class="sxs-lookup"><span data-stu-id="52731-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="52731-195">Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="52731-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="52731-196">Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.</span><span class="sxs-lookup"><span data-stu-id="52731-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="52731-197">Wenn Sie ein Szenario mit dem Cmdlet**Remove-CsClsScenario** entfernen, wird es komplett aus dem Bereich entfernt.</span><span class="sxs-lookup"><span data-stu-id="52731-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="52731-198">Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.</span><span class="sxs-lookup"><span data-stu-id="52731-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="52731-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52731-199">See also</span></span>

[<span data-ttu-id="52731-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="52731-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="52731-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="52731-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="52731-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="52731-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="52731-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="52731-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="52731-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="52731-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
