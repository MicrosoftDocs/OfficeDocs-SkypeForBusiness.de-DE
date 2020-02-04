---
title: PSTN-Gatewayeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:'
ms.openlocfilehash: 4d25c93e9557dd4cf85a58ab21daf94e21e6864b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701700"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="e518e-103">PSTN-Gatewayeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="e518e-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="e518e-104">Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="e518e-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="e518e-105">Der FQDN oder die IP-Adresse des Gateways ist ein erforderlicher Eintrag, der festlegt, ob der vollqualifizierte Domänenname (FQDN)\*\*\*\* des PSTN-Gateways über einen DNS-A-Eintrag (Host), einen statischen HOSTS-Dateieintrag oder die IP-Adresse des PSTN-Gateways definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e518e-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="e518e-p101">Beim SIP-Transportprotokoll kann es sich um das Transmission Control Protocol (TCP) oder Transport Layer Security (TLS) handeln. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Als Standardeinstellung ist TLS festgelegt, und wenn das Gateway TLS unterstützt, ist dies die Option mit höherer Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="e518e-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="e518e-110">Wählen Sie aus, ob für das Gateway IPv4 und IPv6 aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e518e-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="e518e-111">Die **IP-Adresse des alternativen Mediums** ist eine Definition für den Vermittlungs Server, für den das bereitgestellte PSTN-Gateway eine andere IP-Adresse für den Medien Verkehr hat als die standardmäßig konfigurierte IP-Adresse, die normalerweise für den SIP-Datenverkehr reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="e518e-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="e518e-112">Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere unterstützt eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="e518e-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="e518e-113">Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway nicht den alternativen Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="e518e-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

