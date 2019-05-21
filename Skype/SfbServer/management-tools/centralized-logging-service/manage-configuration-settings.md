---
title: Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 abrufen, aktualisieren und erstellen.'
ms.openlocfilehash: e6c1f9c893d0b5e745e558ed37570429689259d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274429"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="21b9f-103">Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="21b9f-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="21b9f-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 abrufen, aktualisieren und erstellen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="21b9f-105">Der zentralisierte Protokollierungsdienst wird von Einstellungen und Parametern gesteuert und konfiguriert, die vom zentralen Protokollierungsdienst Controller (CLSController) erstellt und verwendet werden, um Befehle an den zentralen Protokollierungsdienst-Agent des einzelnen Computers zu senden ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="21b9f-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="21b9f-106">Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Falle eines Start-Befehls) die Konfiguration der Szenarien, Anbieter, Ablaufverfolgungsdauer und Flags, um mit der Erfassung von Ablaufverfolgungsprotokollen gemäß den bereitgestellten Konfigurationsinformationen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="21b9f-107">Nicht alle Windows PowerShell-Cmdlets, die für den zentralisierten Protokollierungsdienst aufgelistet sind, sind für die Verwendung in lokalen Bereitstellungen von Skype for Business Server 2015 vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="21b9f-108">Obwohl Sie anscheinend funktionieren, sind die folgenden Cmdlets nicht für die Funktion mit Skype for Business Server 2015-lokalen Bereitstellungen vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="21b9f-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="21b9f-109">**CsClsRegion-Cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)und [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="21b9f-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="21b9f-110">**CsClsSearchTerm-Cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) und [CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="21b9f-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="21b9f-111">**CsClsSecurityGroup-Cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)und [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="21b9f-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="21b9f-112">Die in diesen Cmdlets definierten Einstellungen werden nicht behindert oder führen zu unerwünschten Verhaltensweisen, sind aber für die Verwendung mit Microsoft Office 365 konzipiert und liefern in lokalen Bereitstellungen keine erwarteten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="21b9f-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="21b9f-113">Das bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht von Nutzen sind, ihre Verwendung ist aber ein komplexes Thema, dessen Beschreibung den Rahmen dieser Dokumentation sprengen würde.</span><span class="sxs-lookup"><span data-stu-id="21b9f-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="21b9f-114">Der zentralisierte Protokollierungsdienst kann in einem Bereich ausgeführt werden, der einen einzelnen Computer oder einen Pool von Computern umfasst, und zwar bei einem Website Bereich (also einer definierten Website wie der Website Redmond, die eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder bei einem globalen Bereich (d. , alle Computer und Pools in Ihrer Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="21b9f-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="21b9f-115">Wenn Sie den Bereich für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell konfigurieren möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die enthält eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="21b9f-116">Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="21b9f-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="21b9f-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21b9f-117">For example:</span></span>

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="21b9f-118">Es gibt grundlegende Unterschiede zwischen den Befehlszeilenbefehlen, die in Windows PowerShell oder CLSController ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="21b9f-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="21b9f-119">Windows PowerShell bietet eine umfassende Methode zum Konfigurieren und Definieren von Szenarien sowie zum zweckmäßigen wieder verwenden dieser Szenarien für Ihre Problembehandlungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="21b9f-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="21b9f-120">Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt.</span><span class="sxs-lookup"><span data-stu-id="21b9f-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="21b9f-121">Im Gegensatz zu den Windows PowerShell-Cmdlets kann CLSController keine neuen Szenarien definieren, den Bereich auf einer Website oder auf globaler Ebene verwalten, und viele andere Einschränkungen eines begrenzten Befehlssatzes, die nicht dynamisch konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="21b9f-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="21b9f-122">Obwohl CLSController ein Mittel zur schnellen Ausführung bietet, bietet Windows PowerShell eine Möglichkeit, die Funktionalität des zentralen Protokollierungsdiensts über das hinaus zu erweitern, was mit CLSController möglich ist.</span><span class="sxs-lookup"><span data-stu-id="21b9f-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="21b9f-123">Ein einzelner Computerbereich kann während der Ausführung einer [Suchfunktion](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)definiert werden: CsClsLogging, [CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) und [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) Befehl mit dem Parameter "-Computer".</span><span class="sxs-lookup"><span data-stu-id="21b9f-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="21b9f-124">Der Parameter-Computers akzeptiert eine durch trennzeichengetrennte Liste der vollqualifizierten Domänennamen (FQDNs) für den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="21b9f-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="21b9f-125">Sie können auch-Pools und eine durch trennzeichengetrennte Liste der Pools definieren, auf denen Sie die Protokollierungs Befehle ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="21b9f-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="21b9f-126">Website-und globale Bereiche werden in den Cmdlets für **neu-**, **fest**gelegte und **entfernte** zentralisierte Protokollierungsdienste definiert.</span><span class="sxs-lookup"><span data-stu-id="21b9f-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="21b9f-127">Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="21b9f-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21b9f-128">Die angezeigten Befehle können Parameter und Konzepte enthalten, die in anderen Abschnitten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="21b9f-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="21b9f-129">Die Beispielbefehle dienen dazu, die Verwendung des **-Identity-** Parameters zum Definieren des Bereichs zu veranschaulichen, und die anderen Parameter werden zur Vollständigkeit und zum Angeben des Bereichs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="21b9f-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="21b9f-130">Ausführliche Informationen zu den Cmdlets für Cmdlets für **festgelegte CsClsConfiguration** finden Sie unter [CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="21b9f-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="21b9f-131">So rufen Sie die aktuelle Konfiguration für den zentralisierten Protokollierungsdienst ab</span><span class="sxs-lookup"><span data-stu-id="21b9f-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="21b9f-132">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-133">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-133">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration
   ```

<span data-ttu-id="21b9f-134">Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **CsClsConfiguration** , um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren. Wenn Sie **Get-CsClsConfiguration**ausführen, werden Informationen ähnlich der folgenden Bildschirmabbildung angezeigt, in der die Bereitstellung derzeit über die globale Standardkonfiguration verfügt, aber keine Websitekonfigurationen definiert sind:</span><span class="sxs-lookup"><span data-stu-id="21b9f-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Beispielausgabe von Get-CsClsConfiguration](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="21b9f-136">So rufen Sie die aktuelle Konfiguration für den zentralisierten Protokollierungsdienst vom lokalen Computerspeicher ab</span><span class="sxs-lookup"><span data-stu-id="21b9f-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="21b9f-137">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-138">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-138">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="21b9f-139">Wenn Sie das erste Beispiel verwenden, in dem **Get-CsClsConfiguration** keine Parameter angibt, verweist der Befehl auf den zentralen Verwaltungsspeicher für die Daten.</span><span class="sxs-lookup"><span data-stu-id="21b9f-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="21b9f-140">Wenn Sie den Parameter-localstore angeben, verweist der Befehl auf den Computer localstore anstelle des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="21b9f-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="21b9f-141">So rufen Sie eine Liste der aktuell definierten Szenarien ab</span><span class="sxs-lookup"><span data-stu-id="21b9f-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="21b9f-142">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-143">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-143">Type the following at the command-line prompt:</span></span>

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="21b9f-144">Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:</span><span class="sxs-lookup"><span data-stu-id="21b9f-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="21b9f-145">Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines bestimmten Bereichs sind.</span><span class="sxs-lookup"><span data-stu-id="21b9f-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="21b9f-146">In den meisten Fällen werden nicht alle Szenarien angezeigt und es wird gekürzt.</span><span class="sxs-lookup"><span data-stu-id="21b9f-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="21b9f-147">Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21b9f-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="21b9f-148">So aktualisieren Sie einen globalen Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21b9f-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="21b9f-149">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-150">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-150">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="21b9f-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21b9f-151">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="21b9f-p111">Der Befehl trägt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung auf, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.</span><span class="sxs-lookup"><span data-stu-id="21b9f-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="21b9f-154">So aktualisieren Sie einen Website Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21b9f-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="21b9f-155">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-156">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-156">Type the following at the command-line prompt:</span></span>

   ```
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="21b9f-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21b9f-157">For example:</span></span>

   ```
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="21b9f-p112">Wie im Beispiel gezeigt ist der Standardspeicherort der Protokolldateien „%TEMP%\Tracing“. Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu „%WINDIR%\ServiceProfiles\NetworkService\AppData\Local“ erweitert.</span><span class="sxs-lookup"><span data-stu-id="21b9f-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="21b9f-p113">Der Befehl trägt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond auf, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei – der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="21b9f-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="21b9f-162">So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="21b9f-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="21b9f-163">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-164">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-164">Type the following at the command-line prompt:</span></span>

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="21b9f-165">„New-CsClsConfiguration“ bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="21b9f-166">Details zu den Konfigurationsoptionen finden Sie unter [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) und [Grundlegendes zu den Konfigurationseinstellungen](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)für den zentralisierten Protokollierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="21b9f-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="21b9f-167">Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="21b9f-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="21b9f-168">Sie sollten die Erstellung neuer Konfigurationen sorgfältig planen und festlegen, wie Sie neue Eigenschaften für den zentralisierten Protokollierungsdienst definieren.</span><span class="sxs-lookup"><span data-stu-id="21b9f-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="21b9f-169">Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind.</span><span class="sxs-lookup"><span data-stu-id="21b9f-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="21b9f-170">Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.</span><span class="sxs-lookup"><span data-stu-id="21b9f-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="21b9f-171">So entfernen Sie eine vorhandene Konfiguration für den zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="21b9f-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="21b9f-172">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21b9f-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21b9f-173">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="21b9f-173">Type the following at the command-line prompt:</span></span>

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="21b9f-174">Um beispielsweise eine von Ihnen erstellte zentralisierte Protokollierungsdienst Konfiguration zu entfernen, um die rolloverzeit der Protokolldatei zu erhöhen, erhöhen Sie die Größe der Rollover-Protokolldatei, und legen Sie den Speicherort für den Protokolldatei Cache auf eine Netzwerkfreigabe wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="21b9f-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="21b9f-175">Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue zentralisierte Protokollierungsdienst Konfiguration" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="21b9f-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="21b9f-176">Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="21b9f-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="21b9f-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21b9f-177">See also</span></span>

[<span data-ttu-id="21b9f-178">Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="21b9f-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="21b9f-179">Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="21b9f-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="21b9f-180">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="21b9f-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="21b9f-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="21b9f-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="21b9f-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="21b9f-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="21b9f-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="21b9f-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="21b9f-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="21b9f-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
