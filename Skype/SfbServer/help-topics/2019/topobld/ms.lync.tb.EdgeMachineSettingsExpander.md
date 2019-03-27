---
title: Edgecomputereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Führen Sie folgende Schritte aus, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:'
ms.openlocfilehash: 5755e03c0d760ef61b8cd4322131316c1d80a4c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899491"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="7ca44-103">Edgecomputereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="7ca44-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="7ca44-104">Führen Sie folgende Schritte aus, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="7ca44-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="7ca44-105">Der **interne Name oder FQDN** kann durch Bearbeiten der vollqualifizierte Domänenname (FQDN) geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7ca44-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="7ca44-106">Der FQDN muss der Domain Name System (DNS) Host (A)-Einträge und der Antragstellername des Zertifikats an den Server für die interne Schnittstelle des Edgeservers Netzwerk zugewiesen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7ca44-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="7ca44-107">Der Wert der **internen IP-Adresse** definiert die IP-Adresse, die die Netzwerkschnittstelle zugewiesen ist, die als internes Netzwerk, relativ zu den Perimeter Network Entwurf definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7ca44-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="7ca44-108">Die nächsten drei Abschnitte des Dialogfelds definieren Sie die IP-Adressen für die externe Konfiguration von dieser Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="7ca44-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="7ca44-109">Die Möglichkeit zum Ändern der IP-Adressen wird durch die Einstellung beeinflusst **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** auf die Einstellungen der Eigenschaften auf dem Edge-Server-pool-Ebene.</span><span class="sxs-lookup"><span data-stu-id="7ca44-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="7ca44-110">SIP-Zugriff</span><span class="sxs-lookup"><span data-stu-id="7ca44-110">SIP Access</span></span>

<span data-ttu-id="7ca44-111">Bearbeiten Sie die externe IP-Adresse, die auf die Netzwerkschnittstelle des Zugriffs durch Session Initiation Protocol (SIP) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7ca44-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="7ca44-112">Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="7ca44-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ca44-113">Wenn die Einstellung **Aktivieren separaten FQDN und IP-Adressen für Webkonferenzen und A / V** im Pool Einstellungsseite aktiviert ist, der nur die IP-Adresse für den SIP-Zugriff für die Bearbeitung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7ca44-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="7ca44-114">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="7ca44-114">Web Conferencing</span></span>

<span data-ttu-id="7ca44-115">Bearbeiten Sie die externe IP-Adresse, die auf die Netzwerkschnittstelle für Webkonferenzen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7ca44-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="7ca44-116">Diese IP-Adresse kann es sich um eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="7ca44-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="7ca44-117">Audio-Video</span><span class="sxs-lookup"><span data-stu-id="7ca44-117">Audio/Video</span></span>

<span data-ttu-id="7ca44-118">Bearbeiten Sie die externe IP-Adresse, die die Netzwerkschnittstelle für Audio/Video zugeordnet ist (A / V).</span><span class="sxs-lookup"><span data-stu-id="7ca44-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="7ca44-119">Diese IP-Adresse kann es sich um eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="7ca44-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="7ca44-120">Die Einstellung für **NAT-aktivierte öffentliche IP-Adresse verwendet,** lautet der öffentlichen Adresse wird von der externen Schnittstelle für die entweder die A / V Netzwerk-Schnittstelle oder der Edge-Server in der Regel.</span><span class="sxs-lookup"><span data-stu-id="7ca44-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="7ca44-121">Wenn die Einstellung **Aktivieren separaten FQDN und IP-Adressen für Webkonferenzen und A / V** ist aktiviert, wird diese öffentliche IP-Adresse für alle drei externen Schnittstellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ca44-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

