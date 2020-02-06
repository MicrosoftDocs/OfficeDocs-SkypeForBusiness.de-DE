---
title: Entfernen der Zuordnung des Archivierungsservers
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
description: Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable-Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: 7b6e35131005866feed04a4e9b68c43558b6c1e1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812973"
---
# <a name="remove-the-archiving-server-association"></a>Entfernen der Zuordnung des Archivierungsservers

Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit auf dem zugehörigen Front-End-Pool, dem Front-End-Server, der Survivable Branch-Appliance und dem Überlebenden Branch-Server ändern oder deaktivieren. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch-Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicher Objekt im Topologie-Generator ebenfalls gelöscht wird.
  
### <a name="to-remove-the-archiving-server-association"></a>So entfernen Sie die Zuordnung des Archivierungsservers

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie zum Legacy Installations Knoten.
    
3. Erweitern Sie im Topologie-Generator **Enterprise Edition-Front-End-Pools**, **Standard Edition-Front-End-Server**oder **Zweigstellenstandorte**, je nachdem, wo der Archivierungs Server definiert ist.
    
4. Wenn Sie über einen Überlebenden Branch Server verfügen, erweitern Sie **Zweigstellen**, erweitern Sie den Namen der Verzweigungs Website, und erweitern Sie dann **Survivable Branch Appliances**.
    
    > [!NOTE]
    > **Survivable-Branch-Appliances** auf der Benutzeroberfläche gelten sowohl für Survival Branch-Server als auch für Survivable Branch-Appliance. 
  
5. Klicken Sie mit der rechten Maustaste auf den Pool, den Server oder das Gerät, der dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
6. Deaktivieren Sie in **Eigenschaften bearbeiten**unter **Allgemeine** > **Zuordnungen**das Kontrollkästchen **Archivierungs Server zuordnen** , und klicken Sie dann auf **OK**.
    
7. Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Archivierungsserver zugeordnet sind, den Sie entfernen möchten.
    
8. Klicken Sie mit der rechten Maustaste auf den Archivierungs Server, und klicken Sie dann auf **Löschen**.
    
9. Klicken Sie unter **abhängige Speicher löschen**auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Bereitstellungs-Assistenten von Skype for Business Server nach Bedarf aus. 
    

