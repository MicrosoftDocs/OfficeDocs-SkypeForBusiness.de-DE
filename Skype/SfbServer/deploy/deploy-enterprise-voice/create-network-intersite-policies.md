---
title: Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 'Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden.'
---

# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Erstellen von standortübergreifenden Netzwerkrichtlinien in Skype for Business Server
 
Erstellen Sie standortübergreifende Netzwerkrichtlinien, die von Enterprise-VoIP Anrufsteuerung in Skype for Business Server verwendet werden. 
  
Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten, zwischen denen direkte WAN-Verbindungen bestehen.
  
> [!IMPORTANT]
> Eine standortübergreifende Netzwerkrichtlinie ist  *nur*  erforderlich, wenn eine direkte standortübergreifende Verbindung zwischen zwei Netzwerkstandorten besteht.
  
In der Region "Nordamerika" der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten "Reno" und "Albuquerque". Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil "20Mb_Link" angewendet.
  
### <a name="to-create-a-network-inter-site-policy"></a>So erstellen Sie eine standortübergreifende Netzwerkrichtlinie

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell**.
    
2. Führen Sie das Cmdlet New-CsNetworkInterSitePolicy aus, um standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil für zwei Standorte anzuwenden, die über eine direkte standortübergreifende Verbindung verfügen. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Wiederholen Sie Schritt 2 nach Bedarf, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandortpaare zu erstellen, die über eine direkte standortübergreifende Verbindung verfügen.
    
## <a name="see-also"></a>Siehe auch

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)