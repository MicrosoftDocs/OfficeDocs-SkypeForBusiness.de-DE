---
title: Hinzufügen der NAT-IP-Adresse des Edgeservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: Die öffentliche IP-Adresse ist die IP-Adresse, die von NAT (Netzwerkadressübersetzung) verwendet wird. Die IP-Adresse muss öffentlich geroutet werden. Dies ist erforderlich, da Sie auf der Seite "Features auswählen" des Assistenten die Option "externe IP-Adresse dieses Edge-Pools wird durch NAT übersetzt" ausgewählt haben.
ms.openlocfilehash: f06d9b61d5ffad29d24e143cf3afbbc4501a67d4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689414"
---
# <a name="add-edge-server-nat-ip"></a>Hinzufügen der NAT-IP-Adresse des Edgeservers

Die öffentliche IP-Adresse ist die IP-Adresse, die von NAT (Netzwerkadressübersetzung) verwendet wird. Die IP-Adresse muss öffentlich geroutet werden. Dies ist erforderlich, da Sie auf der Seite **"Features auswählen** " des Assistenten die Option " **externe IP-Adresse dieses Edge-Pools wird durch NAT übersetzt** " ausgewählt haben.

> [!NOTE]
> Netzwerkadressübersetzung (Network Address Translation, NAT) ermöglicht Clients oder Servern in einem privaten Netzwerk (beispielsweise dem 192.168.0.0-Bereich), mit Systemen in Remotenetzwerken über die öffentlichen Internet Netzwerke zu kommunizieren. NAT funktioniert mithilfe einer einzelnen öffentlichen IP-Adresse auf einer externen Schnittstelle und dem zuordnen interner IP-Adressen zu einer öffentlichen IP-Adresse. Bei der NAT-Zuordnung wird der externen öffentlichen IP-Adresse eine interne Adresse zugeordnet. Das Remote System sieht nur die öffentliche Adresse der Quelle. Das Remote System reagiert auf die Quelle, und die Quelle verweist auf die NAT-Zuordnung, um zu ermitteln, an welche interne IP-Adresse die Antwort zurückgegeben werden soll.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern zu einer vorhandenen Topologie finden Sie in der Edgeserver-Bereitstellungsdokumentation unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


