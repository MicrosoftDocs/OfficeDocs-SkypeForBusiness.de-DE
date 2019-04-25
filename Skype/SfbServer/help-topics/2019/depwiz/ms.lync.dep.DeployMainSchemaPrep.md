---
title: Vorbereiten des Schemas
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Führen Sie zur Vorbereitung des Schemas für Active Directory Domain Services im Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten auf. Klicken Sie auf Ausführen, um mit der Schemavorbereitung zu beginnen.
ms.openlocfilehash: fc9981e5a6f298d4d7697b00cde2798dd0b859ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216143"
---
# <a name="prepare-schema"></a>Vorbereiten des Schemas
 
Führen Sie zur Vorbereitung des Schemas für Active Directory Domain Services im Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten auf. Klicken Sie auf **Ausführen**, um mit der Schemavorbereitung zu beginnen. Der Schritt Schema vorbereiten liest das angegebene Schema Definitionsdateien in der \Program Files\Skype für Business Server 2019\Deployment\Setup Verzeichnis auf dem System, das den Bereitstellungs-Assistenten ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis „\Support\Schema“ zur Verfügung. Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
  
> [!IMPORTANT]
> Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen „Schema-Admins“ und „Organisations-Admins“ angemeldet sein. 
  
Zum Erweitern des Schemas Active Directory Domain Services zur Unterstützung von Skype für Business Server Server-Dienst und User-Objekte werden Klassen und Attribute hinzugefügt. Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen. 
  
> [!CAUTION]
> Das Erweitern des Schemas ist nicht umkehrbar. Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist. Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig. Sie sollten eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung von Active Directory ausführen. 
  
So führen Sie eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung der Active Directory aus:
  
1. Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.
    
2. Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.
    
3. Erweitern Sie das Schema.
    
4. Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.
    
5. Wiederherstellen von in unwahrscheinlichen bei einem den Systemen Zustand des Domänencontrollers und Active Directory anhand der Systemstatus-Sicherung, die Sie zuvor erstellt haben.
    
> [!NOTE]
> Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, finden Sie die Dateien auf dem Computer, auf dem Bereitstellungs-Assistenten ausgeführt wurde, im Verzeichnis Benutzer der Active Directory-Benutzer, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

