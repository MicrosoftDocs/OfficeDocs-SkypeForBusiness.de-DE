---
title: Entfernen der Zuordnung des Archivierungsservers
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
description: Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder löschen. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.
ms.openlocfilehash: 6265642a45b891180e53d3b00d39a9053b663a434aaa1a4a26e92b619dfba257
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340331"
---
# <a name="remove-the-archiving-server-association"></a>Entfernen der Zuordnung des Archivierungsservers

Um einen Archivierungsserver zu entfernen, müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch Appliance und Survivable Branch Server ändern oder löschen. Sie bearbeiten die Eigenschaften des Front-End-Pools, des Front-End-Servers, der Survivable Branch Appliance und des Survivable Branch-Servers, um die Abhängigkeit zu entfernen. Nachdem Sie die Abhängigkeit gelöscht und den Server im Topologie-Generator gelöscht haben, werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.
  
### <a name="to-remove-the-archiving-server-association"></a>So entfernen Sie die Zuordnung des Archivierungsservers

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator.
    
2. Navigieren Sie zum Legacyinstallationsknoten.
    
3. Erweitern Sie im Topologie-Generator **Enterprise Edition Front-End-Pools,** **Standard Edition Front-End-Server** oder **Zweigstellenstandorte,** je nachdem, wo der Archivierungsserver definiert ist.
    
4. Wenn Sie Survivable Branch Server zugeordnet haben, erweitern Sie **Zweigstellen,** den Namen des Zweigstellenstandorts und dann **Survivable Branch Appliances.**
    
    > [!NOTE]
    > **Survivable Branch Appliances** in der Benutzeroberfläche gelten sowohl für Survivable Branch Server als auch für Survivable Branch Appliance. 
  
5. Klicken Sie mit der rechten Maustaste auf den Pool, Server oder das Gerät, das dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **"Eigenschaften bearbeiten".**
    
6. Deaktivieren Sie unter **"Allgemeine** Zuordnungen" unter **"Eigenschaften bearbeiten"**  >  das Kontrollkästchen **"Archivierungsserver zuordnen",** und klicken Sie dann auf **"OK".**
    
7. Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Archivierungsserver zugeordnet sind, den Sie entfernen möchten.
    
8. Klicken Sie mit der rechten Maustaste auf den Archivierungsserver, und klicken Sie dann auf **"Löschen".**
    
9. Klicken Sie unter **Abhängige Speicher löschen** auf **OK**.
    
10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Skype for Business Server Bereitstellungs-Assistenten nach Bedarf aus. 
    

