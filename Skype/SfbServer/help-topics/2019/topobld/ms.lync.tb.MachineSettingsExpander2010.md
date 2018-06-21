---
title: Servereinstellungen – Erweiterung für Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Um die Eigenschaften für diesen Computer zu bearbeiten, führen Sie die folgenden Aufgaben:'
ms.openlocfilehash: 20db8095706c1e74f1d8d0ef1628d154c3a2bd22
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964765"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e3050-103">Servereinstellungen – Erweiterung für Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e3050-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e3050-104">Um die Eigenschaften für diesen Computer zu bearbeiten, führen Sie die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="e3050-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="e3050-105">Bearbeiten Sie den **vollqualifizierten Domänennamen (FQDN)** für diesen Computer.</span><span class="sxs-lookup"><span data-stu-id="e3050-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="e3050-106">Bei diesem Eintrag muss den Namen des Computers übereinstimmen, wie er im Domain Name System (DNS) und im alternativen Antragstellernamen (SAN) oder Antragstellername (SN) des Zertifikats, die diesem Computer zugeordnet definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3050-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="e3050-107">Wählen Sie eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e3050-107">You select one of the following:</span></span>
    
    <span data-ttu-id="e3050-108">**Alle konfigurierte IP-Adressen verwenden**: Wählen Sie diese Option, um alle konfigurierten IP-Adressen auf dem Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3050-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e3050-109">Wenn der Computer über mehrere IP-Adressen verfügt, müssen Sie beachten Sie, dass die Dienste, die diesem Computer zugeordnet alle IP-Adressen für alle Dienste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3050-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="e3050-110">Wenn ein überwachenden Server oder Dienst Kommunikation einer bestimmten IP-Adresse und Port erwartet, kann der Dienst nicht die beste Auswahl an welche IP-Adresse abhören stellen.</span><span class="sxs-lookup"><span data-stu-id="e3050-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="e3050-111">**Verwendung von Grenzwert ausgewählten IP-Adressen**: Wählen Sie diese Option aus, wenn Sie bestimmte IP-Adressen für die **primäre IP-Adresse** , die diesem Computer für die Kommunikation von anderen Computer und Pools in der Bereitstellung überwacht wird, definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e3050-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="e3050-112">Definieren von **PSTN-IP-Adresse** für die spezifischen IP-Adresse, dass der Computer und -Dienst für die Kommunikation abhören und Communications an die definierte PSTN-Gateway oder IP-PBX senden werden.</span><span class="sxs-lookup"><span data-stu-id="e3050-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

