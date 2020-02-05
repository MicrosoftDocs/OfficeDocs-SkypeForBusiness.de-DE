---
title: Erstellen von Bandbreitenrichtlinien Profilen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Sie können Bandbreitenrichtlinien erstellen oder ändern, die von der Sprachanruf Steuerung für Unternehmen in Skype for Business Server verwendet werden.
ms.openlocfilehash: e54fc20c142e0eacc2758d97bdeba8043511b3fe
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767948"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="6cd24-103">Erstellen von Bandbreitenrichtlinien Profilen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6cd24-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="6cd24-104">Sie können Bandbreitenrichtlinien erstellen oder ändern, die von der Sprachanruf Steuerung für Unternehmen in Skype for Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cd24-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="6cd24-105">Bandbreitenrichtlinien definieren Einschränkungen zur Bandbreitenauslastung für in Echtzeit übertragene Audio- und Videodaten.</span><span class="sxs-lookup"><span data-stu-id="6cd24-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="6cd24-106">Bandbreitenrichtlinien gelten für Richtlinien Profile, die für die Anrufsteuerung auf mehrere Netzwerk Websites angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6cd24-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="6cd24-107">Richtlinien zu den Bandbreiteneinschränkungen, die Sie in ihrer CAC-Bereitstellung festlegen sollten, finden Sie unter [Planen der Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6cd24-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="6cd24-p102">Die im folgenden Verfahren erstellten Beispielrichtlinien legen Einschränkungen für den Audiodatenverkehr insgesamt, einzelne Audiositzungen, den Videodatenverkehr insgesamt und einzelne Videositzungen fest. Das Bandbreitenrichtlinienprofil „5Mb_Link“ legt beispielsweise folgende Einschränkungen fest:</span><span class="sxs-lookup"><span data-stu-id="6cd24-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="6cd24-110">Grenzwert für Audio: 2.000 KBit/s</span><span class="sxs-lookup"><span data-stu-id="6cd24-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="6cd24-111">Grenzwert für Audiositzung: 200 KBit/s</span><span class="sxs-lookup"><span data-stu-id="6cd24-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="6cd24-112">Grenzwert für Video: 1.400 KBit/s</span><span class="sxs-lookup"><span data-stu-id="6cd24-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="6cd24-113">Grenzwert für Videositzung: 700 KBit/s</span><span class="sxs-lookup"><span data-stu-id="6cd24-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="6cd24-p103">Der Mindestgrenzwert für Audiositzungen ist 40 KBit/s. Der Mindestgrenzwert für Videositzungen ist 100 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="6cd24-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cd24-116">So erstellen Sie bandbreitenrichtlinienprofile mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cd24-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cd24-117">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cd24-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cd24-118">Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das Cmdlet „New-CsNetworkBandwidthPolicyProfile“ aus.</span><span class="sxs-lookup"><span data-stu-id="6cd24-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="6cd24-119">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6cd24-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cd24-120">So erstellen Sie bandbreitenrichtlinienprofile mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6cd24-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cd24-121">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cd24-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cd24-122">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cd24-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cd24-123">Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil**.</span><span class="sxs-lookup"><span data-stu-id="6cd24-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="6cd24-124">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6cd24-124">Click **New**.</span></span>
    
5. <span data-ttu-id="6cd24-125">Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name** und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.</span><span class="sxs-lookup"><span data-stu-id="6cd24-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="6cd24-126">Klicken Sie auf **Audiolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Audiositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="6cd24-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="6cd24-127">Klicken Sie auf **Grenzwert für Audiositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Audiositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="6cd24-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="6cd24-128">Klicken Sie auf **Videolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Videositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="6cd24-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="6cd24-129">Klicken Sie auf **Grenzwert für Videositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Videositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="6cd24-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="6cd24-130">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Bandbreitenrichtlinienprofils ein.</span><span class="sxs-lookup"><span data-stu-id="6cd24-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="6cd24-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cd24-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="6cd24-132">Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6cd24-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cd24-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cd24-133">See also</span></span>

[<span data-ttu-id="6cd24-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6cd24-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6cd24-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6cd24-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6cd24-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6cd24-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6cd24-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6cd24-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
