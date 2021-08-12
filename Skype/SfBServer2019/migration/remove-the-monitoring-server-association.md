---
title: Entfernen der Zuordnung der Überwachungsserver
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
description: Um den Überwachungsserver zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder löschen. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: 8e4c4b08c6126f6ac2c03d66e9ddcfe921b79850e704c54c65d6951c1449aa9f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280400"
---
# <a name="remove-the-monitoring-server-association"></a>Entfernen der Zuordnung der Überwachungsserver

Um den Überwachungsserver zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder löschen. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.
  
### <a name="to-remove-the-monitoring-server-association"></a>So entfernen Sie die Monitoring Server-Zuordnung

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator.
    
2. Navigieren Sie zum Legacy-Installationsknoten.
    
3. Erweitern Sie im Topologie-Generator **Enterprise Edition Front-End-Pools,** **Standard Edition Front-End-Server** oder **Zweigstellenstandorte,** je nachdem, wo der Überwachungsserver definiert ist.
    
4. Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellen,** den Namen des Zweigstellenstandorts und dann **Survivable Branch Appliances.**
    
    > [!NOTE]
    > **Survivable Branch Appliances** in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance. 
  
5. Klicken Sie mit der rechten Maustaste auf den Pool, Server oder das Gerät, das dem Überwachungsserver zugeordnet ist, und klicken Sie dann auf **"Eigenschaften bearbeiten".**
    
6. Deaktivieren Sie unter "Eigenschaften **bearbeiten"** unter **"Allgemeine**  >  **Zuordnungen"** das Kontrollkästchen **"Monitoring Server zuordnen",** und klicken Sie dann auf **"OK".**
    
7. Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Monitoring Server zugeordnet sind.
    
8. Klicken Sie mit der rechten Maustaste auf den Überwachungsserver, und klicken Sie dann auf **"Löschen".** 
    
9. Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Skype for Business Server Bereitstellungs-Assistenten nach Bedarf aus. 
    

