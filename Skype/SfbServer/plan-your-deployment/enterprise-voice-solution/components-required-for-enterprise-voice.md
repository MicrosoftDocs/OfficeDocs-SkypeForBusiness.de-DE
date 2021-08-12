---
title: Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Eine Zusammenfassung der Enterprise-VoIP Komponenten in Skype for Business Server.
ms.openlocfilehash: e07c075fad0dcbad8fecfc9183b6ab1a4a1901d848d072a893444c295e56a59d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333097"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind
 
Eine Zusammenfassung der Enterprise-VoIP Komponenten in Skype for Business Server.
  
Um Enterprise-VoIP bereitzustellen, sind die folgenden Komponenten in Ihrer Topologie erforderlich. 
  
- Ein oder mehrere Vermittlungsserver, die Signalisierung und in einigen Konfigurationen Medien zwischen Ihrem internen Skype for Business Server, Enterprise-VoIP Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Trunk (Session Initiation Protocol) übersetzen. Die Vermittlungsserver sind die wichtigste Komponente in Ihrer Enterprise-VoIP Bereitstellung. Weitere Informationen finden Sie unter ["Vermittlungsserverkomponente" in Skype for Business Server.](mediation-server.md)
    
    Vermittlungsserver können mit Front-End-Servern verbunden oder als eigenständige Server installiert werden.
    
- PSTN-Verbindungskomponenten, die SIP-Trunks oder PSTN-Gateways umfassen können. Weitere Informationen finden Sie unter [PSTN-Verbindungskomponenten in Skype for Business Server.](pstn-connectivity.md)
    
- Edgeserver, die die Verwendung von Enterprise-VoIP Features durch Ihre Benutzer ermöglichen, wenn sie sich außerhalb der Firewall Ihrer Organisation befinden. 
    
    Der Zugriffs-Edgedienst stellt SIP-Signalisierung für Anrufe von Skype for Business Benutzern bereit, die sich außerhalb der Firewall Ihrer Organisation befinden. Der A/V-Edgedienst ermöglicht es Medien Firewalls und NAT zu passieren. Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.
    
    Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für ihn bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.
    
- Darüber hinaus werden einige Enterprise-VoIP Komponenten auf Front-End-Servern ausgeführt. Ausführliche Informationen zu diesen Komponenten finden Sie unter ["VoIP-Komponenten des Front-End-Servers" für Skype for Business Server](front-end-server-voip.md)
    

