---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor dem Bereitstellen des pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754055"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung

Vor dem Bereitstellen des pilotpools müssen Sie den DNS-Host A-Einträge für den Pilot Pool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
  
### <a name="to-configure-dns-host-a-records"></a>So konfigurieren Sie DNS-Hosteinträge (A)

1. Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Skype for Business Server 2019 installiert wird.
    
3. Klicken Sie auf **Neuer Host (A oder AAAA)**.
    
4. Klicken Sie auf **Name**, geben Sie den Hostnamen für den Skype for Business Server Pool 2019 (der Domänen Name wird von der Zone angenommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).
    
5. Klicken Sie auf **IP-Adresse**, und geben Sie dann die IP-Adresse für die Front-End-Pool ein.
    
6. Klicken Sie auf **Host hinzufügen** und dann auf **OK**. 
    
7. Klicken Sie abschließend auf **Fertig**.
    

