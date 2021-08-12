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
ms.openlocfilehash: 0c3454bd4fbf8ecdc28730da378357e9d50efec3c12ba5b3926abb61010979ab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327051"
---
# <a name="update-dns-srv-records"></a>Aktualisieren von DNS SRV-Einträgen

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.
  
In diesem Thema wird beschrieben, wie Die DNS-Einträge (Domain Name System) nach der Migration zu Skype for Business Server 2019 aktualisiert werden. Nachdem alle Benutzer zu Skype for Business Server 2019 verschoben wurden, aber bevor der Legacypool oder Director außer Betrieb genommen wird, müssen Sie die DNS-SRV-Einträge in Ihrem internen DNS für jede SIP-Domäne aktualisieren. Für diese Vorgehensweise wird davon ausgegangen, dass das interne DNS Zonen für die SIP-Benutzerdomänen aufweist.
  
## <a name="to-configure-a-dns-srv-record"></a>So konfigurieren Sie einen DNS-SRV-Eintrag

1. Klicken Sie auf dem DNS-Server auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.
    
2. Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne **Forward-Lookupzonen,** erweitern Sie die SIP-Domäne, in der Skype for Business Server 2019 installiert ist, und navigieren Sie zur **Einstellung _tcp.** 
    
3. Klicken Sie im rechten Bereich mit der rechten Maustaste auf **_sipinternaltls,** und wählen Sie **"Eigenschaften"** aus.
    
4. Aktualisieren Sie im Host, der **diesen Dienst anbietet,** den Host-FQDN so, dass er auf den Skype for Business Server 2019-Pool verweist.
    
5. Klicken Sie auf **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>So überprüfen Sie, ob der FQDN des Front-End-Pools oder Standard Edition-Servers aufgelöst werden kann

1. Melden Sie sich an einem Clientcomputer in der Domäne an.
    
2. Klicken Sie auf **Start** und dann auf **Ausführen**.
    
3. Geben Sie im **Feld "Öffnen"** cmd ein, und klicken Sie dann auf **"OK".**
    
4. Geben Sie an der Eingabeaufforderung "nslookup" _\<FQDN of the Front End pool\>_ oder  _\<FQDN of the Standard Edition server\>_ ", und drücken Sie dann die EINGABETASTE.
    
5. Stellen Sie sicher, dass eine Antwort zurückgegeben wird, in welcher der FQDN in die zugehörige IP-Adresse aufgelöst wurde.
    

