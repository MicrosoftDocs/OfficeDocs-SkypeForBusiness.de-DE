---
title: Aktivieren Sie die Aufzeichnung von kommunikationsdatensätzen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Zusammenfassung: Erfahren Sie, wie die Aufzeichnung von kommunikationsdatensätzen (CDR) Datensätze in Skype für Business Server aktivieren.'
ms.openlocfilehash: 8ba053c95dcb9e43b6951671853d2c064ad5542f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199714"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="2d8c2-103">Aktivieren Sie die Aufzeichnung von kommunikationsdatensätzen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="2d8c2-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="2d8c2-104">**Zusammenfassung:** Erfahren Sie, wie die Aufzeichnung von kommunikationsdatensätzen (CDR) Datensätze in Skype für Business Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="2d8c2-p101">Bei der Aufzeichnung von Kommunikationsdatensätzen werden Nutzungs- und Diagnoseinformationen über Peer-to-Peer-Aktivitäten aufgezeichnet, z. B. Chat, VoIP-Anrufe (Voice over Internet Protocol), Anwendungsfreigabe, Dateiübertragung und Besprechungen. Anhand der Nutzungsdaten kann die Rendite berechnet werden und die Diagnosedaten können zur Problembehandlung bei Peer-to-Peer-Aktivitäten und Besprechungen eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="2d8c2-107">Verwenden Sie das folgende Verfahren, um die Aufzeichnung von Kommunikationsdatensätzen (KDS) in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="2d8c2-p102">Zur Aktivierung von KDS müssen Sie die Überwachung und eine Überwachungsdatenbank konfigurieren. Ausführliche Informationen finden Sie unter [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d8c2-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="2d8c2-110">So aktivieren Sie KDS mit Skype für Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="2d8c2-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2d8c2-111">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="2d8c2-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="2d8c2-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="2d8c2-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="2d8c2-114">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Aktion** und anschließend auf **KDS aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d8c2-115">KDS ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d8c2-116">Aktivieren KDS mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="2d8c2-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2d8c2-117">Sie können KDS aktivieren, mithilfe von Windows PowerShell und das **Set-CsCdrConfiguration** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="2d8c2-118">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2d8c2-119">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="2d8c2-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2d8c2-120">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="2d8c2-121">So aktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="2d8c2-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="2d8c2-122">Sie können KDS aktivieren, indem Sie den Parameter „EnableCDR“ auf „True“ ($True) setzen.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="2d8c2-123">So deaktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="2d8c2-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="2d8c2-p104">Sie können KDS deaktivieren, indem Sie den Parameter „EnableCDR“ auf „False“ ($False) setzen. Durch die Deaktivierung von KDS wird die Überwachung nicht deinstalliert, sondern die Sammlung und Speicherung von KDS-Daten angehalten.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="2d8c2-127">So verwenden Sie einen einzelnen Befehl zum Aktivieren von KDS an mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="2d8c2-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="2d8c2-128">Mit diesem Befehl wird KDS für alle derzeit in der Organisation verwendeten KDS-Einstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="2d8c2-129">Weitere Informationen finden Sie im Hilfethema zum [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d8c2-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d8c2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d8c2-130">See also</span></span>

[<span data-ttu-id="2d8c2-131">Planen der Überwachung</span><span class="sxs-lookup"><span data-stu-id="2d8c2-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="2d8c2-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="2d8c2-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
