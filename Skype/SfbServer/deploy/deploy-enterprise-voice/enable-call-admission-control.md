---
title: Aktivieren der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Aktivieren der Anrufsteuerung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: a1a2259c754af0275e473e6c0d175039450cecf7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240495"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="7cebb-103">Aktivieren der Anrufsteuerung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7cebb-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="7cebb-104">Aktivieren der Anrufsteuerung in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="7cebb-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7cebb-105">Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7cebb-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7cebb-106">So aktivieren Sie die Anrufsteuerung mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="7cebb-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="7cebb-107">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7cebb-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7cebb-p101">Führen Sie das Cmdlet „Set-CsNetworkConfiguration“ aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7cebb-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="7cebb-110">Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7cebb-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7cebb-111">So aktivieren Sie die Anrufsteuerung mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="7cebb-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7cebb-112">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="7cebb-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7cebb-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7cebb-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="7cebb-114">Klicken Sie auf die Navigationsschaltfläche **Global**.</span><span class="sxs-lookup"><span data-stu-id="7cebb-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="7cebb-115">Klicken Sie in der Liste auf **Global** und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="7cebb-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="7cebb-116">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7cebb-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cebb-117">Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="7cebb-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="7cebb-118">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7cebb-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7cebb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cebb-119">See also</span></span>

[<span data-ttu-id="7cebb-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cebb-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="7cebb-121">Satz-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cebb-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="7cebb-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="7cebb-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
