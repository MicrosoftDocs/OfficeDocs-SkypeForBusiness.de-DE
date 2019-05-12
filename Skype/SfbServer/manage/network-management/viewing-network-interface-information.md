---
title: Anzeigen von Informationen zu Netzwerkschnittstellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkInterface anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung.
ms.openlocfilehash: 5460ee66d61c43925de1ec74778ea8920f79df25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910263"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="83341-104">Anzeigen von Netzwerkschnittstelleninformationen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="83341-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="83341-105">Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkInterface** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="83341-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="83341-106">Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="83341-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="83341-107">So zeigen Sie Netzwerkschnittstelleninformationen an</span><span class="sxs-lookup"><span data-stu-id="83341-107">To view network interface information</span></span>

  - <span data-ttu-id="83341-108">Um Netzwerkschnittstelleninformationen anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="83341-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="83341-109">Dieser Befehl gibt Informationen ähnlich dem folgenden für jede Netzwerkschnittstelle zurück:</span><span class="sxs-lookup"><span data-stu-id="83341-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="83341-110">Weitere Informationen hierzu finden Sie unter [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="83341-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


