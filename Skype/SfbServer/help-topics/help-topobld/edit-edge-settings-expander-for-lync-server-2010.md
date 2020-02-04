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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Sie bearbeiten die Einstellungen für den Edge-Server oder den Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697380"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="08b0a-103">Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="08b0a-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="08b0a-104">Sie bearbeiten die Einstellungen für den Edge-Server oder den Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="08b0a-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="08b0a-105">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="08b0a-105">**General**</span></span>
  
- <span data-ttu-id="08b0a-106">**Interner Pool-FQDN**: der vollqualifizierte Domänenname des internen Pools ist die Identität des Edge-Servers oder des Edge-Pools, wie er im DNS-Host (Domain Name System)-Eintrag (A oder AAAA für IPv6) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="08b0a-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="08b0a-107">Wählen Sie **Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus, wenn Sie den Edgeserver oder den Edge-Pool für den Verbund mit anderen Sitzungs Initiierungs Protokoll Partnern aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="08b0a-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="08b0a-108">Sie können nur einen Edge-Server oder einen Edge-Pool für den Verbund aktiv definieren.</span><span class="sxs-lookup"><span data-stu-id="08b0a-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="08b0a-109">Die in dem zugehörigen Screenshot angezeigte Konfiguration zeigt an, dass ein anderer Edgeserver oder Edge-Pool bereits für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="08b0a-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="08b0a-110">Der externe DNS-SRV-Eintrag für Federation (_sipfederationtls.\< _tcp. externer Domänenname\>) zeigt auf den Edgeserver oder den Edge-Pool für Federation.</span><span class="sxs-lookup"><span data-stu-id="08b0a-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="08b0a-111">Der **interne Konfigurations Replikations Port (HTTPS)** ist standardmäßig am TCP-Port 4443 der Port, auf dem die lokale (lokal für die Edgeserver) Kopie des zentralen Verwaltungsspeichers repliziert wurde.</span><span class="sxs-lookup"><span data-stu-id="08b0a-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="08b0a-112">Die lokale Kopie des zentralen Verwaltungsspeichers befindet sich in der **RTCLOCAL** -Datenbank auf jedem Computer in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08b0a-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="08b0a-113">Die Replikation erfolgt unidirektional, initiiert vom zentralen Verwaltungsserver (oder dem Front-End-Server oder Front-End-Pool, in dem sich die zentrale Verwaltungsserverrolle befindet) an die Edgeserver und ist ein interner Schnittstellenanschluss.</span><span class="sxs-lookup"><span data-stu-id="08b0a-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="08b0a-114">**Nächster Hop-Auswahl**</span><span class="sxs-lookup"><span data-stu-id="08b0a-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="08b0a-115">Wählen Sie für die Liste Ihren **nächsten Hop-Pool**aus.</span><span class="sxs-lookup"><span data-stu-id="08b0a-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="08b0a-116">Sie definieren entweder einen Director-, Director-Pool, einen Front-End-Server oder einen Front-End-Pool, um diese Rolle zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="08b0a-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="08b0a-117">Der Pool für den nächsten Hop ist der Server-oder Serverpool, der eingehende SIP-Nachrichten vom Edgeserver oder der internen Schnittstelle des Edge-Pools akzeptiert und ausgehende SIP an die interne Edge-Schnittstelle sendet.</span><span class="sxs-lookup"><span data-stu-id="08b0a-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08b0a-118">Der Director ist eine optionale Rolle, und wenn Sie sich entschließen, Directors bereitzustellen, übernimmt der Front-End-Server (einzelner Computer oder Pool) die Director-Rolle.</span><span class="sxs-lookup"><span data-stu-id="08b0a-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="08b0a-119">**Externe Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="08b0a-119">**External settings**</span></span>
  
<span data-ttu-id="08b0a-120">In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edge-Servers oder des Edge-Pools bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="08b0a-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="08b0a-121">Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="08b0a-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="08b0a-122">Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie jedem Edge-Server-Dienst unterschiedliche IP-Adressen und vollständig qualifizierte Domänennamen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="08b0a-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08b0a-123">Wenn Sie das Kontrollkästchen nicht aktivieren, müssen Sie für jeden Edgedienst separate Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="08b0a-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="08b0a-124">Jeder Edgedienst gibt den für den Access Edge-Dienst definierten FQDN frei und verwendet daher die gleiche IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="08b0a-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="08b0a-125">Jeder Edgedienst muss entweder durch eine eindeutige IP-Adresse und denselben Port oder die gleiche IP-Adresse und eindeutige Portwerte eindeutig identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="08b0a-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="08b0a-126">Wählen Sie **a/v-Edgedienst ist NAT aktiviert** aus, wenn Sie den a/v-Edgedienst so konfigurieren möchten, dass er eine private Adresse oder eine andere Adresse verwendet, die hinter einem NAT-Gerät (Network Address Translation) verborgen bleibt.</span><span class="sxs-lookup"><span data-stu-id="08b0a-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="08b0a-127">Um den **Access-Edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für den Access-Edgedienst entsprechend der Definition in DNS nach Host (A und AAAA, wenn IPv6 verwendet wird) und einem Portwert</span><span class="sxs-lookup"><span data-stu-id="08b0a-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="08b0a-128">Zum Bearbeiten des **Webkonferenz-Edgedienst**definieren Sie einen **Pool-FQDN** für den Webkonferenz-Edgedienst, wie er in DNS nach Host (a und AAAA, wenn IPv6 verwendet wird), Datensätzen und einem Portwert definiert.</span><span class="sxs-lookup"><span data-stu-id="08b0a-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="08b0a-129">Um den **a/v-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für den a/v-Edgedienst, wie er in DNS von Host (A und AAAA, wenn IPv6 verwendet wird), Datensätzen und einem Portwert definiert.</span><span class="sxs-lookup"><span data-stu-id="08b0a-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="08b0a-130">Wenn Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** aktiviert haben, steht nur der FQDN des Access-Edge-Service-Pools für die Bearbeitung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="08b0a-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="08b0a-131">Weisen Sie für jeden der drei Edge-Dienste verschiedene Ports zu.</span><span class="sxs-lookup"><span data-stu-id="08b0a-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="08b0a-132">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="08b0a-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="08b0a-133">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="08b0a-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="08b0a-134">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="08b0a-134">**Help** Displays this help screen.</span></span>
  

