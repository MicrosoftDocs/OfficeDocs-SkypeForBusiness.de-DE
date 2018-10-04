---
title: Konfigurieren von Anruf Daten Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Informationen zum Konfigurieren von Anrufen Daten Connector, der für lokale Skype für Business Online-Tools mit angezeigt werden, um Business Telemetrie von Skype werden können.
ms.openlocfilehash: 7c64ff1cfb7c300c575fb1b4512c590d1ddb867d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373299"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="c8c0f-103">Konfigurieren von Anruf Daten Connector</span><span class="sxs-lookup"><span data-stu-id="c8c0f-103">Configure Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

<span data-ttu-id="c8c0f-104">In diesem Artikel wird beschrieben, wie Call Data Connector – ein einzelnes Toolset konfigurieren, die dem Skype für Server aufrufen Qualität Geschäftsdaten verwenden Skype für Business Online aufrufen Quality Dashboard (CQD) und Aufrufen Analytics (CA) Tools angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8c0f-105">Unter public Preview-Version steht nur aufrufen Analytics Dashboard.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="c8c0f-106">Weitere Informationen zu aufrufen Data Connector Vorteile und die erforderlichen Komponenten, beispielsweise Rolle Anforderungen und Einrichten von hybridkonnektivität finden Sie unter [Planen der Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c8c0f-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="c8c0f-107">Aktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="c8c0f-107">Enable Monitoring</span></span> 

<span data-ttu-id="c8c0f-108">Sie müssen Call Data Recording (CDR) und Quality of Experience (QoE)-Datensammlung konfigurieren. Andernfalls wird nicht den Analytics aufrufen und die Qualität Dashboards aufrufen anzuzeigenden Informationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection; otherwise, the Call Analytics and Call Quality Dashboards won’t get information to display.</span></span> <span data-ttu-id="c8c0f-109">Bevor Sie Configure Anruf Data Connector, führen Sie die Schritte in [Deploy Überwachung in Skype für Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) zum Konfigurieren von KDS und QoE.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE.</span></span>


## <a name="enable-call-data-connector"></a><span data-ttu-id="c8c0f-110">Anruf Daten Connector aktivieren</span><span class="sxs-lookup"><span data-stu-id="c8c0f-110">Enable Call Data Connector</span></span>

<span data-ttu-id="c8c0f-111">Zum Konfigurieren und Aktivieren von Data Connector aufrufen, verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="c8c0f-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c8c0f-112">Cmdlet</span></span>| <span data-ttu-id="c8c0f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8c0f-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="c8c0f-114">Neue CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="c8c0f-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="c8c0f-115">Ein online-Cmdlet, das ein online Sammlungssatzes herstellt.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="c8c0f-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="c8c0f-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="c8c0f-117">Ein online-Cmdlet, die vorhandenen online Sammlungen abruft.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="c8c0f-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c8c0f-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="c8c0f-119">Eine lokale-Cmdlet, das die Verbindungsinformationen, die vom Cmdlet New-CsCloudCallDataConnection erstellt werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="c8c0f-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c8c0f-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="c8c0f-121">Eine lokale-Cmdlet, das die Verbindungsinformationen, die durch das Cmdlet "New-CsCloudCallDataConnection" erstellt eine lokale Kopie gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="c8c0f-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c8c0f-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="c8c0f-123">Eine lokale-Cmdlet, mit dem Sie aktivieren oder deaktivieren den Connector und Anwendungsebene anpassen.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="c8c0f-124">Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="c8c0f-124">Configure your environment</span></span> 

<span data-ttu-id="c8c0f-125">Zum Konfigurieren Ihrer Umgebung, um eine Sammlung online zu aktivieren, müssen Sie zuerst zu Skype für Business Online PowerShell als Administrator anmelden.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-125">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="c8c0f-126">Weitere Informationen finden Sie unter [Verwalten von Skype für Business Online mit Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8c0f-126">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="c8c0f-127">Es gibt zwei Methoden für die Anmeldung beim Skype für Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-127">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="c8c0f-128">Aus der Skype für Business Server 2019-Verwaltungsshell (empfohlene Methode)</span><span class="sxs-lookup"><span data-stu-id="c8c0f-128">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="c8c0f-129">Aus einer anderen PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="c8c0f-129">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="c8c0f-130">Melden Sie sich bei Skype für Business Online PowerShell aus der Skype für Business Server-Verwaltungsshell (empfohlene Methode)</span><span class="sxs-lookup"><span data-stu-id="c8c0f-130">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="c8c0f-131">Wenn die Verbindung zum ersten Mal zu aktivieren, führen Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-131">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="c8c0f-132">Wenn Sie eine Fehlermeldung, die die Verbindung bereits vorhanden ist erhalten, bedeutet dies, dass für Ihre Mandanten die Anruf-Datenverbindung bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-132">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="c8c0f-133">In diesem Fall führen Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-133">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="c8c0f-134">Melden Sie sich bei Skype für Business Online PowerShell aus einer anderen PowerShell-Sitzung (optional-Methode)</span><span class="sxs-lookup"><span data-stu-id="c8c0f-134">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="c8c0f-135">Wenn die Verbindung zum ersten Mal zu aktivieren, führen Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-135">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="c8c0f-136">Wenn Sie eine Fehlermeldung, die die Verbindung bereits vorhanden ist erhalten, bedeutet dies, dass für Ihre Mandanten die Anruf-Datenverbindung bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-136">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="c8c0f-137">In diesem Fall führen Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-137">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="c8c0f-138">Die Ausgabe des obigen Befehle enthält einen Tokenwert, die Sie benötigen, wenn Sie Ihre lokale Umgebung wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-138">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="c8c0f-139">Geben Sie von innerhalb der Skype für Business Server-Verwaltungsshell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-139">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="c8c0f-140">Konfigurieren Sie den Bereich</span><span class="sxs-lookup"><span data-stu-id="c8c0f-140">Configure the scope</span></span>

