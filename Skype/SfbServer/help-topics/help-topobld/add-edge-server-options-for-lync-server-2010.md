---
title: Hinzufügen der Edgeserveroptionen für Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Sie definieren einen neuen Edgeserver oder Edge-Pool und bieten die Möglichkeit, Features für den neuen Server oder Pool zu definieren. Die Optionen, die Sie auswählen können, sind:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289994"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Hinzufügen der Edgeserveroptionen für Lync Server 2010

Sie definieren einen neuen Edgeserver oder Edge-Pool und bieten die Möglichkeit, Features für den neuen Server oder Pool zu definieren. Die Optionen, die Sie auswählen können, sind:

- **Verwenden eines einzelnen FQDN und einer IP-Adresse**: Aktivieren Sie das Kontrollkästchen, um ein einzelnes IPv4 oder IPv6 zu verwenden (wenn Sie sowohl IPv4 als auch IPv6 verwenden, müssen Sie einen der einzelnen IP-Adresstypen) und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die Schnittstellen für externe Edge definieren.

    > [!IMPORTANT]
    > Wenn Sie diese Option auswählen, verwenden Sie nur eine IP-Adresse oder eine IPv4-und eine IPv6-Adresse, aber Sie müssen jeder Edge-Schnittstelle unterschiedliche Portnummern zuweisen.

- **Föderation aktivieren (Port 5061)**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie mit anderen SIP-Föderationen, Anbietern oder gehosteten angeboten zusammen kommen, die das Session Initiation Protocol (SIP) verwenden.

- **Die externe IP-Adresse dieses Edge-Pools wird von NAT übersetzt**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie private IP-Adressen für die externen Edge-Schnittstellen verwenden und ein NAT-Gerät (Network Address Translation) bereitstellen, um den Edge-Server oder den Edge-Pool logisch zu platzieren. hinter.

## <a name="see-also"></a>Siehe auch

[Planen des Zugriffs für externe Benutzer](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Bereitstellen des Zugriffs externer Benutzer](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
