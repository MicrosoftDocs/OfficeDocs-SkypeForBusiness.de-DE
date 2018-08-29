---
title: Aktivieren von Quality of Experience in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Zusammenfassung: erfahren Sie, wie Quality of Experience (QoE) in Skype für Business Server zu aktivieren.'
ms.openlocfilehash: 38c0c14382e8f00abd49f6671af705400c0cff8c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261091"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="82257-103">Aktivieren von Quality of Experience in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="82257-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="82257-104">**Zusammenfassung:** erfahren Sie, wie Quality of Experience (QoE) in Skype für Business Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="82257-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="82257-105">Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben.</span><span class="sxs-lookup"><span data-stu-id="82257-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="82257-106">Weitere Informationen hierzu finden Sie unter [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="82257-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="82257-107">Verwenden Sie das folgende Verfahren, um QoE in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="82257-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="82257-108">Zur Aktivierung von QoE müssen Sie zunächst die Überwachung und eine Monitoring-Back-End-Datenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="82257-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="82257-109">Weitere Informationen hierzu finden Sie unter [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="82257-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="82257-110">So aktivieren Sie QoE mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="82257-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="82257-111">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="82257-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="82257-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="82257-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="82257-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="82257-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="82257-114">Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion** und anschließend auf **QoE aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="82257-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="82257-115">Aktivieren QoE mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="82257-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="82257-116">Sie können mithilfe von Windows PowerShell und das **Set-CsQoEConfiguration** -Cmdlet QoE aktivieren.</span><span class="sxs-lookup"><span data-stu-id="82257-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="82257-117">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="82257-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="82257-118">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="82257-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="82257-119">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="82257-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="82257-120">So aktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="82257-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="82257-121">Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf „True“ ($True) fest.</span><span class="sxs-lookup"><span data-stu-id="82257-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="82257-122">So deaktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="82257-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="82257-p104">Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf „False“ ($False) fest. Die Überwachung wird dadurch nicht deinstalliert. Das Erfassen und Speichern von QoE-Daten wird unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="82257-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="82257-126">So aktivieren Sie QoE mit einem einzelnen Befehl an mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="82257-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="82257-127">Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="82257-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="82257-128">Weitere Informationen hierzu finden Sie unter [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="82257-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="82257-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82257-129">See also</span></span>

[<span data-ttu-id="82257-130">Planen der Überwachung</span><span class="sxs-lookup"><span data-stu-id="82257-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="82257-131">Bereitstellen des Monitoring</span><span class="sxs-lookup"><span data-stu-id="82257-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

