---
title: Hinzufügen von Edge-Server-NAT-IP-
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: Die öffentliche IP-Adresse ist die IP-Adresse, die von der Netzwerkadressübersetzung (NAT) verwendet wird. Die IP-Adresse muss öffentlich routingfähig sein. Dies ist erforderlich, da Sie die externe IP-Adresse für diese Kante ausgewählt haben, den Pool von NAT-Option auf der Seite Select Features dieses Assistenten übersetzt wird.
ms.openlocfilehash: 034367d42d4ef698315f128e840123295e8fd694
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257479"
---
# <a name="add-edge-server-nat-ip"></a>Hinzufügen von Edge-Server-NAT-IP-

Die öffentliche IP-Adresse ist die IP-Adresse, die von der Netzwerkadressübersetzung (NAT) verwendet wird. Die IP-Adresse muss öffentlich routingfähig sein. Dies ist erforderlich, da Sie **die externe IP-Adresse für diesen edgepool wird von NAT übersetzt** Option auf der Seite **Features auswählen** des Assistenten ausgewählt haben.

> [!NOTE]
> Netzwerkadressübersetzung (NAT) ermöglicht es Clients oder Server in einem privaten Netzwerk (beispielsweise die 192.168.0.0 Bereich) über das öffentliche Internet-Netzwerke mit Systemen in remote-Netzwerken kommunizieren. NAT funktioniert, indem Sie eine einzelne öffentliche IP-Adresse für eine externe Schnittstelle verwenden und eine öffentliche IP-Adresse interne IP-Adressen zugeordnet. NAT-Zuordnung ordnet eine interne Adresse die externe öffentliche IP-Adresse zu. Das Remotesystem erhält nur die öffentliche Adresse der Quelle. Das Remotesystem reagiert auf die Datenquelle, und die Datenquelle bezieht sich auf die NAT-Zuordnung zu bestimmen, welche interne IP-Adresse, der die Antwort an zurückgegeben werden sollen.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edge-Servern zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in der Dokumentation zur Bereitstellung der Edge-Server.


