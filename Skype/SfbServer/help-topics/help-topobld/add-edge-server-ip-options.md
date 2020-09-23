---
title: Hinzufügen der IP-Adresse des Edgeservers – Optionen
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
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für die Edgeserver und Edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219790"
---
# <a name="add-edge-server-ip-options"></a>Hinzufügen der IP-Adresse des Edgeservers – Optionen
 
Microsoft lync Server 2013 können Sie IPv4-und IPv6-Adressen für jede Schnittstelle für die Edgeserver und Edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:
  
- **IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
- **IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.
    
- **IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
- **IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.
    
Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.
  
NAT-Unterstützung. Die Netzwerkadressübersetzung (Network Address Translation, NAT) wird nicht unterstützt, wenn Sie einen Hardwarelastenausgleich verwenden, wählen Sie daher die Option NAT nicht aus, wenn Sie einen Edgeserver Pool mit Hardwarelastenausgleich bereitstellen.
  

