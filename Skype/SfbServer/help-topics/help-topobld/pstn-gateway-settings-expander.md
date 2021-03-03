---
title: PSTN-Gatewayeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Ändern Sie die folgenden Felder, um die Einstellungen für ein PstN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:'
ms.openlocfilehash: 56f26a4113841b7563e42180aa51a80eedb2f859
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823725"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN-Gatewayeinstellungen – Erweiterung
 
Ändern Sie die folgenden Felder, um die Einstellungen für ein PstN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:
  
Der FQDN oder die IP-Adresse des Gateways ist ein erforderlicher Eintrag und definiert den vollqualifizierten Domänennamen **(Fully Qualified Domain Name, FQDN)** des PSTN-Gateways gemäß definition durch einen DNS-A-Eintrag (Domain Name System), einen statischen HOST-Dateieintrag oder die IP-Adresse des PSTN-Gateways.
  
Das SIP-Transport-Protokoll kann entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) sein. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.
  
Wählen Sie aus, ob IPv4 und IPv6 für das Gateway aktiviert werden sollen.
  
Die **alternative Medien-IP-Adresse** ist eine Definition für den Vermittlungsserver, für den das bereitgestellte PSTN-Gateway eine andere IP-Adresse für den Mediendatenverkehr hat als die standardmäßig konfigurierte IP-Adresse, die in der Regel für den SIP-Datenverkehr festgelegt ist. Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien. Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway den alternativen Pfad für Medien nicht.
  

