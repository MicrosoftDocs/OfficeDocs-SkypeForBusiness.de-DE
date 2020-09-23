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
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="a0f8e-103">PSTN-Gatewayeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="a0f8e-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="a0f8e-104">Ändern Sie die folgenden Felder, um die Einstellungen für ein PSTN-Gateway (Public Switched Telephone Network) zu bearbeiten oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a0f8e-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="a0f8e-105">Der FQDN oder die IP-Adresse des Gateways ist ein erforderlicher Eintrag und definiert den **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)** des PSTN-Gateways, der durch einen Domain Name System (DNS)-Host (a)-Eintrag, einen statischen Hosts-Dateieintrag oder die IP-Adresse des PSTN-Gateways definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="a0f8e-106">Das SIP-Transport Protokoll kann entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) sein.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-106">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span> <span data-ttu-id="a0f8e-107">Als Standardeinstellung ist TLS festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-107">TLS is the default.</span></span> <span data-ttu-id="a0f8e-108">In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-108">Refer to the gateway vendor documentation for what you gateway supports.</span></span> <span data-ttu-id="a0f8e-109">Wenn das Gateway TLS unterstützt, ist die Standardeinstellung "TLS" die Option mit höherer Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-109">The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="a0f8e-110">Wählen Sie aus, ob IPv4 und IPv6 für das Gateway aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="a0f8e-111">Die **Alternative Medien-IP-Adresse** ist eine Definition für die Vermittlungsserver, für die das bereitgestellte PSTN-Gateway über eine andere IP-Adresse für den Mediendatenverkehr verfügt als die standardmäßig konfigurierte IP-Adresse, die in der Regel für den SIP-Datenverkehr reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="a0f8e-112">Wenn Sie diesen Parameter definieren, unterstützt das PSTN-Gateway eine andere unterstützt eine andere Netzwerkschnittstelle oder einen anderen Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="a0f8e-113">Wenn diese Adresse leer bleibt, unterstützt das PSTN-Gateway nicht den alternativen Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="a0f8e-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

