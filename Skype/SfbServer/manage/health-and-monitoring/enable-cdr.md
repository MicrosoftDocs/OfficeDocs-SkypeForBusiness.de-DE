---
title: Aktivieren der Anrufdetailaufzeichnung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Datensätze für die Anrufdetailaufzeichnung in Skype for Business Server aktivieren.'
ms.openlocfilehash: 3474a82bfc9ed8e8bad954bb91346989d9181465
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992945"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="1c9d4-103">Aktivieren der Anrufdetailaufzeichnung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1c9d4-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="1c9d4-104">**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server Datensätze für die Anrufdetailaufzeichnung (CDR) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="1c9d4-p101">Bei der Aufzeichnung von Kommunikationsdatensätzen werden Nutzungs- und Diagnoseinformationen über Peer-to-Peer-Aktivitäten aufgezeichnet, z. B. Chat, VoIP-Anrufe (Voice over Internet Protocol), Anwendungsfreigabe, Dateiübertragung und Besprechungen. Anhand der Nutzungsdaten kann die Rendite berechnet werden und die Diagnosedaten können zur Problembehandlung bei Peer-to-Peer-Aktivitäten und Besprechungen eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="1c9d4-107">Verwenden Sie das folgende Verfahren, um die Aufzeichnung von Kommunikationsdatensätzen (KDS) in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="1c9d4-p102">Zur Aktivierung von KDS müssen Sie die Überwachung und eine Überwachungsdatenbank konfigurieren. Ausführliche Informationen finden Sie unter [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="1c9d4-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="1c9d4-110">So aktivieren Sie CDR mit der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="1c9d4-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1c9d4-111">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="1c9d4-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="1c9d4-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1c9d4-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="1c9d4-114">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Aktion** und anschließend auf **KDS aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c9d4-115">KDS ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1c9d4-116">Aktivieren von CDR mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1c9d4-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1c9d4-117">Sie können CdR mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsCdrConfiguration** " aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1c9d4-118">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1c9d4-119">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="1c9d4-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1c9d4-120">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="1c9d4-121">So aktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="1c9d4-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="1c9d4-122">Sie können KDS aktivieren, indem Sie den Parameter „EnableCDR“ auf „True“ ($True) setzen.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="1c9d4-123">So deaktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="1c9d4-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="1c9d4-p104">Sie können KDS deaktivieren, indem Sie den Parameter „EnableCDR“ auf „False“ ($False) setzen. Durch die Deaktivierung von KDS wird die Überwachung nicht deinstalliert, sondern die Sammlung und Speicherung von KDS-Daten angehalten.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="1c9d4-127">So verwenden Sie einen einzelnen Befehl zum Aktivieren von KDS an mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="1c9d4-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="1c9d4-128">Mit diesem Befehl wird KDS für alle derzeit in der Organisation verwendeten KDS-Einstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c9d4-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="1c9d4-129">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="1c9d4-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c9d4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c9d4-130">See also</span></span>

[<span data-ttu-id="1c9d4-131">Planen der Überwachung</span><span class="sxs-lookup"><span data-stu-id="1c9d4-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="1c9d4-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="1c9d4-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
