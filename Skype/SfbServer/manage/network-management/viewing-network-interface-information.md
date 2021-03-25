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
localization_priority: Normal
description: Sie können Netzwerkschnittstelleninformationen mithilfe von Windows PowerShell und dem Get-CsNetworkInterface anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen.
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122419"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Anzeigen von Netzwerkschnittstelleninformationen in Skype for Business Server

Sie können Netzwerkschnittstelleninformationen mit Windows PowerShell **und dem Cmdlet Get-CsNetworkInterface** anzeigen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. 

## <a name="to-view-network-interface-information"></a>So zeigen Sie Netzwerkschnittstelleninformationen an

  - Geben Sie zum Anzeigen von Netzwerkschnittstelleninformationen den folgenden Befehl in die Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkInterface
    
    Dieser Befehl gibt Informationen wie die folgenden für jede Netzwerkschnittstelle zurück:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Weitere Informationen finden Sie unter [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).