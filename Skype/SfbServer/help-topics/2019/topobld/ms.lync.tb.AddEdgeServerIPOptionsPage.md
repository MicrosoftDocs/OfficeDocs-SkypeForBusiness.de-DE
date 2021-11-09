---
title: Hinzufügen der IP-Adresse des Edgeservers – Optionen
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server können Sie IPv4- und IPv6-Adressen für jede Schnittstelle für den Edgeserver und edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:'
ms.openlocfilehash: cd742999521c4700b969ac001153135b403962df
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829318"
---
# <a name="add-edge-server-ip-options"></a>Hinzufügen der IP-Adresse des Edgeservers – Optionen
 
Skype for Business Server können Sie IPv4- und IPv6-Adressen für jede Schnittstelle für den Edgeserver und edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:
  
- **Aktivieren von IPv4 auf der internen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf den Edgeserver oder die interne Schnittstelle des Edgepools anwenden möchten.
    
- **Aktivieren von IPv6 auf der internen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf den Edgeserver oder die interne Schnittstelle des Edgepools anwenden möchten.
    
- **Aktivieren von IPv4 auf der externen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Edgeserver- oder Edgepoolschnittstelle anwenden möchten.
    
- **Aktivieren von IPv6 auf der externen Schnittstelle:** Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Edgeserver- oder Edgepoolschnittstelle anwenden möchten.
    
Sie können auch den Edgeserver oder Edgepool so konfigurieren, dass eine Netzwerkadressenübersetzungsadresse für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.
  
NAT-Unterstützung. Die Netzwerkadressübersetzung (Network Address Translation, NAT) wird bei Verwendung des Hardwarelastenausgleichs nicht unterstützt. Wählen Sie daher nicht die NAT-Option aus, wenn Sie einen Edgeserverpool mit Hardwarelastenausgleich bereitstellen.
  

