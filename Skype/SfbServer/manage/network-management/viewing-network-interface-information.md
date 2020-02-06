---
title: Anzeigen von Netzwerkschnittstelleninformationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkInterface anzeigen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817351"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="634f7-104">Anzeigen von Netzwerkschnittstelleninformationen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="634f7-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="634f7-105">Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkInterface** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="634f7-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="634f7-106">Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="634f7-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="634f7-107">So zeigen Sie Netzwerkschnittstelleninformationen an</span><span class="sxs-lookup"><span data-stu-id="634f7-107">To view network interface information</span></span>

  - <span data-ttu-id="634f7-108">Wenn Sie Netzwerkschnittstelleninformationen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="634f7-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="634f7-109">Dieser Befehl gibt für jede Netzwerkschnittstelle Informationen ähnlich der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="634f7-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="634f7-110">Ausführliche Informationen finden Sie unter [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="634f7-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


