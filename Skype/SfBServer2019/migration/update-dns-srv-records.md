---
title: Aktualisieren von DNS SRV-Einträgen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872724"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

Zum erfolgreichen Durchführen dieses Verfahrens sollten Sie auf dem Server oder Domäne als Mitglied der Gruppe Domänen-Admins oder ein Mitglied der Gruppe "DnsAdmins" angemeldet sein.
  
In diesem Thema wird beschrieben, wie die Datensätze Domain Name System (DNS) nach der Migration zu Skype für Business Server 2019 aktualisieren. Nachdem alle Benutzer in Skype für Business Server 2019 verschoben wurden, jedoch vor dem vorversionspool oder dem Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge im internen DNS für jede SIP-Domäne aktualisieren. In diesem Verfahren wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.
  
## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1. Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.
    
2. In der Konsolenstruktur für Ihre SIP-Domäne erweitern Sie **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in welche Skype für Business Server 2019 installiert ist, und navigieren Sie zur **_tcp** -Einstellung. 
    
3. Klicken Sie im rechten Bereich mit der rechten Maustaste **_sipinternaltls ein** , und wählen Sie **Eigenschaften**aus.
    
4. Aktualisieren Sie unter **Host, der diesen Dienst anbietet**den Host FQDN So zeigen Sie auf die Skype für Business Server 2019 Pool ein.
    
5. Klicken Sie auf **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Um sicherzustellen, dass der FQDN des Front-End-Pool oder Standard Edition-Servers aufgelöst werden kann

1. Melden Sie sich an einem Clientcomputer in der Domäne.
    
2. Klicken Sie auf  **Start ** und dann auf  **Ausführen**.
    
3. Klicken Sie im Feld **Öffnen** Geben Sie cmd ein, und klicken Sie dann auf **OK**.
    
4. Geben Sie an der Eingabeaufforderung Nslookup _ \<FQDN des Front-End-Pools\> _ oder _ \<FQDN des Standard Edition-Servers\>_, und drücken Sie dann die EINGABETASTE.
    
5. Stellen Sie sicher, dass Sie eine Antwort erhalten, die für den FQDN in die entsprechenden IP-Adresse auflöst.
    

