---
title: Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 634af0c7603ef9f3455933e7ef22ce06fe9f28e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741401"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype for Business Server
 
Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten, zwischen denen direkte WAN-Verbindungen bestehen.
  
> [!IMPORTANT]
> Eine standortübergreifende Netzwerkrichtlinie ist  *nur*  erforderlich, wenn eine direkte standortübergreifende Verbindung zwischen zwei Netzwerkstandorten besteht.
  
In der Region "Nordamerika" der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten "Reno" und "Albuquerque". Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil "20Mb_Link" angewendet.
  
### <a name="to-create-a-network-inter-site-policy"></a>So erstellen Sie eine standortübergreifende Netzwerkrichtlinie

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das Cmdlet New-CsNetworkInterSitePolicy aus, um standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil für zwei Standorte anzuwenden, die über eine direkte standortübergreifende Verbindung verfügen. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Wiederholen Sie Schritt 2 nach Bedarf, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandortpaare zu erstellen, die über eine direkte standortübergreifende Verbindung verfügen.
    
## <a name="see-also"></a>Weitere Informationen

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)