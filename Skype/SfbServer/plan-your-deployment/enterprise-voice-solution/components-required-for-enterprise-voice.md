---
title: Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype for Business Server.
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277006"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind
 
Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype for Business Server.
  
Zur Bereitstellung von Enterprise-VoIP sind die folgenden Komponenten in Ihrer Topologie erforderlich. 
  
- Einen oder mehrere Vermittlungsserver, die Signalübertragungen und in einigen Konfigurationen Medien zwischen Ihrem internen Skype for Business-Server, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem Sitzungs Initiierungs Protokoll übersetzen (SIP) trunk. Die Vermittlungsserver sind die wichtigste Komponente in Ihrer Enterprise-VoIP-Bereitstellung. Weitere Informationen finden Sie unter [Vermittlungs Server Komponente in Skype for Business Server](mediation-server.md).
    
    Vermittlungsserver können mit Front-End-Servern oder als eigenständige Server installiert werden.
    
- PSTN-Konnektivitäts-Komponenten, die SIP-Trunks oder PSTN-Gateways umfassen können. Weitere Informationen finden Sie unter [Komponenten der PSTN-Konnektivität in Skype for Business Server](pstn-connectivity.md).
    
- Edgeserver, der die Verwendung von Enterprise-VoIP-Features durch Ihre Benutzer ermöglicht, wenn diese sich außerhalb der Firewall Ihrer Organisation befinden. 
    
    Der Zugriffs-Edgedienst bietet SIP-Signalisierungen für Anrufe von Skype for Business-Benutzern, die sich außerhalb der Firewall Ihrer Organisation befinden. Der A/V-Edgedienst ermöglicht es Medien, Firewalls und NAT zu passieren. Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.
    
    Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für diesen bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.
    
- Darüber hinaus werden einige Enterprise-VoIP-Komponenten auf Front-End-Servern ausgeführt. Details zu diesen Komponenten finden Sie unter [VoIP-Komponenten für den Front-End-Server für Skype for Business Server](front-end-server-voip.md) .
    

