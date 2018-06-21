---
title: Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Willkommen Sie bei der Skype für Business Server-Systemsteuerung, die webbasierte Benutzeroberfläche für die Administration und Verwaltung von Skype für Business Server. Mit der Systemsteuerung können Sie diejenigen Arten von administrativen Aufgaben ausführen, die in früheren Versionen über die Microsoft Management Console ausgeführt wurden.
ms.openlocfilehash: 78c9943145e0dd12feb5b73e165610fef19bf396
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978083"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung
 
Willkommen Sie bei der Skype für Business Server-Systemsteuerung, die webbasierte Benutzeroberfläche für die Administration und Verwaltung von Skype für Business Server. Mit der Systemsteuerung können Sie diejenigen Arten von administrativen Aufgaben ausführen, die in früheren Versionen über die Microsoft Management Console ausgeführt wurden.
  
Es gibt eine Reihe von wichtigen Aufgaben, bei denen es wird dringend empfohlen, dass Sie durchführen, nachdem Sie Skype für Business Server bereitgestellt haben. Einige dieser Aufgaben sind anfängliche Konfigurationsschritte, die Sie möglicherweise bereits während der Bereitstellung ausgeführt haben, bei anderen Aufgaben handelt es sich um Optimierungen oder Änderungen an Standardeinstellungen oder Einstellungen, die Sie bei der Bereitstellung konfiguriert haben. Bei weiteren in diesem Thema beschriebenen Aufgaben werden die Konfigurationseinstellungen überprüft, die Sie während des Bereitstellungsprozesses vorgenommen haben.
  
> [!NOTE]
> Bevor Sie die Aufgaben in der folgenden Tabelle durchführen, stellen Sie sicher, dass Sie melden Sie sich mit den richtigen Benutzerrechte, Berechtigungen und Rolle wie im Abschnitt "Rollen und Umfang" neben dem Thema [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) beschrieben.
  
## <a name="first-run-checklist"></a>Prüfliste vor der erstmaligen Ausführung

Es wird dringend empfohlen, dass Sie überprüfen Sie die Aufgaben, die in diesem Thema bezeichnet wird, und Sie dann die entsprechenden Schritte für die Lync Server-Bereitstellung in Ihrer Organisation führen.
  
|**Aufgabe**|**Systemsteuerung Steuerelementgruppe**|**Dokumentation**|
|:-----|:-----|:-----|
|Überprüfen Sie, ob die in Ihrer Topologie installierten Dienste wie erwartet ausgeführt werden.  <br/> |**Topologie** <br/> |[Anzeigen von Details zu einem Dienst](http://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Aktivieren von Benutzern für Skype für Business Server. Optional und, wenn eine Migration von einer vorherigen Version, Migrieren von Benutzern zu Skype für Business Server.  <br/> |**Benutzer** <br/> |[Verwalten von Benutzern](http://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben oder dies für die Zukunft planen, konfigurieren Sie eine SIP-Trunkverbindung, um Verbindungen mit dem Telefonfestnetz zu ermöglichen.  <br/> |**VoIP-Routing** <br/> |[Konfigurieren von Trunks und Übersetzungsregeln](http://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben, überprüfen Sie die Enterprise-VoIP-Routingeinstellungen.  <br/> |**VoIP-Routing** <br/> |[Testen des VoIP-Routings](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Wenn Sie einen Archivierungsserver bereitgestellt haben, überprüfen Sie, ob die Archivierungsrichtlinien und -einstellungen die Anforderungen im Hinblick auf die Einhaltung rechtlicher Bestimmungen Ihrer Organisation erfüllen.  <br/> |**Überwachen und Archivieren** <br/> |[Verwalten der Archivierung](http://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Wenn Sie einen Monitoring Server bereitgestellt haben, zeigen Sie die Monitoring Server-Berichte mit Nutzungs- und Diagnoseinformationen an.  <br/> |**Pos1** <br/> |[Verwalten von Integritäts- und Überwachung in Skype für Business Server 2015](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |
   

