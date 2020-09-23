---
title: PSTN-Gatewayeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:'
ms.openlocfilehash: 10669d4355acc8d2ea1a8546275116660c1ac7a7
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216586"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN-Gatewayeinstellungen – Erweiterung
 
Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:
  
Der FQDN oder die IP-Adresse des Gateways ist ein erforderlicher Eintrag und definiert den **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)** des PSTN-Gateways, der durch einen Domain Name System (DNS)-Host (a)-Eintrag, einen statischen Hosts-Dateieintrag oder die IP-Adresse des PSTN-Gateways definiert ist.
  
Das SIP-Transport Protokoll kann entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) sein. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.
  
Wählen Sie aus, ob IPv4 und IPv6 für das Gateway aktiviert werden sollen.
  
Die **Alternative Medien-IP-Adresse** ist eine Definition für die Vermittlungsserver, für die das bereitgestellte PSTN-Gateway über eine andere IP-Adresse für den Mediendatenverkehr verfügt als die standardmäßig konfigurierte IP-Adresse, die in der Regel für den SIP-Datenverkehr reserviert ist. Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere unterstützt eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien. Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway nicht den alternativen Pfad für Medien.
  

