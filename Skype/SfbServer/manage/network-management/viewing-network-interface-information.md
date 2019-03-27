---
title: Anzeigen von Informationen zu Netzwerkschnittstellen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkInterface anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung.
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888029"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Anzeigen von Netzwerkschnittstelleninformationen in Skype für Business Server

Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkInterface** anzeigen. Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. 

## <a name="to-view-network-interface-information"></a>So zeigen Sie Netzwerkschnittstelleninformationen an

  - Um Netzwerkschnittstelleninformationen anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkInterface
    
    Dieser Befehl gibt Informationen ähnlich dem folgenden für jede Netzwerkschnittstelle zurück:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Weitere Informationen hierzu finden Sie unter [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


