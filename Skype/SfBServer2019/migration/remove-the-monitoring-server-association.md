---
title: Entfernen der Zuordnung der Monitoring Server
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
description: Um die Monitoring Server zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753417"
---
# <a name="remove-the-monitoring-server-association"></a>Entfernen der Zuordnung der Monitoring Server

Zum Entfernen des Monitoring Server müssen Sie die Abhängigkeit von der zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
  
### <a name="to-remove-the-monitoring-server-association"></a>So entfernen Sie die Monitoring Server-Zuordnung

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie zum Knoten Legacy Installationen.
    
3. Erweitern Sie im Topologie-Generator die **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**, je nachdem, wo die Monitoring Server definiert ist.
    
4. Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellenstandorte**, erweitern Sie den Namen der Zweigstelle, und erweitern Sie dann **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable Branch Appliances** in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance. 
  
5. Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, das dem Monitoring Server zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemeine**  >  **Zuordnungen**das Kontrollkästchen **Monitoring Server zuordnen** , und klicken Sie dann auf **OK**.
    
7. Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Monitoring Server zugeordnet sind.
    
8. Klicken Sie mit der rechten Maustaste auf den Monitoring Server, und klicken Sie dann auf **Löschen**. 
    
9. Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Assistenten für die Skype for Business Server-Bereitstellung bei Bedarf aus. 
    

