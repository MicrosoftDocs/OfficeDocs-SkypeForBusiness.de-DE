---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Konfigurieren Sie zum Definieren der Eigenschaften unter externe Einstellungen Folgendes:'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218246"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="93606-103">Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="93606-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="93606-104">Konfigurieren Sie zum Definieren der Eigenschaften unter **externe Einstellungen**Folgendes:</span><span class="sxs-lookup"><span data-stu-id="93606-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="93606-105">Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie einen eindeutigen Pool-FQDN und IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="93606-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93606-106">Wenn Sie das Kontrollkästchen für separate FQDN-und IP-Adressen nicht aktivieren möchten, müssen Sie für jeden der drei vom Edgeserver bereitgestellten Dienste unterschiedliche Ports bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="93606-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="93606-107">Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der dem Zugriffs-Edgedienst zugeordnete FQDN.</span><span class="sxs-lookup"><span data-stu-id="93606-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="93606-108">Aktivieren Sie das Kontrollkästchen **A/V-Edgedienst ist NAT aktiviert** , wenn die A/V-Edgedienst eine NAT-IP-Adresse (Network Address Translation, Netzwerkadressübersetzung) und-Konfiguration verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="93606-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="93606-109">Für die aktivierten Edge-Dienste geben Sie einen **Pool-FQDN** und einen Port unter **Ports** ein.</span><span class="sxs-lookup"><span data-stu-id="93606-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="93606-110">Definieren Sie den FQDN des **Zugriffs-Edgedienst** Pools und einen Port, mit dem der Dienst eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="93606-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="93606-111">Definieren Sie den FQDN des **Webkonferenz-Edgedienst** Pools (wenn unterschiedlicher FQDN und IP-Adresse für Webkonferenzen aktiviert ist und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="93606-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="93606-112">Definieren Sie den FQDN des **A/V-Edgedienst** Pools (wenn unterschiedlicher FQDN und IP-Adresse für Webkonferenzen aktiviert ist und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="93606-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="93606-113">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="93606-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="93606-114">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="93606-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="93606-115">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="93606-115">**Help** Displays this help screen.</span></span>
  

