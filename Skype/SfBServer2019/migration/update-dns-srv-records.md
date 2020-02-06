---
title: Aktualisieren von DNS SRV-Einträgen
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
description: Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812773"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie als Mitglied der Gruppe Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe am Server oder in der Domäne angemeldet sein.
  
In diesem Thema wird beschrieben, wie Sie die DNS-Einträge (Domain Name System) nach der Migration zu Skype for Business Server 2019 aktualisieren. Nachdem alle Benutzer in Skype for Business Server 2019 verschoben wurden, aber bevor der Legacy Pool oder Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren. Bei diesem Verfahren wird davon ausgegangen, dass Ihr interner DNS Zonen für Ihre SIP-Benutzerdomänen aufweist.
  
## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1. Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur ihrer SIP-Domäne **Forward-Lookupzonen**, erweitern Sie die SIP-Domäne, in der Skype for Business Server 2019 installiert ist, und navigieren Sie zur **_tcp** -Einstellung. 
    
3. Klicken Sie im rechten Bereich mit der rechten Maustaste auf **_sipinternaltls** , und wählen Sie **Eigenschaften**aus.
    
4. Aktualisieren Sie im Host, der **diesen Dienst anbietet**, den FQDN des Hosts so, dass er auf den Skype for Business Server 2019-Pool verweist.
    
5. Klicken Sie auf **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>So überprüfen Sie, ob der FQDN des Front-End-Pools oder des Standard Edition-Servers aufgelöst werden kann

1. Melden Sie sich bei einem Clientcomputer in der Domäne an.
    
2. Klicken Sie auf  **Start ** und dann auf  **Ausführen**.
    
3. Geben Sie im Feld **Öffnen** den Befehl cmd ein, und klicken Sie dann auf **OK**.
    
4. Geben Sie an der Eingabeaufforderung nslookup _ \<-FQDN des Front-End\> -Pools_ oder _ \<den FQDN des Standard\>Edition-Servers_ein, und drücken Sie dann die EINGABETASTE.
    
5. Überprüfen Sie, ob Sie eine Antwort erhalten, die in die entsprechende IP-Adresse für den FQDN aufgelöst wird.
    

