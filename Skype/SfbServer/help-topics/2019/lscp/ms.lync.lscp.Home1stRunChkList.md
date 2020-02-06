---
title: Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Willkommen beim Skype for Business Server Control Panel, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Mit der Systemsteuerung können Sie diejenigen Arten von administrativen Aufgaben ausführen, die in früheren Versionen über die Microsoft Management Console ausgeführt wurden.
ms.openlocfilehash: 0efd6b5730154e0f1847de6f4caf87867f977817
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797636"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung

Willkommen beim Skype for Business Server Control Panel, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Mit der Systemsteuerung können Sie diejenigen Arten von administrativen Aufgaben ausführen, die in früheren Versionen über die Microsoft Management Console ausgeführt wurden.

Nach der Bereitstellung von Skype for Business Server empfehlen wir dringend, dass Sie eine Reihe wichtiger Aufgaben ausführen. Einige dieser Aufgaben sind anfängliche Konfigurationsschritte, die Sie möglicherweise bereits während der Bereitstellung ausgeführt haben, bei anderen Aufgaben handelt es sich um Optimierungen oder Änderungen an Standardeinstellungen oder Einstellungen, die Sie bei der Bereitstellung konfiguriert haben. Bei weiteren in diesem Thema beschriebenen Aufgaben werden die Konfigurationseinstellungen überprüft, die Sie während des Bereitstellungsprozesses vorgenommen haben.

> [!NOTE]
> Bevor Sie die in der folgenden Tabelle aufgeführten Aufgaben ausführen, stellen Sie sicher, dass Sie mit den richtigen Benutzerrechten, Berechtigungen und Rollen angemeldet sind. Eine Beschreibung der erforderlichen Benutzerrechte, Berechtigungen und Rollen finden Sie in der Planungsdokumentation im Abschnitt „Rollen und Bereiche“ des Themas [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Prüfliste vor der erstmaligen Ausführung

Wir empfehlen dringend, die in diesem Thema aufgeführten Aufgaben zu überprüfen und dann die entsprechenden Verfahren für die Bereitstellung in Ihrer Organisation durchzuführen.

|**Aufgabe**|**Systemsteuerungsgruppe**|**Dokumentation**|
|:-----|:-----|:-----|
|Überprüfen Sie, ob die in Ihrer Topologie installierten Dienste wie erwartet ausgeführt werden.  <br/> |**Topologie** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Aktivieren von Benutzern für Skype for Business Server. Wenn Sie die Migration von einer früheren Version aus durchlaufen, verschieben Sie die Benutzer optional in Skype for Business Server.  <br/> |**Benutzer** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben oder dies für die Zukunft planen, konfigurieren Sie eine SIP-Trunkverbindung, um Verbindungen mit dem Telefonfestnetz zu ermöglichen.  <br/> |**VoIP-Routing** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben, überprüfen Sie die Enterprise-VoIP-Routingeinstellungen.  <br/> |**VoIP-Routing** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Wenn Sie einen Archivierungsserver bereitgestellt haben, überprüfen Sie, ob die Archivierungsrichtlinien und -einstellungen die Anforderungen im Hinblick auf die Einhaltung rechtlicher Bestimmungen Ihrer Organisation erfüllen.  <br/> |**Überwachen und Archivieren** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Wenn Sie einen Monitoring Server bereitgestellt haben, zeigen Sie die Monitoring Server-Berichte mit Nutzungs- und Diagnoseinformationen an.  <br/> |**Pos1** <br/> |[Verwalten von Status und Überwachung in Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


