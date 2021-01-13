---
title: Hinzufügen der IP-Adresse des Edgeservers – Optionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Mit Skype for Business Server können Sie IPv4- und -IPv6-Adressen für jede Schnittstelle für den Edgeserver und edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:'
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801075"
---
# <a name="add-edge-server-ip-options"></a>Hinzufügen der IP-Adresse des Edgeservers – Optionen
 
Mit Skype for Business Server können Sie IPv4- und -IPv6-Adressen für jede Schnittstelle für den Edgeserver und edgepool konfigurieren. Gehen Sie hierzu folgendermaßen vor:
  
- **IPv4 für interne Schnittstelle** aktivieren: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edgeservers oder Edgepools anwenden möchten.
    
- **IPv6** für interne Schnittstelle aktivieren: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edgeservers oder Edgepools anwenden möchten.
    
- **IPv4 für externe** Schnittstelle aktivieren: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edgeservers oder Edgepools anwenden möchten.
    
- **IPv6 für externe** Schnittstelle aktivieren: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edgeservers oder Edgepools anwenden möchten.
    
Sie können den Edgeserver oder Edgepool auch so konfigurieren, dass eine Netzwerkadressenübersetzungsadresse für die externen IP-Adressen verwendet wird. Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.
  
NAT-Unterstützung. Die Netzwerkadressenübersetzung (Network Address Translation, NAT) wird bei Verwendung des Hardwarelastenausgleichs nicht unterstützt. Wählen Sie daher nicht die NAT-Option aus, wenn Sie einen Edgeserverpool mit Hardwaregerät zum Lastenausgleich bereitstellen.
  

