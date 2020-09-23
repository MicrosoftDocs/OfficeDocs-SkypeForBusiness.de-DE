---
title: Servereinstellungen für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Führen Sie die folgenden Schritte aus, um die Eigenschaften für diesen Computer zu bearbeiten:'
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215696"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2d8ba-103">Servereinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="2d8ba-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2d8ba-104">Führen Sie die folgenden Schritte aus, um die Eigenschaften für diesen Computer zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="2d8ba-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="2d8ba-p101">Bearbeiten Sie unter **Vollqualifizierter Domänenname (FQDN)** den FQDN für diesen Computer. Dieser Eintrag muss mit dem Computernamen übereinstimmen, der im Domain Name System (DNS) und in den alternativen Antragstellernamen (SAN) bzw. Antragstellernamen (SN) des Zertifikats für diesen Computer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2d8ba-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="2d8ba-107">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="2d8ba-107">You select one of the following:</span></span>
    
    <span data-ttu-id="2d8ba-108">**Alle konfigurierten IP-Adressen verwenden**: Wählen Sie diese Option aus, um alle auf dem Computer konfigurierten IP-Adressen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d8ba-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2d8ba-p102">Beachten Sie bei mehreren auf dem Computer vorhandenen IP-Adressen, dass für die Dienste, die diesem Computer zugeordnet sind, alle IP-Adressen für alle Dienste verwendet werden. Wenn ein Überwachungsserver oder -dienst eine Kommunikation von einer bestimmten IP-Adresse und dem dazugehörigen Port erwartet, wird für den Dienst möglicherweise nicht die beste IP-Adresse für die Überwachung gewählt.</span><span class="sxs-lookup"><span data-stu-id="2d8ba-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="2d8ba-p103">**Dienstnutzung auf die ausgewählten IP-Adressen beschränken**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen als **Primäre IP-Adresse** definieren möchten, über die der Computer eine Kommunikation mit anderen Computern und Pools der Bereitstellung erwartet. Definieren Sie die **PSTN-IP-Adresse** für die jeweilige IP-Adresse, über die der Computer und der Dienst die Kommunikation erwartet und Kommunikationsdaten an das definierte PSTN-Gateway oder die Festnetztelefonanlage sendet.</span><span class="sxs-lookup"><span data-stu-id="2d8ba-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

