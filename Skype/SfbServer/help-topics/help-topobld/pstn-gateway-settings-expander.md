---
title: PSTN-Gatewayeinstellungen – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern, ändern Sie die folgenden Felder:'
---

# <a name="pstn-gateway-settings-expander"></a>PSTN-Gatewayeinstellungen – Erweiterung
 
Um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern, ändern Sie die folgenden Felder:
  
Der Gateway-FQDN oder die IP-Adresse ist ein erforderlicher Eintrag und definiert den **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)** des PSTN-Gateways entsprechend der Definition durch einen DNS-Hosteintrag (Domain Name System, A),einen statischen HOSTS-Dateieintrag oder die IP-Adresse des PSTN-Gateways.
  
Das SIP-Transportprotokoll kann entweder TCP (Transmission Control Protocol) oder Transport Layer Security (TLS) sein. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.
  
Wählen Sie aus, ob IPv4 und IPv6 für das Gateway aktiviert werden sollen.
  
Die **alternative Medien-IP-Adresse** ist eine Definition für den Vermittlungsserver, für den das bereitgestellte PSTN-Gateway eine andere IP-Adresse für Mediendatenverkehr aufweist als die standardmäßig konfigurierte IP-Adresse, die in der Regel für SIP-Datenverkehr reserviert ist. Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien. Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway den alternativen Pfad für Medien nicht.
  

