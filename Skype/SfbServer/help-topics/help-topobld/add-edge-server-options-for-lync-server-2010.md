---
title: Hinzufügen der Edgeserveroptionen für Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Sie definieren einen neuen Edgeserver oder Edgepool und haben die Möglichkeit, Features für den neuen Server oder Pool zu definieren. Sie können unter den folgenden Optionen wählen:'
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835515"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Hinzufügen der Edgeserveroptionen für Lync Server 2010

Sie definieren einen neuen Edgeserver oder Edgepool und haben die Möglichkeit, Features für den neuen Server oder Pool zu definieren. Sie können unter den folgenden Optionen wählen:

- **Einen einzelnen FQDN und eine einzelne IP-Adresse verwenden**: Aktivieren Sie das Kontrollkästchen, um eine einzelne IPv4- oder IPv6-Adresse (bei gleichzeitiger Verwendung von IPv4 und IPv6 müssen Sie jeweils einen IP-Adresstyp definieren) und einen vollqualifizierten Domänennamen (FQDN) für die externen Schnittstellen des Edgeservers zu verwenden.

    > [!IMPORTANT]
    > Bei Auswahl dieser Option verwenden Sie nur eine IP-Adresse bzw. eine IPv4- und eine IPv6-Adresse, aber Sie müssen jeder Edgeschnittstelle unterschiedliche Portnummern zuweisen.

- **Partnerverbund aktivieren (Port 5061)**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie einen Partnerverbund mit anderen SIP-Partnerverbunden, Anbietern oder gehosteten Angeboten einrichten möchten, die das Session Initiation Protocol (SIP) verwenden.

- Die externe IP-Adresse dieses **Edgepools** wird von NAT übersetzt: Aktivieren Sie dieses Kontrollkästchen, wenn Sie private IP-Adressen für die externen Edgeschnittstellen verwenden und ein Netzwerkadressenübersetzungsgerät (Network Address Translation, NAT) bereitstellen, um den Edgeserver oder Edgepool logisch hinter sich zu platzieren.

## <a name="see-also"></a>Siehe auch

[Planen des Zugriffs externer Benutzer](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Bereitstellen des Zugriffs durch externe Benutzer](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
