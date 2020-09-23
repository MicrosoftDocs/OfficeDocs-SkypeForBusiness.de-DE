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
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Führen Sie zum Bearbeiten der Eigenschaften eines Servers in einem Edgeserverpool die folgenden Schritte aus:'
ms.openlocfilehash: e62cfa000379ed7318c5780bf91ac40035e6beee
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218916"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="cb6fa-103">Edgecomputereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="cb6fa-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="cb6fa-104">Führen Sie zum Bearbeiten der Eigenschaften eines Servers in einem Edgeserverpool die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="cb6fa-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="cb6fa-p101">\*\*\*\* Der interne Name oder vollqualifizierte Domänenname (FQDN) kann durch Bearbeiten des vollqualifizierten Domänennamens geändert werden. Der vollqualifizierte Domänenname muss dem DNS-Hosteintrag (A) und dem Antragstellernamen des Zertifikats entsprechen, das dem Server für die interne Edge-Netzwerkschnittstelle zugewiesen ist. Der Wert von **Interne IP-Adresse** gibt die IP-Adresse an, die der als internes Netzwerk definierten Netzwerkschnittstelle relativ zum Entwurf des Umkreisnetzwerks zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="cb6fa-p102">In den folgenden drei Abschnitten des Dialogfelds werden die IP-Adressen für die externe Konfiguration dieses Edgeservers bestimmt. Die Möglichkeit zur Änderung der IP-Adressen wird von der Einstellung **Separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** im Dialogfeld "Einstellungen" auf Edgeserverpool-Ebene bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="cb6fa-110">SIP-Zugriff</span><span class="sxs-lookup"><span data-stu-id="cb6fa-110">SIP Access</span></span>

<span data-ttu-id="cb6fa-p103">Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für den SIP-Zugriff (Session Initiation Protocol) zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb6fa-113">Wenn die Einstellung **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren** auf der Seite mit den Pooleinstellungen aktiviert ist, kann nur die IP-Adresse für den SIP-Zugriff bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="cb6fa-114">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="cb6fa-114">Web Conferencing</span></span>

<span data-ttu-id="cb6fa-p104">Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für Webkonferenzen zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="cb6fa-117">Audio/Video</span><span class="sxs-lookup"><span data-stu-id="cb6fa-117">Audio/Video</span></span>

<span data-ttu-id="cb6fa-p105">Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für Audio/Video (A/V) zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="cb6fa-p106">Die Einstellung **Für NAT aktivierte verwendete öffentliche IP-Adresse** ist die von der externen Schnittstelle für entweder die A/V-Netzwerkschnittstelle oder den Edgeserver im Allgemeinen verwendete öffentliche IP-Adresse. Wenn die Einstellung **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren** aktiviert ist, wird diese IP-Adresse für alle drei externen Schnittstellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

