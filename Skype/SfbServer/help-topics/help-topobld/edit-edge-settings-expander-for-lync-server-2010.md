---
title: Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Sie bearbeiten die Einstellungen für die Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216116"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="16918-103">Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="16918-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="16918-104">Sie bearbeiten die Einstellungen für die Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="16918-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="16918-105">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="16918-105">**General**</span></span>
  
- <span data-ttu-id="16918-106">**Interner FQDN des Pools**: der vollqualifizierte Domänenname des internen Pools ist die Identität der Edgeserver oder Edgepool, die im DNS-Eintrag (Domain Name System) (DNS)-Host (A oder AAAA für IPv6) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="16918-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="16918-107">Wählen Sie Partner **Verbund für diesen Edgepool aktivieren (Port 5061)** aus, wenn Sie die Edgeserver oder Edgepool für den Verbund mit anderen Session Initiation Protocol-Partnern aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="16918-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="16918-108">Sie können nur eine Edgeserver oder aktiv für den Verbund Edgepool definieren.</span><span class="sxs-lookup"><span data-stu-id="16918-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="16918-109">Die im dazugehörigen Screenshot angezeigte Konfiguration gibt an, dass bereits ein anderes Edgeserver oder Edgepool für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="16918-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="16918-110">Der externe DNS-SRV-Eintrag für den Verbund (_sipfederationtls. _tcp. \<external domain name\> ) zeigt auf den Edgeserver oder Edgepool für den Verbund.</span><span class="sxs-lookup"><span data-stu-id="16918-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="16918-111">Der **interne Konfigurations Replikations Port (HTTPS)** ist standardmäßig am TCP-Port 4443 der Port, über den die lokale Kopie des zentralen Verwaltungsspeichers (lokal für die Edgeserver) repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="16918-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="16918-112">Die lokale Kopie des zentralen Verwaltungsspeichers befindet sich in der SQL Server auf jedem Computer in der **RTCLOCAL** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="16918-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="16918-113">Die Replikation erfolgt unidirektional, initiiert vom zentralen Verwaltungsserver (oder dem Front-End-Server oder Front-End-Pool mit der zentralen Verwaltungsserverrolle) auf den Edgeserver und ist ein interner Schnittstellen Port.</span><span class="sxs-lookup"><span data-stu-id="16918-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="16918-114">**Auswahl für nächsten Hop**</span><span class="sxs-lookup"><span data-stu-id="16918-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="16918-115">Treffen Sie in der Liste **Nächster Hoppool** eine Auswahl.</span><span class="sxs-lookup"><span data-stu-id="16918-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="16918-116">Sie definieren entweder einen Director, Directorpool, Front-End-Server oder Front-End-Pool, um diese Rolle zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="16918-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="16918-117">Der Pool für den nächsten Hop ist der Server oder Serverpool, der eingehende SIP-Nachrichten vom Edgeserver oder Edgepool internen Schnittstelle akzeptiert und ausgehende SIP an die interne Edge-Schnittstelle sendet.</span><span class="sxs-lookup"><span data-stu-id="16918-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="16918-118">Der Director ist eine optionale Rolle, und wenn Sie Directors nicht bereitstellen möchten, übernehmen die Front-End-Server (einzelner Computer oder Pool) die Director-Rolle.</span><span class="sxs-lookup"><span data-stu-id="16918-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="16918-119">**Externe Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="16918-119">**External settings**</span></span>
  
<span data-ttu-id="16918-120">In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edgeserver oder Edgepool bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="16918-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="16918-121">Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="16918-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="16918-122">Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie jedem Edgeserver Dienst unterschiedliche IP-Adressen und vollqualifizierte Domänennamen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="16918-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="16918-123">Wenn Sie das Kontrollkästchen nicht aktivieren, müssen Sie für jeden Edgedienst separate Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="16918-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="16918-124">Jeder Edgedienst gibt den für die Zugriffs-Edgedienst definierten FQDN frei und verwendet daher dieselbe IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="16918-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="16918-125">Jeder Edgedienst muss entweder mit einer separaten IP-Adresse und demselben Port oder derselben IP-Adresse und separaten Portwerten eindeutig identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="16918-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="16918-126">Wählen Sie **A/V-Edgedienst ist NAT aktiviert** aus, wenn Sie die A/V-Edgedienst so konfigurieren möchten, dass eine private Adresse oder andere Adresse verwendet wird, die hinter einem NAT-Gerät (Network Address Translation, Netzwerkadressübersetzung) verborgen ist.</span><span class="sxs-lookup"><span data-stu-id="16918-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="16918-127">Um die **Zugriffs-Edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für die Zugriffs-Edgedienst, wie in DNS durch Host definiert (A und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert.</span><span class="sxs-lookup"><span data-stu-id="16918-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="16918-128">Um die **Webkonferenz-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für die Webkonferenz-Edgedienst, wie in DNS durch Host definiert (a und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert</span><span class="sxs-lookup"><span data-stu-id="16918-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="16918-129">Um die **A/V-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für die A/V-Edgedienst, wie in DNS durch Host definiert (A und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert</span><span class="sxs-lookup"><span data-stu-id="16918-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="16918-130">Wenn Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** aktiviert haben, steht nur der FQDN des Zugriffs-Edgedienst Pools zur Bearbeitung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="16918-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="16918-131">Weisen Sie für die drei Edgedienste jeweils unterschiedliche Ports zu.</span><span class="sxs-lookup"><span data-stu-id="16918-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="16918-132">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="16918-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="16918-133">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="16918-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="16918-134">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="16918-134">**Help** Displays this help screen.</span></span>
  

