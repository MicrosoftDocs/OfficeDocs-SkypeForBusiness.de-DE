---
title: Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Bearbeiten Sie die Einstellungen für den Edge-Server oder Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203130"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="22945-103">Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="22945-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="22945-104">Bearbeiten Sie die Einstellungen für den Edge-Server oder Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="22945-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="22945-105">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="22945-105">**General**</span></span>
  
- <span data-ttu-id="22945-106">**Interner FQDN des Pools**: der vollqualifizierten Domänennamen des internen Pool ist die Identität des Edge-Server oder Edge-Pools, wie im Domain Name System (DNS) Host (A oder AAAA für IPv6) Datensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="22945-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="22945-107">Wählen Sie **aktivieren den Verbund für diesen edgepool (Port 5061)** aus, wenn Sie den Edgeserver oder edgepool für den Verbund mit anderen Session Initiation Protocol-Partnern aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="22945-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="22945-108">Sie können nur auf einem Edge-Server oder Edge-Pool aktiv für den Verbund definieren.</span><span class="sxs-lookup"><span data-stu-id="22945-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="22945-109">Die Konfiguration der zugehörige Screenshot dargestellt gibt an, dass bereits einen anderen Edgeserver oder Edge-Pool für den Verbund konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="22945-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="22945-110">Der externe DNS-SRV-Eintrag für den Verbund (_sipfederationtls.\< externe Domänennamen\>) verweist auf den Edgeserver oder edgepool für den Verbund.</span><span class="sxs-lookup"><span data-stu-id="22945-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="22945-111">Die **Interne Konfiguration Replikation Port (HTTPS)**, die standardmäßig auf TCP-Port 4443, ist der Port, der lokalen Kopie (d. h., lokal auf den Edge-Servern) Kopie des zentralen Verwaltungsspeichers über repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="22945-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="22945-112">Die lokale Kopie des zentralen Verwaltungsspeichers ist in die **RTCLOCAL** -Datenbank in SQL Server auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="22945-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="22945-113">Die Replikation ist unidirektional, initiiert aus den zentralen Verwaltungsserver (oder die Front-End-Server oder Front-End-Pool, der die Rolle des zentralen Verwaltungsservers beinhaltet) mit den Edgeservern und ein Port für die interne Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="22945-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="22945-114">**Auswahl für nächsten hop**</span><span class="sxs-lookup"><span data-stu-id="22945-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="22945-115">Wählen Sie den **nächsten hoppool**, für die Liste aus.</span><span class="sxs-lookup"><span data-stu-id="22945-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="22945-116">Sie definieren Sie entweder einen Director, Director-Pool Front-End-Server oder Front-End-Pool dieser Rolle übernehmen.</span><span class="sxs-lookup"><span data-stu-id="22945-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="22945-117">Der nächste hoppool ist der Server oder Serverpool, die eingehende SIP-Nachrichten vom Edge-Server akzeptieren oder interne Schnittstelle des Edgeservers Pool und Senden ausgehender SIP an die interne Schnittstelle des Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="22945-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22945-118">Der Director ist eine optionale Rolle, und wenn Sie sich, keine Director-Server bereitstellen entscheiden, wird die Front-End-Server (einzelner Computer oder Pool) die Director-Rolle voraus.</span><span class="sxs-lookup"><span data-stu-id="22945-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="22945-119">**Einstellungen für externe**</span><span class="sxs-lookup"><span data-stu-id="22945-119">**External settings**</span></span>
  
<span data-ttu-id="22945-120">In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edge-Server oder Edge-Pools zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="22945-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="22945-121">Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="22945-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="22945-122">Wählen Sie aus der **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen, wenn Sie unterschiedliche IP-Adressen und vollqualifizierten Domänennamen zuweisen möchten den Namen für jeden Dienst Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="22945-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22945-123">Wenn Sie das Kontrollkästchen nicht aktivieren möchten, müssen Sie für jeden Dienst Edge eigenen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="22945-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="22945-124">Jeder edgedienst nutzen den FQDN für Zugriffs-edgediensts definiert und wird daher dieselbe IP-Adresse verwenden.</span><span class="sxs-lookup"><span data-stu-id="22945-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="22945-125">Jeder edgedienst muss eindeutig identifiziert werden, indem eine unterschiedliche IP-Adresse und denselben Port oder der dieselbe IP-Adresse und eindeutige Portwerte.</span><span class="sxs-lookup"><span data-stu-id="22945-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="22945-126">Wählen Sie **A / V-edgedienst ist für NAT aktiviert** Wenn Sie A konfigurieren möchten a / V-edgedienst verwenden eine private Adresse oder andere Adresse, die hinter einem Gerät Network Address Translation (NAT) ausgeblendet ist.</span><span class="sxs-lookup"><span data-stu-id="22945-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="22945-127">Um den **Zugriffs-edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für Zugriffs-edgediensts gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert</span><span class="sxs-lookup"><span data-stu-id="22945-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="22945-128">Um den **Webkonferenz-edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für den Webkonferenz-edgedienst gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert</span><span class="sxs-lookup"><span data-stu-id="22945-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="22945-129">So bearbeiten Sie die **A / V-edgedienst**, definieren Sie einen **Pool-FQDN** für den A / V-edgedienst gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert</span><span class="sxs-lookup"><span data-stu-id="22945-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="22945-130">Wenn Sie ausgewählt haben, haben die **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen nur der Zugriffs-edgedienst Pool-FQDN wird zur Bearbeitung verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="22945-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="22945-131">Weisen Sie unterschiedliche Ports für jede der drei edgedienste.</span><span class="sxs-lookup"><span data-stu-id="22945-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="22945-132">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="22945-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="22945-133">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="22945-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="22945-134">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="22945-134">**Help** Displays this help screen.</span></span>
  

