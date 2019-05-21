---
title: Entfernen der Zuordnung der Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301097"
---
# <a name="remove-the-monitoring-server-association"></a>Entfernen der Zuordnung der Monitoring Server

Zum Entfernen des Überwachungsservers müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
  
### <a name="to-remove-the-monitoring-server-association"></a>So entfernen Sie die Monitoring Server-Zuordnung

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy Installationen.
    
3. Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**, je nachdem, wo der Monitoring Server definiert ist.
    
4. Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable-Branch** -Appliances auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance. 
  
5. Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Überwachungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemeine** > **Zuordnungen**das Kontrollkästchen **Überwachungs Server zuordnen** , und klicken Sie dann auf **OK**.
    
7. Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Überwachungsserver zugeordnet sind.
    
8. Klicken Sie mit der rechten Maustaste auf den Überwachungs Server, und klicken Sie dann auf **Löschen**. 
    
9. Klicken Sie unter **abhängige Speicher löschen**auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Bereitstellungs-Assistenten von Skype for Business Server nach Bedarf aus. 
    

