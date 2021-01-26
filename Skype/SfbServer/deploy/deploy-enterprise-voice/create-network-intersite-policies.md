---
title: Erstellen standortübergreifender Netzwerkrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822475"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Erstellen standortübergreifender Netzwerkrichtlinien in Skype for Business Server
 
Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten mit direkten WAN-Verbindungen.
  
> [!IMPORTANT]
> Eine standortübergreifende Netzwerkrichtlinie ist nur  *erforderlich,*  wenn eine direkte standortübergreifende Verbindung zwischen zwei Netzwerkstandorten besteht.
  
In der Region "Nordamerika" der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten "Reno" und "Albuquerque". Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil an wendet. Im folgenden Beispiel wird das Profil "20Mb_Link" angewendet.
  
### <a name="to-create-a-network-inter-site-policy"></a>So erstellen Sie eine standortübergreifende Netzwerkrichtlinie

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Führen Sie New-CsNetworkInterSitePolicy Cmdlet aus, um standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil für zwei Standorte anzuwenden, die über eine direkte standortübergreifende Verbindung verfügen. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Wiederholen Sie Schritt 2 nach Bedarf, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandortpaare zu erstellen, die über eine direkte standortübergreifende Verbindung verfügen.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
