---
title: Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Mithilfe dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) für den Edge-Server angeben.
ms.openlocfilehash: b54fae5ce536e1f859c4c05059b18b5e5067af7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873326"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Hinzufügen der internen IP-Adresse zum Edgecomputer – 2010

Mithilfe dieser Seite können Sie die interne IP-Adresse und den internen vollqualifizierten Domänennamen (FQDN) für den Edge-Server angeben.

- Geben Sie im Feld **interne IPv4-Adresse**die IP-Adresse des Edgeservers, den Sie dem Pool hinzufügen möchten.

- Geben Sie Sie in **Interner FQDN**den vollqualifizierten Domänennamen (FQDN) des Edgeservers, den Sie dem Pool hinzufügen möchten.

Der FQDN, die Sie angeben, muss mit den Namen des Computers identisch sein, die auf dem Server konfiguriert ist. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs. Daher müssen Sie ein Suffix Domain Name System (DNS) konfigurieren, auf den Namen des Computers, der als ein Edge-Server bereitgestellt werden, die nicht Mitglied einer Domäne ist. Weitere Informationen zum Hinzufügen einer DNS-Suffix an einen Computernamen finden Sie unter [Konfigurieren von DNS für die Edgeunterstützung](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


