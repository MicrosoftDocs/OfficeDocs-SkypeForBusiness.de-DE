---
title: Edgecomputereinstellungen
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
description: 'Führen Sie folgende Schritte aus, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:'
ms.openlocfilehash: 3570675fd82512aa25d760c2380f05a2de80cec6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990196"
---
# <a name="edge-machine-settings-expander"></a>Edgecomputereinstellungen
 
Führen Sie folgende Schritte aus, um die Eigenschaften für einen Server in einem Pool von Edge-Servern zu bearbeiten:
  
Der **interne Name oder FQDN** kann durch Bearbeiten der vollqualifizierte Domänenname (FQDN) geändert werden. Der FQDN muss der Domain Name System (DNS) Host (A)-Einträge und der Antragstellername des Zertifikats an den Server für die interne Schnittstelle des Edgeservers Netzwerk zugewiesen übereinstimmen. Der Wert der **internen IP-Adresse** definiert die IP-Adresse, die die Netzwerkschnittstelle zugewiesen ist, die als internes Netzwerk, relativ zu den Perimeter Network Entwurf definiert ist.
  
Die nächsten drei Abschnitte des Dialogfelds definieren Sie die IP-Adressen für die externe Konfiguration von dieser Edge-Server. Die Möglichkeit zum Ändern der IP-Adressen wird durch die Einstellung beeinflusst **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** auf die Einstellungen der Eigenschaften auf dem Edge-Server-pool-Ebene.
  
## <a name="sip-access"></a>SIP-Zugriff

Bearbeiten Sie die externe IP-Adresse, die auf die Netzwerkschnittstelle des Zugriffs durch Session Initiation Protocol (SIP) zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.
  
> [!NOTE]
> Wenn die Einstellung **Aktivieren separaten FQDN und IP-Adressen für Webkonferenzen und A / V** im Pool Einstellungsseite aktiviert ist, der nur die IP-Adresse für den SIP-Zugriff für die Bearbeitung zur Verfügung stehen.
  
## <a name="web-conferencing"></a>Webkonferenzen

Bearbeiten Sie die externe IP-Adresse, die auf die Netzwerkschnittstelle für Webkonferenzen zugewiesen ist. Diese IP-Adresse kann es sich um eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.
  
## <a name="audiovideo"></a>Audio-Video

Bearbeiten Sie die externe IP-Adresse, die die Netzwerkschnittstelle für Audio/Video zugeordnet ist (A / V). Diese IP-Adresse kann es sich um eine öffentliche IP-Adresse oder eine Adresse in der privaten IP-Adressbereich sein.
  
Die Einstellung für **NAT-aktivierte öffentliche IP-Adresse verwendet,** lautet der öffentlichen Adresse wird von der externen Schnittstelle für die entweder die A / V Netzwerk-Schnittstelle oder der Edge-Server in der Regel. Wenn die Einstellung **Aktivieren separaten FQDN und IP-Adressen für Webkonferenzen und A / V** ist aktiviert, wird diese öffentliche IP-Adresse für alle drei externen Schnittstellen verwendet.
  

