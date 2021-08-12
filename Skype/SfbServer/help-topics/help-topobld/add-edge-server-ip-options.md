---
title: Hinzufügen der IP-Adresse des Edgeservers – Optionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Mit Microsoft Lync Server 2013 können Sie IPv4- und IPv6-Adressen für jede Schnittstelle für den Edgeserver und den Edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:'
ms.openlocfilehash: 713c5030b0ca39555c57bb5ae0d36f873701c54181b46cb845d75012b3a81b65
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284865"
---
# <a name="add-edge-server-ip-options"></a>Hinzufügen der IP-Adresse des Edgeservers – Optionen
 
Mit Microsoft Lync Server 2013 können Sie IPv4- und IPv6-Adressen für jede Schnittstelle für den Edgeserver und den Edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:
  
- **Aktivieren von IPv4 auf der internen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf den Edgeserver oder die interne Schnittstelle des Edgepools anwenden möchten.
    
- **Aktivieren von IPv6 auf der internen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf den Edgeserver oder die interne Schnittstelle des Edgepools anwenden möchten.
    
- **Aktivieren von IPv4 auf der externen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Edgeserver- oder Edgepoolschnittstelle anwenden möchten.
    
- **Aktivieren von IPv6 auf der externen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Edgeserver- oder Edgepoolschnittstelle anwenden möchten.
    
Sie können auch den Edgeserver oder Edgepool so konfigurieren, dass eine Netzwerkadressenübersetzungsadresse für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.
  
NAT-Unterstützung. Die Netzwerkadressübersetzung (Network Address Translation, NAT) wird bei Verwendung des Hardwarelastenausgleichs nicht unterstützt. Wählen Sie daher nicht die NAT-Option aus, wenn Sie einen Edgeserverpool mit Hardwarelastenausgleich bereitstellen.
  

