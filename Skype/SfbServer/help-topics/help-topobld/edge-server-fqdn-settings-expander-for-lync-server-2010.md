---
title: Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Um die Eigenschaften unter externe Einstellungen zu definieren, konfigurieren Sie Folgendes:'
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882348"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0cac6-103">Edgeserver-FQDN-Einstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="0cac6-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0cac6-104">Um die Eigenschaften unter **externe Einstellungen**zu definieren, konfigurieren Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0cac6-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="0cac6-105">Wählen Sie aus der **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen, wenn Sie unterschiedliche Pool-FQDN und IP-definieren möchten Adressen für Webkonferenzen und Audio/Video.</span><span class="sxs-lookup"><span data-stu-id="0cac6-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cac6-106">Wenn Sie das Kontrollkästchen für separaten FQDN und IP-Adressen nicht zu aktivieren auswählen, müssen Sie unterschiedliche Ports für jede der drei Dienste von der Edge-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="0cac6-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="0cac6-107">Der einzige vollqualifizierten Domänennamen zu konfigurieren ist der vollqualifizierte Domänenname der Zugriffs-edgedienst zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0cac6-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="0cac6-108">Wählen Sie aus der **A / V-edgedienst ist für NAT aktiviert** das Kontrollkästchen, wenn Sie möchten, dass den A / V-edgedienst, ein Netzwerk verwenden Adresse Netzwerkadressübersetzung (NAT) IP-Adresse und Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0cac6-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="0cac6-109">Für die aktivierten edgedienste Geben Sie einen **Pool-FQDN** und unter **Ports** einen port</span><span class="sxs-lookup"><span data-stu-id="0cac6-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="0cac6-110">Definieren Sie den Pool-FQDN des **Zugriffs-edgedienst** und einen Port, der den Dienst eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0cac6-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0cac6-111">Definieren Sie den Pool-FQDN des **Webkonferenz-edgedienst** (wenn aktivieren, trennen Sie FQDN und IP-Adresse für Webkonferenzen und A / V nicht ausgewählt ist) und einen Port, die den Dienst eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0cac6-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0cac6-112">Definieren der **A / V-edgedienst** Pool-FQDN (wenn aktivieren, trennen Sie FQDN und IP-Adresse für Webkonferenzen und A / V nicht ausgewählt ist) und einen Port, die den Dienst eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0cac6-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="0cac6-113">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="0cac6-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0cac6-114">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="0cac6-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0cac6-115">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="0cac6-115">**Help** Displays this help screen.</span></span>
  

