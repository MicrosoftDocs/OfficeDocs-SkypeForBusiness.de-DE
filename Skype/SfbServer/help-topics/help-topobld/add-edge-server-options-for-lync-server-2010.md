---
title: Hinzufügen von Edgeserveroptionen für Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definieren Sie einen neuen Edge-Server oder einen Edge-Pool und die Möglichkeit, Features für den neuen Server oder Pool definieren angezeigt werden. Die Optionen, die Sie auswählen können, sind:'
ms.openlocfilehash: d42a7cf7c926e8a879a148c3e4dcb7cc7624d23e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257346"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Hinzufügen von Edgeserveroptionen für Lync Server 2010

Definieren Sie einen neuen Edge-Server oder einen Edge-Pool und die Möglichkeit, Features für den neuen Server oder Pool definieren angezeigt werden. Die Optionen, die Sie auswählen können, sind:

- **Verwenden Sie eine einzelne FQDN und IP-Adresse**: Aktivieren Sie das Kontrollkästchen mit einer einzelnen IPv4 oder IPv6 (Wenn Sie sowohl IPv4 als auch IPv6 verwenden können, müssen Sie über die einzelnen IP-Adresse definieren) Adresse und den vollqualifizierten Domänennamen (FQDN) für die externe Edge-Schnittstellen.

    > [!IMPORTANT]
    > Wenn Sie diese Option auswählen, verwenden Sie nur eine IP-Adresse oder eine IPv4- und IPv6 eine, jedoch müssen Sie jede edgeschnittstelle unterschiedliche Portnummern zuweisen.

- **Partnerverbund aktivieren (Port 5061)**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie einen Partnerverbund mit anderen SIP partnerverbunden, Anbietern oder gehosteten angeboten, die das Session Initiation Protocol (SIP) verwenden.

- **Die externe IP-Adresse für diesen edgepool wird von NAT übersetzt**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie private IP-Adressen für die externen edgeschnittstellen verwenden und werden ein Gerät Network Address Translation (NAT), zum Platzieren der Edge-Server oder logisch Edge-Pool bereitstellen hinter.

## <a name="see-also"></a>Siehe auch

[Planen des Zugriffs externer Benutzer](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Bereitstellen von Zugriff durch externe Benutzer](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)