<span data-ttu-id="c8c0f-141">Sie können Daten Connector rufen Sie mithilfe des Set-CsCloudCallDataConnectorConfiguration-Cmdlets in der Skype für Business Server-Verwaltungsshell für einen bestimmten Standort oder für Ihre gesamte Skype für Business Server-Bereitstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-141">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="c8c0f-142">Beispielsweise kann der folgende Befehl rufen Sie Data Connector auf globaler Ebene:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-142">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="c8c0f-143">Zusätzlich zu den globalen Einstellungen für können Call Data Connector-Konfigurationseinstellungen, die auf Standortebene zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-143">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="c8c0f-144">Dies bietet zusätzliche Management-Flexibilität, wenn es für die Überwachung stammt.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-144">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="c8c0f-145">Beispielsweise kann der Administrator aktivieren Sie die Weiterleitung von Anrufen Data Connector für den Standort Redmond jedoch Call Data Connector-Weiterleitung für die Website Dublin deaktivieren, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-145">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="c8c0f-146">Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-146">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c8c0f-147">Nehmen wir beispielsweise bei Weiterleitung von Anrufen Data Connector auf globaler Ebene aktiviert ist, jedoch auf Standortebene (für den Standort Redmond) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-147">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="c8c0f-148">Das bedeutet, die Aufzeichnung von kommunikationsdatensätzen und QoE-Informationen aufrufen werden nicht für Benutzer in den Standort Redmond weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-148">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="c8c0f-149">Allerdings haben Benutzer an anderen Standorten (d. h., Benutzer, die durch die globalen Einstellungen anstelle der Redmond-websiteeinstellungen verwaltet) ihre KDS- und QoE-Informationen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-149">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="c8c0f-150">Werte für den am häufigsten verwendeten Einstellungen aufrufen Data Connector werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-150">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="c8c0f-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c8c0f-151">Property</span></span>|<span data-ttu-id="c8c0f-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8c0f-152">Description</span></span>|<span data-ttu-id="c8c0f-153">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c8c0f-153">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8c0f-154">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="c8c0f-154">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="c8c0f-155">Gibt an, ob Call Data Connector aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-155">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="c8c0f-156">Bei True werden Datensätze Überwachung auf die Überwachung der online weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-156">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="c8c0f-157">$False</span><span class="sxs-lookup"><span data-stu-id="c8c0f-157">$False</span></span>  <br/> |
| <span data-ttu-id="c8c0f-158">Identität </span><span class="sxs-lookup"><span data-stu-id="c8c0f-158">Identity</span></span> | <span data-ttu-id="c8c0f-159">Bestimmt die Bereichsebene für den Befehl: global oder Standort.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-159">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="c8c0f-160">globale</span><span class="sxs-lookup"><span data-stu-id="c8c0f-160">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="c8c0f-161">Anruf Daten Connector deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c8c0f-161">Disable Call Data Connector</span></span>

<span data-ttu-id="c8c0f-162">Deaktivieren Data Connector rufen Sie den Speicher für überwachen aus dem Front-End-Pool nicht aufheben, noch ist es deinstallieren oder anderweitig beeinträchtigt die Überwachung Back-End-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-162">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="c8c0f-163">Wenn Sie rufen Sie Data Connector deaktivieren, verhindern, dass Sie Skype für Business Server hochladen Anrufdaten in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-163">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="c8c0f-164">Deaktivieren Sie Call Data Connector mithilfe des Set-CsCloudCallDataConnectorConfiguration-Cmdlets in der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-164">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="c8c0f-165">Beispielsweise deaktiviert der folgende Befehl rufen Sie Data Connector auf globaler Ebene, indem es die EnableCallDataConnector-Eigenschaft auf $False festlegen:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-165">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="c8c0f-166">Wenn Sie Hochladen von Daten in die Cloud fortsetzen möchten, werden die EnableCallDataConnector-Eigenschaft wieder auf $True festgelegt, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-166">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="c8c0f-167">Anzeigen der lokale Daten über das online-dashboard</span><span class="sxs-lookup"><span data-stu-id="c8c0f-167">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="c8c0f-168">Nach dem Aufrufen der Data-Connector aktiviert ist, können Sie auf das Dashboard Analytics rufen Sie wie beschrieben in [Verwendung aufrufen Analytics schlechten Qualität Beheben von Problemen mit](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)Ihrer lokalen Anrufdaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-168">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="c8c0f-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8c0f-169">For more information</span></span>

<span data-ttu-id="c8c0f-170">Weitere Informationen in den Cmdlets können Sie den Befehl Get-Help aus der Skype für Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8c0f-170">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c8c0f-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8c0f-171">For example:</span></span>

<span data-ttu-id="c8c0f-172">Get-Help Get-CsCloudCallDataConnector | Weitere</span><span class="sxs-lookup"><span data-stu-id="c8c0f-172">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="c8c0f-173">Get-Help Set-CsCloudCallDataConnector | Weitere</span><span class="sxs-lookup"><span data-stu-id="c8c0f-173">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="c8c0f-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | Weitere</span><span class="sxs-lookup"><span data-stu-id="c8c0f-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>