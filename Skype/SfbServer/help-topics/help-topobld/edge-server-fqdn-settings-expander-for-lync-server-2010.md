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
- NOCSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Konfigurieren Sie die folgenden Optionen, um die Eigenschaften unter externe Einstellungen zu definieren:'
ms.openlocfilehash: 95e55625ec698d8762832e812a79547daf4d2bcf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820057"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="19a35-103">Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="19a35-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="19a35-104">Konfigurieren Sie die folgenden Optionen, um die Eigenschaften unter **externe Einstellungen**zu definieren:</span><span class="sxs-lookup"><span data-stu-id="19a35-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="19a35-105">Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie einen eindeutigen Pool-FQDN und IP-Adressen für Webkonferenzen und Audio/Video definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19a35-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19a35-106">Wenn Sie das Kontrollkästchen für getrennte FQDN-und IP-Adressen nicht aktivieren möchten, müssen Sie für jeden der drei Dienste, die vom Edgeserver bereitgestellt werden, unterschiedliche Ports angeben.</span><span class="sxs-lookup"><span data-stu-id="19a35-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="19a35-107">Der einzige vollqualifizierte Domänenname, der konfiguriert werden soll, ist der FQDN, der dem Access Edge-Dienst zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="19a35-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="19a35-108">Aktivieren Sie das Kontrollkästchen **a/v-Edgedienst ist NAT-fähig** , wenn der a/v-Edgedienst eine IP-Adresse und-Konfiguration für Netzwerkadressübersetzung (Network Address Translation, NAT) verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="19a35-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="19a35-109">Für die aktivierten Edge-Dienste geben Sie einen **Pool-FQDN** und einen Port unter **Ports** ein.</span><span class="sxs-lookup"><span data-stu-id="19a35-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="19a35-110">Definieren Sie den FQDN des **Access Edge-Service** Pools und einen Port, der den Dienst eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="19a35-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="19a35-111">Definieren Sie den FQDN des **Web Conferencing Edge-Service** Pools (wenn separater FQDN und IP-Adresse für Webkonferenzen aktiviert sind und a/V nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="19a35-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="19a35-112">Definieren Sie den FQDN des **A/v-Edge-Service** Pools (wenn separater FQDN und IP-Adresse für Webkonferenzen aktiviert sind und a/v nicht ausgewählt ist) und einen Port, der den Dienst eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="19a35-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="19a35-113">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="19a35-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="19a35-114">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="19a35-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="19a35-115">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="19a35-115">**Help** Displays this help screen.</span></span>
  

