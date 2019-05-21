---
title: PSTN-Gatewayeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:'
ms.openlocfilehash: 80e3f6b0f6e0afa4b28b384cfe9a64ac8bbd6ebc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302182"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN-Gatewayeinstellungen – Erweiterung
 
Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:
  
Der FQDN oder die IP-Adresse des Gateways ist ein erforderlicher Eintrag, der festlegt, ob der vollqualifizierte Domänenname (FQDN)**** des PSTN-Gateways über einen DNS-A-Eintrag (Host), einen statischen HOSTS-Dateieintrag oder die IP-Adresse des PSTN-Gateways definiert ist.
  
Beim SIP-Transportprotokoll kann es sich um das Transmission Control Protocol (TCP) oder Transport Layer Security (TLS) handeln. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Als Standardeinstellung ist TLS festgelegt, und wenn das Gateway TLS unterstützt, ist dies die Option mit höherer Sicherheit.
  
Wählen Sie aus, ob für das Gateway IPv4 und IPv6 aktiviert werden soll.
  
Die **IP-Adresse des alternativen Mediums** ist eine Definition für den Vermittlungs Server, für den das bereitgestellte PSTN-Gateway eine andere IP-Adresse für den Medien Verkehr hat als die standardmäßig konfigurierte IP-Adresse, die normalerweise für den SIP-Datenverkehr reserviert ist. Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere unterstützt eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien. Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway nicht den alternativen Pfad für Medien.
  

