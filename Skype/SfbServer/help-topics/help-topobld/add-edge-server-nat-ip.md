---
title: Hinzufügen der NAT-IP-Adresse des Edgeservers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: Bei der öffentlichen IP-Adresse handelt es sich um die von der Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendete IP-Adresse. Die IP-Adresse muss öffentlich routingfähig sein. Dies ist erforderlich, da Sie auf der Seite zur Auswahl von Funktionen dieses Assistenten die Option Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt ausgewählt haben.
ms.openlocfilehash: 6aa2a3444158e32f62288dc9c572aad8c067f8ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776355"
---
# <a name="add-edge-server-nat-ip"></a>Hinzufügen der NAT-IP-Adresse des Edgeservers

Bei der öffentlichen IP-Adresse handelt es sich um die von der Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendete IP-Adresse. Die IP-Adresse muss öffentlich routingfähig sein. Dies ist erforderlich, da Sie auf der Seite zur Auswahl von Funktionen dieses Assistenten die Option **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt** ausgewählt haben.

> [!NOTE]
> Die Netzwerkadressenübersetzung ermöglicht Clients oder Servern in einem privaten Netzwerk (z. B. der Bereich 192.168.0.0) die Kommunikation mit Systemen in Remotenetzwerken über öffentliche Internetnetzwerke. Bei der Netzwerkadressenübersetzung wird eine einzelne öffentliche IP-Adresse einer externen Schnittstelle internen IP-Adressen zugeordnet. Bei der NAT-Zuordnung wird der externen öffentlichen IP-Adresse eine interne Adresse zugeordnet. Für das Remotesystem ist lediglich die öffentliche Adresse der Quelle sichtbar. Das Remotesystem antwortet der Quelle, und die Quelle ermittelt anhand der NAT-Zuordnung, an welche interne IP-Adresse die Antwort zurückgegeben werden soll.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in der Edgeserver-Bereitstellungsdokumentation.