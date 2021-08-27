---
title: Anzeigen von Netzwerkschnittstelleninformationen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Sie können Informationen zur Netzwerkschnittstelle anzeigen, indem Sie Windows PowerShell und das Cmdlet Get-CsNetworkInterface verwenden. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen.
ms.openlocfilehash: 64e22ef14260ebadbbbe05ac1c7eff8cdf0b2ff1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585049"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Anzeigen von Netzwerkschnittstelleninformationen in Skype for Business Server

Sie können Informationen zur Netzwerkschnittstelle anzeigen, indem Sie Windows PowerShell und das Cmdlet **"Get-CsNetworkInterface"** verwenden. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. 

## <a name="to-view-network-interface-information"></a>So zeigen Sie Netzwerkschnittstelleninformationen an

  - Geben Sie zum Anzeigen von Netzwerkschnittstelleninformationen den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkInterface
    
    Dieser Befehl gibt für jede Netzwerkschnittstelle Informationen wie die folgenden zurück:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Ausführliche Informationen finden Sie unter ["Get-CsNetworkInterface".](/powershell/module/skype/Get-CsNetworkInterface)