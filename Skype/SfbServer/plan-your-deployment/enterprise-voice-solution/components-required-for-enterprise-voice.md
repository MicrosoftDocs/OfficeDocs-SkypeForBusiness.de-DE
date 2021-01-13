---
title: Erforderliche Komponenten für Enterprise-VoIP in Skype for Business Server
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
description: Eine Zusammenfassung der Enterprise-VoIP in Skype for Business Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825825"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Erforderliche Komponenten für Enterprise-VoIP in Skype for Business Server
 
Eine Zusammenfassung der Enterprise-VoIP in Skype for Business Server.
  
Zum Bereitstellen Enterprise-VoIP sind die folgenden Komponenten in Ihrer Topologie erforderlich. 
  
- Ein oder mehrere Vermittlungsserver, die Signaldaten und in einigen Konfigurationen Medien zwischen Ihrer internen Skype for Business Server-, Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem Session Initiation Protocol (SIP)-Trunk übersetzen. Die Vermittlungsserver sind die wichtigste Komponente in Ihrer Enterprise-VoIP Bereitstellung. Weitere Informationen finden Sie unter [Vermittlungsserverkomponente in Skype for Business Server](mediation-server.md).
    
    Vermittlungsserver können mit Front-End-Servern ausgeführt oder als eigenständige Server installiert werden.
    
- PstN-Konnektivitätskomponenten, die SIP-Trunks oder PSTN-Gateways umfassen können. Weitere Informationen finden Sie unter Komponenten für die [Festnetzanbindung in Skype for Business Server.](pstn-connectivity.md)
    
- Edgeserver, die die Verwendung von Enterprise-VoIP von Benutzern ermöglichen, wenn sie sich außerhalb der Firewall Ihrer Organisation befinden. 
    
    Der Zugriffs-Edgedienst bietet eine SIP-Signalisierung für Anrufe von Skype for Business-Benutzern, die sich außerhalb der Firewall Ihrer Organisation befinden. Der A/V-Edgedienst ermöglicht es Medien Firewalls und NAT zu passieren. Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.
    
    Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für ihn bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.
    
- Außerdem werden einige Enterprise-VoIP auf Front-End-Servern ausgeführt. Weitere Informationen zu diesen Komponenten finden Sie unter ["Front-End-Server-VoIP-Komponenten für Skype for Business Server".](front-end-server-voip.md)
    

