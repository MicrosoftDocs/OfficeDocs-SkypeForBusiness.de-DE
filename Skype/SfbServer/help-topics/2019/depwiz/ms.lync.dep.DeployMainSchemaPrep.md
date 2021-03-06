---
title: Vorbereiten des Schemas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Vorbereiten des Schemas für Active Directory Domain Services führen Sie den Schritt "Schema vorbereiten" im Skype for Business Server-Bereitstellungs-Assistenten aus. Klicken Sie auf Ausführen, um die Schemavorbereitung zu beginnen.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833775"
---
# <a name="prepare-schema"></a>Vorbereiten des Schemas
 
Zum Vorbereiten des Schemas für Active Directory Domain Services führen Sie den Schritt "Schema vorbereiten" im Skype for Business Server-Bereitstellungs-Assistenten aus. Klicken Sie auf **Ausführen**, um die Schemavorbereitung zu beginnen. Im Schritt "Schema vorbereiten" werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis "\Programme\Skype for Business Server 2019\Deployment\Setup" auf dem System gelesen, auf dem der Bereitstellungsassistent ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis "\Support\Schema" zur Verfügung. Der Schritt "Schema vorbereiten" dient zum Erweitern des Schemas und Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
  
> [!IMPORTANT]
> Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen "Schema-Admins" und "Organisations-Admins" angemeldet sein. 
  
Klassen und Attribute werden hinzugefügt, um das Active Directory Domain Services-Schema zur Unterstützung von Skype for Business Server-Server-, Dienst- und Benutzerobjekten zu erweitern. Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen. 
  
> [!CAUTION]
> Das Erweitern des Schemas ist nicht umkehrbar. Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist. Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig. Sie sollten eine Sicherung des Schemamasterdomänencontrollers und eine vollständige Sicherung von Active Directory ausführen. 
  
So führen Sie eine Sicherung des Schemamasterdomänencontrollers und eine vollständige Sicherung von Active Directory durch:
  
1. Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.
    
2. Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.
    
3. Erweitern Sie das Schema.
    
4. Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk, und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.
    
5. Stellen Sie im unwahrscheinlichen Fall eines Schemaerweiterungsfehlers den Systemstatus des Domänencontrollers und von Active Directory mithilfe der zuvor erstellten Systemstatussicherung wieder her.
    
> [!NOTE]
> Wenn Sie die vom Skype for Business Server-Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen müssen, finden Sie die Dateien auf dem Computer, auf dem der Bereitstellungsassistent ausgeführt wurde, im Verzeichnis "Benutzer" des Active Directory-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne Contoso.net angemeldet hat, befinden sich die Protokolldateien unter: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

