---
title: Konfigurieren des Connectors für die Anrufdaten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Konfigurieren des Anruf datenconnectors, mit dem die Telemetrie aus Skype for Business lokal mit Skype for Business Online Tools angezeigt werden kann.
ms.openlocfilehash: 48af644523e9872107c814aa330d2af2d9a4272f
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328374"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="e1ee6-103">Konfigurieren des Connectors für die Anrufdaten</span><span class="sxs-lookup"><span data-stu-id="e1ee6-103">Configure Call Data Connector</span></span>

<span data-ttu-id="e1ee6-104">In diesem Artikel wird beschrieben, wie Sie den Anruf Datenkonnektor konfigurieren – ein einzelnes Toolset, mit dem Skype for Business Server Daten zur Anrufqualität mithilfe von Skype for Business Online CQD-und Call Analytics (ca)-Tools angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="e1ee6-105">Weitere Informationen zu den Vorteilen und Voraussetzungen des Anruf datenconnectors, wie beispielsweise die Rollenanforderungen und das Einrichten von Hybrid Konnektivität, finden Sie unter [Plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e1ee6-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="e1ee6-106">Überwachung aktivieren</span><span class="sxs-lookup"><span data-stu-id="e1ee6-106">Enable Monitoring</span></span>
 
<span data-ttu-id="e1ee6-107">Sie müssen die Datenerfassung für die Aufzeichnung von Datensätzen (KDS) und QoE-Daten (Quality of Experience) in der Front-End-Pool Überwachung mit lokalen LCSCdr-und QoEMetrics-Datenbanken konfigurieren. Andernfalls erhalten die Dashboards für anrufanalyse und Anrufqualität keine Daten, mit denen Sie arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="e1ee6-108">Führen Sie vor dem Konfigurieren von Call Data Connector die Schritte unter [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) aus, um sowohl KDS als auch QoE sowie die grundlegende Überwachung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1ee6-109">Der Anrufdaten-Konnektor funktioniert nicht, wenn die Überwachung im Front-End-Pool nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="e1ee6-110">Aktivieren von Anrufdaten-Konnektor</span><span class="sxs-lookup"><span data-stu-id="e1ee6-110">Enable Call Data Connector</span></span>

<span data-ttu-id="e1ee6-111">Zum Konfigurieren und Aktivieren von Call Data Connector verwenden Sie die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="e1ee6-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1ee6-112">Cmdlet</span></span>| <span data-ttu-id="e1ee6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ee6-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="e1ee6-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="e1ee6-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="e1ee6-115">Ein Online-Cmdlet, das einen Online-Datensammelpunkt einrichtet.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="e1ee6-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="e1ee6-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="e1ee6-117">Ein Online-Cmdlet, mit dem ein vorhandener Online Datensammler abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="e1ee6-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e1ee6-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="e1ee6-119">Ein lokales Cmdlet, das die vom New-CsCloudCallDataConnection-Cmdlet erstellten Verbindungsinformationen abruft.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="e1ee6-120">Gruppe-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e1ee6-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="e1ee6-121">Ein lokales Cmdlet, mit dem eine lokale Kopie der Verbindungsinformationen gespeichert wird, die mit dem Cmdlet New-CsCloudCallDataConnection erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="e1ee6-122">Gruppe-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e1ee6-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="e1ee6-123">Ein lokales Cmdlet, mit dem Sie den Connector aktivieren oder deaktivieren und die Bereichsebene anpassen können.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="e1ee6-124">Verwenden Sie das Cmdlet Remove-csclouddatconnectorconfiguration, um die Konfiguration zu löschen und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="e1ee6-125">Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="e1ee6-125">Configure your environment</span></span> 

<span data-ttu-id="e1ee6-126">Um Ihre Umgebung so zu konfigurieren, dass ein Online-Datensammelpunkt aktiviert wird, müssen Sie sich zunächst bei Skype for Business Online PowerShell als Administrator anmelden.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="e1ee6-127">Weitere Informationen finden Sie unter [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e1ee6-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="e1ee6-128">Es gibt zwei Methoden für die Anmeldung bei Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="e1ee6-129">Von der Skype for Business Server 2019-Verwaltungsshell (empfohlene Methode)</span><span class="sxs-lookup"><span data-stu-id="e1ee6-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="e1ee6-130">Aus einer anderen PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="e1ee6-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="e1ee6-131">Anmelden bei Skype for Business Online PowerShell über die Skype for Business Server-Verwaltungsshell (empfohlene Methode)</span><span class="sxs-lookup"><span data-stu-id="e1ee6-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="e1ee6-132">Wenn der Connector zum ersten Mal aktiviert wird, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="e1ee6-133">Wenn Sie eine Fehlermeldung erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdaten Verbindung bereits für Ihren Mandanten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="e1ee6-134">Führen Sie in diesem Fall den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="e1ee6-135">Anmelden bei Skype for Business Online PowerShell aus einer anderen PowerShell-Sitzung (optionale Methode)</span><span class="sxs-lookup"><span data-stu-id="e1ee6-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="e1ee6-136">Wenn der Connector zum ersten Mal aktiviert wird, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="e1ee6-137">Wenn Sie eine Fehlermeldung erhalten, dass die Verbindung bereits vorhanden ist, bedeutet dies, dass die Anrufdaten Verbindung bereits für Ihren Mandanten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="e1ee6-138">Führen Sie in diesem Fall den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="e1ee6-139">Die Ausgabe der obigen Befehle enthält einen Tokenwert, den Sie beim Konfigurieren Ihrer lokalen Umgebung wie folgt benötigen:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="e1ee6-140">Geben Sie in der Skype for Business Server Verwaltungsshell den folgenden Befehl an:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="e1ee6-141">Konfigurieren des Bereichs</span><span class="sxs-lookup"><span data-stu-id="e1ee6-141">Configure the scope</span></span>

<span data-ttu-id="e1ee6-142">Sie können den Anruf Datenkonnektor für einen bestimmten Standort oder für die gesamte Skype for Business Server-Bereitstellung mithilfe des Cmdlets "CsCloudCallDataConnectorConfiguration" in der Skype for Business Server-Verwaltungsshell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="e1ee6-143">Mit dem folgenden Befehl wird beispielsweise der Anrufdaten-Konnektor auf globaler Ebene aktiviert:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="e1ee6-144">Zusätzlich zu den globalen Einstellungen können Konfigurationseinstellungen für den Anruf Datenconnector dem Standortbereich zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="e1ee6-145">Dies bietet zusätzliche Flexibilität bei der Verwaltung im Hinblick auf die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="e1ee6-146">Beispielsweise kann ein Administrator die Weiterleitung des Anruf datenconnectors für den Standort "Redmond" aktivieren, aber die Weiterleitung des Anruf datenconnectors für den Standort Dublin deaktivieren, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="e1ee6-147">Auf Standortebene konfigurierte Einstellungen haben Vorrang vor den auf globaler Ebene konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="e1ee6-148">Nehmen wir beispielsweise an, dass die Weiterleitung des Anruf datenconnectors auf globaler Ebene aktiviert, aber auf Standortebene (für den Standort "Redmond") deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="e1ee6-149">Das bedeutet, dass die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen nicht für Benutzer am Standort "Redmond" weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="e1ee6-150">Benutzern an anderen Standorten (also Benutzern, die von den globalen Einstellungen anstelle der Einstellungen für den Standort "Redmond" verwaltet werden) werden jedoch die Aufzeichnung von Kommunikationsdatensätzen und QoE-Informationen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="e1ee6-151">Die Werte für die am häufigsten verwendeten Einstellungen, die von Call Data Connector verwendet werden, sind in der folgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="e1ee6-152">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e1ee6-152">Property</span></span>|<span data-ttu-id="e1ee6-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1ee6-153">Description</span></span>|<span data-ttu-id="e1ee6-154">Standardwert</span><span class="sxs-lookup"><span data-stu-id="e1ee6-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1ee6-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e1ee6-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="e1ee6-156">Gibt an, ob der Anrufdaten-Konnektor aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="e1ee6-157">Bei true werden Überwachungsdatensätze an die Online Überwachung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="e1ee6-158">$False</span><span class="sxs-lookup"><span data-stu-id="e1ee6-158">$False</span></span>  <br/> |
| <span data-ttu-id="e1ee6-159">Identität</span><span class="sxs-lookup"><span data-stu-id="e1ee6-159">Identity</span></span> | <span data-ttu-id="e1ee6-160">Legt die Bereichsebene für den Befehl fest: Global oder Site.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="e1ee6-161">globalen</span><span class="sxs-lookup"><span data-stu-id="e1ee6-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="e1ee6-162">Anrufdaten Verbindung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="e1ee6-162">Disable Call Data Connector</span></span>

<span data-ttu-id="e1ee6-163">Durch die Deaktivierung des Anruf datenconnectors wird der Überwachungsspeicher nicht vom Front-End-Pool aufgehoben, es wird auch keine Deinstallation oder anderweitige Auswirkung auf die Datenbank der Back-End-Datenbank</span><span class="sxs-lookup"><span data-stu-id="e1ee6-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="e1ee6-164">Wenn Sie den Anrufdaten-Konnektor deaktivieren, beenden Sie Skype for Business Server vom Hochladen von Anrufdaten in die Cloud.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="e1ee6-165">Sie können den Anrufdaten-Konnektor mithilfe des Cmdlets "CsCloudCallDataConnectorConfiguration" in der Skype for Business Server Verwaltungsshell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="e1ee6-166">Mit dem folgenden Befehl wird beispielsweise der Anrufdaten-Konnektor auf globaler Ebene deaktiviert, indem die EnableCallDataConnector-Eigenschaft auf $false festgesetzt wird:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="e1ee6-167">Wenn Sie das Hochladen von Anrufdaten in die Cloud fortsetzen möchten, legen Sie die EnableCallDataConnector-Eigenschaft wie im folgenden Beispiel gezeigt auf $true zurück:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="e1ee6-168">Anzeigen lokaler Daten über das Online Dashboard</span><span class="sxs-lookup"><span data-stu-id="e1ee6-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="e1ee6-169">Nachdem der Anrufdaten-Konnektor aktiviert wurde, können Sie Ihre lokalen Anrufdaten im anrufanalyse-Dashboard oder im Anruf qualitätsdashboard anzeigen, wie unter [Verwenden der anrufanalyse zur Behandlung schlechter Qualität](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) und [aktivieren und Verwenden des Anruf Qualitäts Dashboards für Microsoft Teams und Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="e1ee6-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e1ee6-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1ee6-170">For more information</span></span>

<span data-ttu-id="e1ee6-171">Weitere Informationen zu den Cmdlets finden Sie im Get-Help-Befehl in der Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e1ee6-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e1ee6-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e1ee6-172">For example:</span></span>

<span data-ttu-id="e1ee6-173">Get-Help Get-CsCloudCallDataConnector | Weitere</span><span class="sxs-lookup"><span data-stu-id="e1ee6-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="e1ee6-174">Get-Help-Gruppe-CsCloudCallDataConnector | Weitere</span><span class="sxs-lookup"><span data-stu-id="e1ee6-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="e1ee6-175">Get-Help-Gruppe-CsCloudCallDataConnectorConfiguration | Weitere</span><span class="sxs-lookup"><span data-stu-id="e1ee6-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
