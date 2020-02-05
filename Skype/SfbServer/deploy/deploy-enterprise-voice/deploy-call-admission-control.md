---
title: Bereitstellen der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern.
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767668"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Bereitstellen der Anrufsteuerung in Skype for Business Server
 
Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern. Weitere Informationen finden Sie unter [Planen der Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Bereitstellung der Anrufsteuerung

1.  Sammeln Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie, wie in [Beispiel: Erfassen der Anforderungen für die Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)beschrieben.
    
2. Falls noch nicht geschehen, müssen Sie Netzwerkregionen und Standorten definieren und Subnetzen zu Netzwerkstandorten zuordnen. Ausführliche Informationen finden Sie unter [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business](deploy-network.md).
    
3. Erstellen von Bandbreitenrichtlinien Profilen, wie in [Erstellen von Bandbreitenrichtlinien Profilen in Skype for Business Server](create-bandwidth-policy-profiles.md) beschrieben
    
4. Erstellen Sie Netzwerk Regions Verknüpfungen, wie unter [Erstellen von Netzwerk Regions Verknüpfungen in Skype for Business Server](create-network-region-links.md)beschrieben.
    
5. Erstellen Sie netzwerkübergreifende Routen, wie unter Erstellen von [Netzwerk interregionalen Routen in Skype for Business Server](create-network-interregional-routes.md)beschrieben.
    
6. Erstellen Sie netzwerkübergreifende Richtlinien, wie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in Skype for Business Server](create-network-intersite-policies.md)beschrieben.
    
7. Aktivieren Sie die Anrufsteuerung, wie unter [Aktivieren der Anrufsteuerung in Skype for Business Server](enable-call-admission-control.md)beschrieben.
    
8. Prüfen Sie ein paar abschließende Einstellungen, um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist. Ausführliche Informationen finden Sie unter [Bereitstellung von Anrufsteuerung: endgültige Checkliste für Skype for Business Server](final-checklist.md).
    

