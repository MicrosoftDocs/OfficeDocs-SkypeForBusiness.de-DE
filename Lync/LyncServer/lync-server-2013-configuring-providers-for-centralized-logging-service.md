---
title: 'Lync Server 2013: Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="285a2-102">Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="285a2-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="285a2-103">_**Letztes Änderungsdatum des Themas:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="285a2-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="285a2-104">Die Konzepte und die Konfiguration von *Anbietern* im zentralisierten Protokollierungsdienst sind eine der wichtigsten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="285a2-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="285a2-105">Die *Anbieter* werden den lync Server-Rollen Komponenten direkt im lync Server-Ablaufverfolgungsmodell zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="285a2-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="285a2-106">Der Anbieter definiert die Komponenten eines lync Server 2013, die nachverfolgt werden, den Typ der Nachrichten (beispielsweise fatal, Fehler oder Warnung), die erfasst werden sollen, und die Flags (beispielsweise TF\_Connection oder TF\_Diag).</span><span class="sxs-lookup"><span data-stu-id="285a2-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="285a2-107">Anbieter sind die nachvollziehbaren Komponenten in jeder lync Server-Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="285a2-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="285a2-108">Mithilfe von Anbietern definieren Sie die Ablaufverfolgungsebene und den Typ von Verfolgung für Komponenten (z. B. S4, SIPStack, Chat oder Anwesenheit).</span><span class="sxs-lookup"><span data-stu-id="285a2-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="285a2-109">Der festgelegte Anbieter wird in einem Szenario verwendet, um sämtliche Anbieter für eine vorgegebene logische Auflistung zu gruppieren, die eine bestimmte Problembedingung betrifft.</span><span class="sxs-lookup"><span data-stu-id="285a2-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="285a2-110">Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control) oder einer benutzerdefinierten RBAC-Rolle sein, die eines der beiden Diese beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="285a2-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="285a2-111">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="285a2-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="285a2-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="285a2-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="285a2-113">Im weiteren Verlauf dieses Themas wird erläutert, wie Sie Anbieter definieren, einen Anbieter ändern und was eine Anbieter Definition enthält, um die Problembehandlung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="285a2-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="285a2-114">Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für zentralisierte Protokollierungsdienste.</span><span class="sxs-lookup"><span data-stu-id="285a2-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="285a2-115">Sie können\\die CLSController. exe verwenden, die sich standardmäßig im Verzeichnis C: Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013\\CLSAgent befindet.</span><span class="sxs-lookup"><span data-stu-id="285a2-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="285a2-116">Oder Sie können die lync Server-Verwaltungsshell zum Ausgeben von Windows PowerShell-Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="285a2-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="285a2-117">Der wichtige Unterschied besteht darin, dass bei der Verwendung von CLSController. exe in der Befehlszeile eine begrenzte Auswahl von Szenarien verfügbar ist, in denen die Anbieter bereits definiert sind und nicht änderbar sind, Sie aber die Protokollebene definieren können.</span><span class="sxs-lookup"><span data-stu-id="285a2-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="285a2-118">Mithilfe von Windows PowerShell können Sie neue Anbieter für die Verwendung in ihren Protokollierungssitzungen definieren, die vollständige Kontrolle über ihre Erstellung, deren Erfassung und auf welcher Ebene Sie Daten sammeln.</span><span class="sxs-lookup"><span data-stu-id="285a2-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="285a2-p104">Wie schon erwähnt sind Anbieter äußerst leistungsfähig. Szenarien sind jedoch noch leistungsfähiger, da sie die Darstellung sämtlicher Informationen enthalten, die zum Festlegen und Ausführen der Ablaufverfolgung für die Komponenten erforderlich sind, die die Anbieter darstellen. Diese Vorstellung von Szenarien als Auflistung von Anbietern lässt sich in etwa mit einer Batchdatei vergleichen, die Hunderte von Befehlen ausführt, um eine Vielzahl an Informationen zu sammeln, anstatt dass man jeden Befehl einzeln an der Befehlszeile ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="285a2-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="285a2-122">Anstatt zu verlangen, dass Sie sich eingehend mit den Details von Anbietern befassen, bietet der zentralisierte Protokollierungsdienst eine Reihe von Szenarien, die bereits für Sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="285a2-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="285a2-123">Die bereitgestellten Szenarien decken die meisten möglichen Probleme ab, die Ihnen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="285a2-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="285a2-124">In seltenen Fällen müssen Sie möglicherweise Anbieter erstellen und definieren und diese Szenarien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="285a2-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="285a2-125">Wir empfehlen Ihnen dringend, sich mit den einzelnen Szenarien vertraut zu machen, bevor Sie untersuchen, ob neue Anbieter und Szenarien erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="285a2-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="285a2-126">Während Informationen zum Erstellen von Anbietern hier gefunden werden, um Sie mit den Szenarien vertraut zu machen, in denen die Anbieter Elemente zum Sammeln von Ablaufverfolgungsinformationen verwendet werden, werden zu diesem Zeitpunkt keine Details zu den Anbietern selbst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="285a2-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="285a2-127">In der [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)werden die wichtigsten Elemente zum Definieren eines Anbieters für die Verwendung in einem Szenario vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="285a2-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="285a2-128">**Anbieter**   Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll.</span><span class="sxs-lookup"><span data-stu-id="285a2-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="285a2-129">Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="285a2-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="285a2-130">Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, über die der zentralisierte Protokollierungsdienst Protokolle sammeln kann.</span><span class="sxs-lookup"><span data-stu-id="285a2-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="285a2-131">Beim zentralisierten Protokollierungsdienst ist der CLSAgent der architektonische Teil des zentralen Protokollierungsdiensts, bei dem die Nachverfolgung der Komponenten erfolgt, die Sie in der Anbieterkonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="285a2-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="285a2-132">**Protokollierungsstufen**   OCSLogger die Option zum Auswählen einer Reihe von Detailebenen für die gesammelten Daten.</span><span class="sxs-lookup"><span data-stu-id="285a2-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="285a2-133">Dieses Feature ist ein integraler Bestandteil des zentralen Protokollierungsdiensts und der Szenarien und wird durch den **Type** -Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="285a2-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="285a2-134">Sie haben folgende Auswahlmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="285a2-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="285a2-135">**Alle**   sammelt Nachverfolgungsmeldungen vom Typ fatal, Fehler, Warnung und Informationen in das Protokoll des definierten Anbieters.</span><span class="sxs-lookup"><span data-stu-id="285a2-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="285a2-136">**Fatal**   sammelt nur die Ablaufverfolgungsmeldungen, die einen Fehler für den definierten Anbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="285a2-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="285a2-137">**Fehler**   sammelt nur die Ablaufverfolgungsmeldungen, die einen Fehler für den definierten Anbieter angeben, sowie schwerwiegende Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="285a2-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="285a2-138">**Warnung**   sammelt nur die Ablaufverfolgungsmeldungen, die eine Warnung für den definierten Anbieter sowie fatale und Fehlermeldungen angeben.</span><span class="sxs-lookup"><span data-stu-id="285a2-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="285a2-139">**Informationen**   sammelt nur die Ablaufverfolgungsmeldungen, die eine Informationsmeldung für den definierten Anbieter angeben, sowie fatale, Fehler-und Warnmeldungen.</span><span class="sxs-lookup"><span data-stu-id="285a2-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="285a2-140">**Verbose**   sammelt alle Ablaufverfolgungsmeldungen vom Typ fatal, Fehler, Warnung und Informationen für den definierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="285a2-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="285a2-141">**Flags**   OCSLogger hat die Option zum Auswählen von Flags für jeden Anbieter bereitgestellt, die definiert haben, welche Art von Informationen aus den Ablaufverfolgungsdateien abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="285a2-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="285a2-142">Auf der Grundlage des Anbieters können Sie die folgenden Flags auswählen:</span><span class="sxs-lookup"><span data-stu-id="285a2-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="285a2-143">**TF\_Connection**   bietet verbindungsbezogene Protokolleinträge.</span><span class="sxs-lookup"><span data-stu-id="285a2-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="285a2-144">Diese Protokolle umfassen Informationen zu Verbindungen, die zu und von einer bestimmten Komponente hergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="285a2-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="285a2-145">Dies kann auch wichtige Informationen auf Netzwerkebene enthalten (also für Komponenten ohne das Konzept einer Verbindung).</span><span class="sxs-lookup"><span data-stu-id="285a2-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="285a2-146">**TF\_Security**   stellt alle Ereignisse/Protokolleinträge in Bezug auf Sicherheit bereit.</span><span class="sxs-lookup"><span data-stu-id="285a2-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="285a2-147">Bei SipStack handelt es sich beispielsweise um Sicherheitsereignisse wie Fehler bei der Domänenüberprüfung und Clientauthentifizierung/Autorisierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="285a2-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="285a2-148">**TF\_Diag**   stellt Diagnoseereignisse bereit, die Sie zur Diagnose oder Problembehandlung der Komponente verwenden können.</span><span class="sxs-lookup"><span data-stu-id="285a2-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="285a2-149">Bei SipStack handelt es sich beispielsweise um Zertifikat Fehler oder DNS-Warnungen/-Fehler.</span><span class="sxs-lookup"><span data-stu-id="285a2-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="285a2-150">**Das\_TF-Protokoll**   bietet Protokollnachrichten wie SIP-und kombinierte Community-Codec-Paket Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="285a2-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="285a2-151">**Die\_TF-Komponente**   ermöglicht die Protokollierung an den als Teil der Anbieter angegebenen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="285a2-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="285a2-152">**Alle**   legt alle verfügbaren Flags fest, die für den Anbieter verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="285a2-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="285a2-153">So überprüfen Sie Informationen zu vorhandenen Szenario-Anbietern für zentralisierte Protokollierungsdienste</span><span class="sxs-lookup"><span data-stu-id="285a2-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="285a2-154">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="285a2-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="285a2-155">Mit dem folgenden Befehl können Sie die Konfiguration vorhandener Anbieter überprüfen:</span><span class="sxs-lookup"><span data-stu-id="285a2-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="285a2-156">Wenn Sie beispielsweise Informationen über die globale Konferenzzentrale überprüfen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="285a2-157">Der Befehl listet Anbieter mit den zugehörigen Flags, Einstellungen und Komponenten auf.</span><span class="sxs-lookup"><span data-stu-id="285a2-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="285a2-158">Wenn die angezeigten Informationen nicht ausreichen oder die Liste für das standardmäßige Windows PowerShell-Listenformat zu lang ist, können Sie zusätzliche Informationen anzeigen, indem Sie eine andere Ausgabemethode definieren.</span><span class="sxs-lookup"><span data-stu-id="285a2-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="285a2-159">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="285a2-160">Dieser Befehl gibt die einzelnen Anbieter in einem fünfzeiligen Format aus, bei dem der Anbietername, der Protokollierungstyp, die Protokollierungsebene, Flags, GUID und Rolle jeweils in einer eigenen Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="285a2-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="285a2-161">So definieren Sie einen neuen szenariodienst für zentrale Protokollierungsdienste</span><span class="sxs-lookup"><span data-stu-id="285a2-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="285a2-162">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="285a2-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="285a2-p113">Ein Szenarioanbieter besteht aus einer nachzuverfolgenden Komponente, zu verwendenden Flags und einer Detailstufe für die Erfassung. Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="285a2-165">Beispiel: Die Definition eines Ablaufverfolgungsanbieters, in der festgelegt ist, was und mit welcher Detailstufe vom Anbieter „Lyss“ erfasst werden soll, sieht so aus:</span><span class="sxs-lookup"><span data-stu-id="285a2-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="285a2-166">Die Stufe – sammelt fatale, Fehler-, Warnungs-und Informationsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="285a2-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="285a2-167">Bei den verwendeten Flags handelt es sich um alle für den Lyss-Anbieter definierten Flags\_, die TF\_Connection, TF\_diag und TF-Protokoll umfassen.</span><span class="sxs-lookup"><span data-stu-id="285a2-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="285a2-168">Nachdem die Variable „$LyssProvider“ definiert ist, können Sie sie mit dem Cmdlet **New-CsClsScenario** verwenden, um Ablaufverfolgungen vom Anbieter „Lyss“ zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="285a2-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="285a2-169">Geben Sie für die Erstellung und Zuweisung des Anbieters zu einem neuen Szenario den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="285a2-170">Hierbei ist „$LyssProvider“ die Variable, in der sich das definierte Szenario befindet, das mit **New-CsClsProvider** erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="285a2-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="285a2-171">So ändern Sie einen vorhandenen szenariodienst für zentralisierte Protokollierungsdienste</span><span class="sxs-lookup"><span data-stu-id="285a2-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="285a2-172">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="285a2-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="285a2-173">Geben Sie Folgendes ein, um die Konfiguration eines vorhandenen Anbieters zu aktualisieren oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="285a2-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="285a2-174">Aktualisieren Sie das Szenario anschließend mit der folgenden Eingabe, um den Anbieter zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="285a2-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="285a2-p116">Dieser Befehl bewirkt, dass beim Szenariostandort „Redmond/RedmondLyssInfo“ die Flags und die Ebene für den zugewiesenen Anbieter aktualisiert werden. Das neue Szenario können Sie mithilfe von „Get-CsClsScenario“ anzeigen. Weitere Informationen dazu finden Sie unter [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="285a2-p116">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it. You can view the new scenario by using Get-CsClsScenario. For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="285a2-178"><STRONG>New-ClsCsProvider</STRONG> überprüft nicht, ob die Flags gültig sind.</span><span class="sxs-lookup"><span data-stu-id="285a2-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="285a2-179">Sie müssen sicherstellen, dass die Namen der Flags keine Schreibfehler enthalten (z. B. TF_DIAG oder TF_CONNECTION).</span><span class="sxs-lookup"><span data-stu-id="285a2-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="285a2-180">Wenn die Flags falsch geschrieben sind, kann der Anbieter nicht die gewünschten Protokollinformationen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="285a2-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="285a2-181">Wenn Sie diesem Szenario weitere Anbieter hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="285a2-182">Hierbei wurde jeder mit der „Add“-Anweisung festgelegte Anbieter bereits mithilfe des **New-CsClsProvider**-Prozesses definiert.</span><span class="sxs-lookup"><span data-stu-id="285a2-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="285a2-183">So entfernen Sie einen Szenarioanbieter</span><span class="sxs-lookup"><span data-stu-id="285a2-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="285a2-184">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="285a2-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="285a2-185">Mithilfe der bereitgestellten Cmdlets können Sie vorhandene Anbieter aktualisieren und neue Anbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="285a2-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="285a2-186">Wenn Sie einen Anbieter entfernen möchten, müssen Sie bei **Set-CsClsScenario** beim Parameter „-Provider“ die Anweisung „Replace“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="285a2-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="285a2-187">Die einzige Möglichkeit, einen Anbieter komplett zu entfernen, besteht darin, ihn durch einen neu definierten Anbieter mit dem gleichen Namen zu ersetzen und die Anweisung „Update“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="285a2-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="285a2-188">So wird beispielsweise unser Anbieter LyssProvider mit WPP als Protokolltyp definiert, auf Debugebene festgelegt, und Flags sind TF\_Connection und TF\_diag.</span><span class="sxs-lookup"><span data-stu-id="285a2-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="285a2-189">Sie möchten die Flags auf „Alle“ ändern.</span><span class="sxs-lookup"><span data-stu-id="285a2-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="285a2-190">Geben Sie dazu den folgenden Befehl ein, um den Anbieter zu ändern:</span><span class="sxs-lookup"><span data-stu-id="285a2-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="285a2-191">Wenn Sie ein Szenario mit den zugehörigen Anbietern vollständig entfernen möchten, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="285a2-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="285a2-192">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="285a2-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="285a2-193">Das Cmdlet <STRONG>Remove-CsClsScenario</STRONG> fordert Sie nicht zur Eingabe einer Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="285a2-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="285a2-194">Das Szenario wird einschließlich der zugewiesenen Anbieter gelöscht.</span><span class="sxs-lookup"><span data-stu-id="285a2-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="285a2-195">Sie können das Szenario wieder neu erstellen, indem Sie die Befehle ausführen, mit denen das Szenario ursprünglich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="285a2-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="285a2-196">Ein Verfahren zum Wiederherstellen entfernter Szenarien oder Anbieter gibt es nicht.</span><span class="sxs-lookup"><span data-stu-id="285a2-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="285a2-197">Wenn Sie ein Szenario mit dem Cmdlet**Remove-CsClsScenario** entfernen, wird es komplett aus dem Bereich entfernt.</span><span class="sxs-lookup"><span data-stu-id="285a2-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="285a2-198">Wenn Sie die von Ihnen erstellten Szenarien mit den zugehörigen Anbietern verwenden möchten, müssen Sie neue Anbieter erstellen und diese einem neuen Szenario zuweisen.</span><span class="sxs-lookup"><span data-stu-id="285a2-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="285a2-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="285a2-199">See Also</span></span>


[<span data-ttu-id="285a2-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="285a2-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="285a2-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="285a2-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="285a2-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="285a2-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="285a2-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="285a2-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="285a2-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="285a2-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

