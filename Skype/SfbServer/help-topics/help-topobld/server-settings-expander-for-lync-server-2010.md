---
title: Servereinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Gehen Sie wie folgt vor, um die Eigenschaften für diesen Computer zu bearbeiten:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297610"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8adac-103">Servereinstellungen für Lync Server 2010 – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="8adac-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="8adac-104">Gehen Sie wie folgt vor, um die Eigenschaften für diesen Computer zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="8adac-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="8adac-105">Bearbeiten Sie den **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)** für diesen Computer.</span><span class="sxs-lookup"><span data-stu-id="8adac-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="8adac-106">Dieser Eintrag muss mit dem Computernamen übereinstimmen, wie er im DNS (Domain Name System) definiert ist, sowie in "Subject Alternative Names (San)" oder "Subject Name (SN)" des Zertifikats, das diesem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8adac-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="8adac-107">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="8adac-107">You select one of the following:</span></span>
    
    <span data-ttu-id="8adac-108">**Alle konfigurierten IP-Adressen verwenden**: Wählen Sie diese Option aus, um alle konfigurierten IP-Adressen auf dem Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8adac-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8adac-109">Wenn der Computer über mehrere IP-Adressen verfügt, müssen Sie beachten, dass die diesem Computer zugeordneten Dienste alle IP-Adressen für alle Dienste verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="8adac-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="8adac-110">Wenn ein Überwachungsserver oder-Dienst die Kommunikation mit einer bestimmten IP-Adresse und einem Port erwartet, kann der Dienst möglicherweise nicht die beste Auswahl für die IP-Adresse treffen, die Sie abhören möchten.</span><span class="sxs-lookup"><span data-stu-id="8adac-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="8adac-111">**Einschränken der Dienstnutzung auf ausgewählte IP-Adressen**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen für die **primäre IP-Adresse** definieren möchten, die dieser Computer für die Kommunikation von anderen Computern und Pools in der Bereitstellung überwacht.</span><span class="sxs-lookup"><span data-stu-id="8adac-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="8adac-112">Definieren Sie die **PSTN-IP-Adresse** für die spezifische IP-Adresse, die der Computer und Dienst für die Kommunikation überwacht, und senden Sie die Kommunikation an das definierte PSTN-Gateway oder die IP-Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="8adac-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

