---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vor der Bereitstellung des pilotpools müssen Sie den DNS-Host einen Eintrag für den Pilot Pool aktualisieren. Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813853"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung

Bevor Sie den Pilot Pool bereitstellen, müssen Sie den DNS-Host einen Eintrag für den Pilot Pool aktualisieren. Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.
  
### <a name="to-configure-dns-host-a-records"></a>So konfigurieren Sie DNS-Host A-Einträge

1. Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur für Ihre Domäne **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Skype for Business Server 2019 installiert wird.
    
3. Klicken Sie auf **neuer Host (A oder AAAA)**.
    
4. Klicken Sie auf **Name**, geben Sie den Hostnamen für den Skype for Business Server 2019-Pool ein (der Domänen Name wird aus der Zone übernommen, in der der Datensatz definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).
    
5. Klicken Sie auf **IP-Adresse**, und geben Sie dann die IP-Adresse für den Front-End-Pool ein.
    
6. Klicken Sie auf **Host hinzufügen**, und klicken Sie dann auf **OK**. 
    
7. Wenn Sie fertig sind, klicken Sie auf **Fertig**.
    

