---
title: Für Enterprise-VoIP in Skype für Business Server erforderlichen Komponenten
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype für Business Server.
ms.openlocfilehash: 513f116f1c92bbe931e9015bc8507b0c1f16fc1a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881804"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Für Enterprise-VoIP in Skype für Business Server erforderlichen Komponenten
 
Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype für Business Server.
  
Die folgenden Komponenten sind für die Bereitstellung von Enterprise-VoIP in Ihrer Topologie erforderlich. 
  
- Eine oder mehrere Vermittlungsserver, die Signalisierung und in einigen Konfigurationen, Medien zwischen Ihrem internen Skype für Business Server, Enterprise-VoIP-Infrastruktur und ein Gateway public switched Telephone Network, (PSTN) oder ein Session Initiation-Protokoll übersetzen Trunks (SIP). Der Vermittlungsserver sind die wichtigsten Komponente in der Enterprise-VoIP-Bereitstellung. Weitere Informationen finden Sie unter [Mediation Server Component in Skype für Business Server](mediation-server.md).
    
    Vermittlungsserver können mit dem Front-End-Server verbunden oder als eigenständiger Server installiert werden.
    
- PSTN-Konnektivitätskomponenten, die SIP-Trunks oder PSTN-Gateways angeben können. Weitere Informationen finden Sie unter [PSTN Connectivity Komponenten in Skype für Business Server](pstn-connectivity.md).
    
- Edge-Server, der die Verwendung von Enterprise-VoIP-Funktionen von den Benutzern ermöglicht, wenn sie sich außerhalb der Firewall Ihrer Organisation befinden. 
    
    Der Zugriffs-Edgeservers Service bietet SIP-Signale für Anrufe von Skype für Unternehmensbenutzer, die sich außerhalb der Firewall Ihrer Organisation befinden. Der A/V-Edgedienst ermöglicht es Medien, Firewalls und NAT zu passieren. Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.
    
    Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für diesen bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.
    
- Darüber hinaus werden einige Enterprise-VoIP-Komponenten auf Front-End-Servern ausgeführt. Ausführliche Informationen zu diesen Komponenten finden Sie unter [Front-End-Server-VoIP-Komponenten für Skype für Business Server](front-end-server-voip.md)
    

