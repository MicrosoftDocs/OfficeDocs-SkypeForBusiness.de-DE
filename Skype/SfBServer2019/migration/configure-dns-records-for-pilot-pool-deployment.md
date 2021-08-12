---
title: Konfigurieren von DNS-Einträgen für die Bereitstellung von Pilotpools
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
description: Vor der Bereitstellung des Pilotpools müssen Sie die DNS-Host-A-Einträge für den Pilotpool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
ms.openlocfilehash: 270b0bda7da679cb0c75e9a99e10a898dcee6ac70413ce276abfe19ba1eb2231
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337833"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Bereitstellung von Pilotpools

Vor der Bereitstellung des Pilotpools müssen Sie die DNS-Host-A-Einträge für den Pilotpool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
  
### <a name="to-configure-dns-host-a-records"></a>So konfigurieren Sie DNS-Hosteinträge (A)

1. Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward LookupZonen,** und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Skype for Business Server 2019 installiert wird.
    
3. Klicken Sie auf **Neuer Host (A oder AAAA)**.
    
4. Klicken Sie auf **"Name",** geben Sie den Hostnamen für den Skype for Business Server 2019-Pool ein (der Domänenname wird aus der Zone angenommen, in der der Datensatz definiert ist und nicht als Teil des A-Eintrags eingegeben werden muss).
    
5. Klicken Sie auf **"IP-Adresse",** und geben Sie dann die IP-Adresse für den Front-End-Pool ein.
    
6. Klicken Sie auf **Host hinzufügen** und dann auf **OK**. 
    
7. Klicken Sie abschließend auf **Fertig**.
    

