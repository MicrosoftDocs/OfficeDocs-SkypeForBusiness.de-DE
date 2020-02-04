---
title: Edgecomputereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Wenn Sie die Eigenschaften für Edgeserver-Computer als einzelnen Edgeserver oder als Mitgliedscomputer in einem Edge-Pool bearbeiten möchten, konfigurieren Sie die Konfigurationseinstellungen für Servername und IP-Adresse:'
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684778"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="38594-103">Edgecomputereinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="38594-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="38594-104">Wenn Sie die Eigenschaften für Edgeserver-Computer als einzelnen Edgeserver oder als Mitgliedscomputer in einem Edge-Pool bearbeiten möchten, konfigurieren Sie die Konfigurationseinstellungen für **Servername und IP-Adresse** :</span><span class="sxs-lookup"><span data-stu-id="38594-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="38594-105">**Interner Name oder FQDN**: Geben Sie den Namen des Computers ein, auf den im DNS (Domain Name System) Bezug genommen wird.</span><span class="sxs-lookup"><span data-stu-id="38594-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="38594-106">**Interne IPv4-Adresse**: Geben Sie die IPv4-Adresse der internen Netzwerkschnittstellenkarte (NIC) für diesen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="38594-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="38594-107">Sie konfigurieren die **externe IPv4-Adresse** des **Access Edge-Diensts** , die diesem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="38594-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="38594-108">Wenn Sie die Verwendung einer einzelnen IP-Adresse für die Edgeserver-Konfiguration ausgewählt haben, können Sie nur die externe IPv4-Adresse für den Access Edge-Dienst bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="38594-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="38594-109">Die anderen Edge-Dienste verwenden dieselbe IPv4-Adresse wie der Access-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="38594-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="38594-110">Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **externe IPv4-Adresse** des **Webkonferenz Diensts** , die diesem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="38594-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="38594-111">Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **externe IPv4-Adresse** des **A/V-Edgedienst** , die diesem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="38594-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="38594-112">Wenn Sie zum Bearbeiten zur Verfügung stehen, konfigurieren Sie die **NAT-fähige öffentliche IPv4-Adresse** , die diesem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="38594-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="38594-113">Die Konfigurationseigenschaft für **NAT-fähige öffentliche IPv4-Adressen** steht nur zur Bearbeitung zur Verfügung, wenn Sie für den A/V-Edgedienst Netzwerkadressübersetzung (Network Address Translation, NAT) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="38594-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="38594-114">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="38594-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="38594-115">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="38594-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="38594-116">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="38594-116">**Help** Displays this help screen.</span></span>
  

