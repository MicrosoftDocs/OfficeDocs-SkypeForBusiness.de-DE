---
title: Aktualisieren von DNS SRV-Einträgen
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
description: Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753267"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
  
In diesem Thema wird beschrieben, wie Sie die Domain Name System (DNS) Datensätze nach der Migration zu Skype for Business Server 2019 aktualisieren. Nachdem alle Benutzer auf Skype for Business Server 2019 verschoben wurden, aber bevor der ältere Pool oder Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.
  
## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1. Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne den Knoten **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der Skype for Business Server 2019 installiert ist, und navigieren Sie zur Einstellung **_tcp** . 
    
3. Klicken Sie im rechten Bereich mit der rechten Maustaste auf **_sipinternaltls** , und wählen Sie **Eigenschaften**aus.
    
4. Aktualisieren Sie unter Host, der **diesen Dienst anbietet**den Host-FQDN so, dass er auf den Skype for Business Server 2019-Pool zeigt.
    
5. Klicken Sie auf **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann

1. Melden Sie sich an einem Clientcomputer in der Domäne an.
    
2. Klicken Sie auf **Start** und dann auf **Ausführen**.
    
3. Geben Sie im Feld **Öffnen** den Befehl cmd ein, und klicken Sie dann auf **OK**.
    
4. Geben Sie an der Eingabeaufforderung nslookup _\<FQDN of the Front End pool\>_ oder _\<FQDN of the Standard Edition server\>_ ein, und drücken Sie dann die EINGABETASTE.
    
5. Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.
    

