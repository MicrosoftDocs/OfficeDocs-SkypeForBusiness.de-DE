---
title: Vorbereiten des Schemas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Wenn Sie das Schema für Active Directory-Domänendienste vorbereiten möchten, führen Sie den Schritt "Schema vorbereiten" im Skype for Business Server-Bereitstellungs-Assistenten aus. Klicken Sie auf Ausführen, um mit der Schemavorbereitung zu beginnen. Der Schritt "Schema vorbereiten" liest die angegebenen Schemadefinitionsdateien im Verzeichnis/Programm Files/Microsoft lync Server 2013/Deployment/Setup auf dem System ein, auf dem der Bereitstellungs-Assistent ausgeführt wird. Diese Dateien sind auch auf den Installationsmedien im Support/Schema-Verzeichnis verfügbar. Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
ms.openlocfilehash: 12b4bcbe93bd1ed55e0a2c2c1a133db41b30cd00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292123"
---
# <a name="prepare-schema"></a>Vorbereiten des Schemas
 
Wenn Sie das Schema für Active Directory-Domänendienste vorbereiten möchten, führen Sie den Schritt "Schema vorbereiten" im Skype for Business Server-Bereitstellungs-Assistenten aus. Klicken Sie auf **Ausführen**, um mit der Schemavorbereitung zu beginnen. Im Schritt „Schema vorbereiten“ werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis „\Programme\Microsoft Lync Server 2013\Deployment\Setup“ des Systems gelesen, auf dem der Bereitstellungs-Assistent ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis „\Support\Schema“ zur Verfügung. Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
  
> [!IMPORTANT]
> Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen „Schema-Admins“ und „Organisations-Admins“ angemeldet sein. 
  
Klassen und Attribute werden hinzugefügt, um das Active Directory-Domänendienste-Schema zur Unterstützung von Skype for Business Server 2015 Server-, Dienst-und Benutzerobjekten zu erweitern. Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen. Details zum Sicherungsvorgang für Windows Server 2008 R2 mit SP1 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Informationen zu Windows Server 2003 und Windows Server 2003 R2 finden [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)Sie unter.
  
> [!CAUTION]
> Das Erweitern des Schemas ist nicht umkehrbar. Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist. Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig. Sie sollten eine Sicherung des Schemamaster-Domänencontrollers und eine vollständige Sicherung von Active Directory durchführen. 
  
So führen Sie eine Sicherung des Schemamaster-Domänencontrollers und einer vollständigen Sicherung von Active Directory durch:
  
1. Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.
    
2. Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.
    
3. Erweitern Sie das Schema.
    
4. Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.
    
5. Stellen Sie im unwahrscheinlichen Fall, dass ein Schema Erweiterungsfehler auftritt, den Systemstatus des Domänencontrollers und Active Directory wieder her, indem Sie die System Status Sicherung verwenden, die Sie zuvor ausgeführt haben.
    
> [!NOTE]
> Wenn Sie die Protokolldateien überprüfen müssen, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie die Dateien auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis Benutzer des Active Directory-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator im Domänen contoso.net angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp 
  

