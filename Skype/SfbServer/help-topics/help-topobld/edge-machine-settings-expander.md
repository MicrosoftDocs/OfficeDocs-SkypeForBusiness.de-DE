---
title: Edgecomputereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Gehen Sie wie folgt vor, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:'
ms.openlocfilehash: aeb9c48968b7b5223ac33fc3419d630229724a09
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697480"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="c1a7c-103">Edgecomputereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="c1a7c-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="c1a7c-104">Gehen Sie wie folgt vor, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="c1a7c-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="c1a7c-105">Der **interne Name oder FQDN** kann geändert werden, indem Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c1a7c-106">Der FQDN muss mit dem Domänennamen-Host (A)-Eintrag (Domain Name System) und dem Antragstellernamen des Zertifikats übereinstimmen, das dem Server für die interne Edge-Netzwerkschnittstelle zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="c1a7c-107">Der Wert der **internen IP-Adresse** definiert die IP-Adresse, der die Netzwerkschnittstelle zugeordnet ist, die im Verhältnis zum Umkreisnetzwerk Entwurf als internes Netzwerk definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="c1a7c-108">In den nächsten drei Abschnitten des Dialogfelds werden die IP-Adressen für die externe Konfiguration dieses Edgeserver definiert.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="c1a7c-109">Die Möglichkeit zum Ändern der IP-Adressen ist von der Einstellung **Aktivieren des separaten FQDN und der IP-Adresse für Webkonferenzen und A/V** in den Eigenschafteneinstellungen auf der Poolebene des Edge-Servers betroffen.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="c1a7c-110">SIP-Zugriff</span><span class="sxs-lookup"><span data-stu-id="c1a7c-110">SIP Access</span></span>

<span data-ttu-id="c1a7c-111">Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für den SIP-Zugriff (Session Initiation Protocol) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="c1a7c-112">Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1a7c-113">Wenn die Einstellung **separater FQDN und IP-Adresse für Webkonferenzen und A/V** auf der Seite Pooleinstellungen aktivieren aktiviert ist, steht nur die IP-Adresse für den SIP-Zugriff zur Bearbeitung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="c1a7c-114">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="c1a7c-114">Web Conferencing</span></span>

<span data-ttu-id="c1a7c-115">Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für Webkonferenzen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="c1a7c-116">Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="c1a7c-117">Audio/Video</span><span class="sxs-lookup"><span data-stu-id="c1a7c-117">Audio/Video</span></span>

<span data-ttu-id="c1a7c-118">Bearbeiten Sie die externe IP-Adresse, die der Netzwerkschnittstelle für Audio/Video (A/V) zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="c1a7c-119">Bei dieser IP-Adresse kann es sich entweder um eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich handeln.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="c1a7c-120">Die Einstellung für die **verwendete NAT-aktivierte öffentliche IP-Adresse** ist die öffentliche Adresse, die von der externen Schnittstelle für die A/V-Netzwerkschnittstelle oder den Edgeserver im Allgemeinen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="c1a7c-121">Wenn die Einstellung **separater FQDN und IP-Adresse für Webkonferenzen aktivieren und A/V** aktiviert ist, wird diese öffentliche IP-Adresse für alle drei externen Schnittstellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1a7c-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

