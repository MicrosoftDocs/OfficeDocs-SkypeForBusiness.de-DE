---
title: Entfernen der Zuordnung des Archiving server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie einen Archivierungsserver entfernen möchten, müssen Sie ändern oder löschen die Abhängigkeit von der neu zugeordnete Front-End-Pool Front-End-Server, Survivable Branch Appliance und Survivable Branch Server. Sie bearbeiten die Eigenschaften des Front-End-Pools, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit deaktivieren, und Sie den Server im Topologie-Generator löschen, werden Sie benachrichtigt, dass das Store-Objekt zugeordnete Datenbank im Topologie-Generator ebenfalls gelöscht werden.
ms.openlocfilehash: 7438145f5822de8f95e881f114983fdb9351d4b9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028873"
---
# <a name="remove-the-archiving-server-association"></a>Entfernen der Zuordnung des Archiving server

Wenn Sie einen Archivierungsserver entfernen möchten, müssen Sie ändern oder löschen die Abhängigkeit von den zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server. Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit deaktivieren und den Server im Topologie-Generator löschen, werden Sie benachrichtigt, dass das Store-Objekt zugeordnete Datenbank im Topologie-Generator ebenfalls gelöscht werden.
  
### <a name="to-remove-the-archiving-server-association"></a>So entfernen Sie die Archivierungsserver-Zuordnung

1. Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.
    
2. Navigieren Sie zu der Knoten legacy installieren.
    
3. Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigniederlassungen**, je nachdem, wo der Archivierungsserver definiert ist.
    
4. Wenn Sie einen Survivable Branch Server zugeordnete verfügen, erweitern Sie **Zweigniederlassungen**, erweitern Sie Namen des Zweigniederlassung und dann **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** auf der Benutzeroberfläche gilt für Survivable Branch Server- und Survivable Branch Appliance. 
  
5. Mit der rechten Maustaste die Pools, Server oder Gerät, das den Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. **Bearbeiten von Eigenschaften**unter **Allgemein** > **Zuordnungen**, deaktivieren Sie das Kontrollkästchen **Archivierungsserver zuordnen** , und klicken Sie dann auf **OK**.
    
7. Wiederholen Sie den vorherigen Schritt für jeden Pool, Server oder Geräte, die zu entfernende Archivierungsserver zugeordnet.
    
8. Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen**.
    
9. **Abhängige Speicher löschen**klicken Sie auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann die Skype für Business Server-Bereitstellungs-Assistenten aus, je nach Bedarf. 
    

