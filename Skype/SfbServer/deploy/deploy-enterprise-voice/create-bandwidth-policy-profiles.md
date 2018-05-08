---
title: Erstellen von Bandbreitenrichtlinienprofilen in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Erstellen oder Ändern von Bandbreitenrichtlinien, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.
ms.openlocfilehash: 6cb3e22151596fe388f5f72f3a9325c97671e257
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server-2015"></a><span data-ttu-id="318d9-103">Erstellen von Bandbreitenrichtlinienprofilen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="318d9-103">Create bandwidth policy profiles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="318d9-104">Erstellen oder Ändern von Bandbreitenrichtlinien, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="318d9-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="318d9-105">Bandbreitenrichtlinien definieren Einschränkungen für die Auslastung der Bandbreite für übertragene in Echtzeit Audio- und Videodaten.</span><span class="sxs-lookup"><span data-stu-id="318d9-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="318d9-106">Bandbreitenrichtlinien sind Richtlinienprofilen angewendeten Tobandwidth, die zu mehreren Netzwerkstandorten für die anrufsteuerung angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="318d9-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="318d9-107">Hinweise zum welche Bandbreite begrenzt, Sie sollten in Ihrer Bereitstellung der Anrufsteuerung festlegen, finden Sie unter [Planen für die anrufsteuerung in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="318d9-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="318d9-p102">Die im folgenden Verfahren erstellten Beispielrichtlinien legen Einschränkungen für den Audiodatenverkehr insgesamt, einzelne Audiositzungen, den Videodatenverkehr insgesamt und einzelne Videositzungen fest. Das Bandbreitenrichtlinienprofil „5Mb_Link“ legt beispielsweise folgende Einschränkungen fest:</span><span class="sxs-lookup"><span data-stu-id="318d9-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="318d9-110">Grenzwert für Audio: 2.000 KBit/s</span><span class="sxs-lookup"><span data-stu-id="318d9-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="318d9-111">Grenzwert für Audiositzung: 200 KBit/s</span><span class="sxs-lookup"><span data-stu-id="318d9-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="318d9-112">Grenzwert für Video: 1.400 KBit/s</span><span class="sxs-lookup"><span data-stu-id="318d9-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="318d9-113">Grenzwert für Videositzung: 700 KBit/s</span><span class="sxs-lookup"><span data-stu-id="318d9-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="318d9-p103">Der Mindestgrenzwert für Audiositzungen ist 40 KBit/s. Der Mindestgrenzwert für Videositzungen ist 100 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="318d9-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="318d9-116">Bandbreite Richtlinienprofile erstellen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="318d9-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="318d9-117">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="318d9-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="318d9-p104">Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das Cmdlet „New-CsNetworkBandwidthPolicyProfile“ aus. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="318d9-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="318d9-120">Bandbreite Richtlinienprofile erstellen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="318d9-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="318d9-121">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="318d9-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="318d9-122">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="318d9-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="318d9-123">Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil**.</span><span class="sxs-lookup"><span data-stu-id="318d9-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="318d9-124">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="318d9-124">Click **New**.</span></span>
    
5. <span data-ttu-id="318d9-125">Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name** und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.</span><span class="sxs-lookup"><span data-stu-id="318d9-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="318d9-126">Klicken Sie auf **Audiolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Audiositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="318d9-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="318d9-127">Klicken Sie auf **Grenzwert für Audiositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Audiositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="318d9-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="318d9-128">Klicken Sie auf **Videolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Videositzungen insgesamt zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="318d9-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="318d9-129">Klicken Sie auf **Grenzwert für Videositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Videositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="318d9-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="318d9-130">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Bandbreitenrichtlinienprofils ein.</span><span class="sxs-lookup"><span data-stu-id="318d9-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="318d9-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="318d9-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="318d9-132">Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="318d9-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="318d9-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="318d9-133">See also</span></span>

#### 

[<span data-ttu-id="318d9-134">Neue CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="318d9-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="318d9-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="318d9-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="318d9-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="318d9-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="318d9-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="318d9-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)

