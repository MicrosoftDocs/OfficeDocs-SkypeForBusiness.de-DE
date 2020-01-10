---
title: Erstellen von Netzwerk-standortübergreifenden Richtlinien in Skype for Business Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Erstellen von netzwerkinternen Richtlinien, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: ce1826a1205216791f056a46fa625d26e0362f1f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001745"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Erstellen von Netzwerk-standortübergreifenden Richtlinien in Skype for Business Server
 
Erstellen von netzwerkinternen Richtlinien, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden. 
  
Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten, die über direkte WAN-Verbindungen miteinander verbunden sind.
  
> [!IMPORTANT]
> Eine Inter-Site-Netzwerkrichtlinie ist *nur* erforderlich, wenn zwischen zwei Netzwerkstandorten eine direkte Querverbindung besteht.
  
In der Region „Nordamerika“ der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten „Reno“ und „Albuquerque“. Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil „20Mb_Link“ angewendet.
  
### <a name="to-create-a-network-inter-site-policy"></a>So erstellen Sie eine standortübergreifende Netzwerkrichtlinie

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das Cmdlet „New-CsNetworkInterSitePolicy“ aus, um für zwei Standorte mit standortübergreifender Direktverbindung standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Wiederholen Sie bei Bedarf Schritt 2, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandorte mit standortübergreifender Direktverbindung zu erstellen.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
