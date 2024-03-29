---
title: Vorbereiten des Schemas
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Um das Schema für Active Directory Domain Services vorzubereiten, führen Sie den Schritt "Schema vorbereiten" im Bereitstellungs-Assistenten für Skype for Business Server aus. Klicken Sie auf Ausführen, um die Schemavorbereitung zu beginnen.
ms.openlocfilehash: 43496aa2b9d3ec40f4c79aed0e20824ee7ef1494
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404327"
---
# <a name="prepare-schema"></a>Vorbereiten des Schemas
 
Um das Schema für Active Directory Domain Services vorzubereiten, führen Sie den Schritt "Schema vorbereiten" im Bereitstellungs-Assistenten für Skype for Business Server aus. Klicken Sie auf **Ausführen**, um die Schemavorbereitung zu beginnen. Im Schritt "Schema vorbereiten" werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis "\Programme\Skype for Business Server 2019\Bereitstellung\Setup" auf dem System gelesen, auf dem der Bereitstellungs-Assistent ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis "\Support\Schema" zur Verfügung. Der Schritt "Schema vorbereiten" dient zum Erweitern des Schemas und Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
  
> [!IMPORTANT]
> Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen "Schema-Admins" und "Organisations-Admins" angemeldet sein. 
  
Klassen und Attribute werden hinzugefügt, um das Active Directory Domain Services-Schema so zu erweitern, dass Skype for Business Server Server-, Dienst- und Benutzerobjekte unterstützt werden. Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen. 
  
> [!CAUTION]
> Das Erweitern des Schemas ist nicht umkehrbar. Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist. Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig. Sie sollten eine Sicherung des Schemamaster-Domänencontrollers und eine vollständige Sicherung von Active Directory durchführen. 
  
So führen Sie eine Sicherung des Schemamaster-Domänencontrollers und eine vollständige Sicherung von Active Directory durch:
  
1. Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.
    
2. Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.
    
3. Erweitern Sie das Schema.
    
4. Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk, und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.
    
5. Stellen Sie im unwahrscheinlichen Fall eines Fehlers bei einer Schemaerweiterung den Systemstatus des Domänencontrollers und active Directory mithilfe der zuvor erstellten Systemstatussicherung wieder her.
    
> [!NOTE]
> Wenn Sie die Vom Skype for Business Server Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie die Dateien auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

