---
title: Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Willkommen bei der Skype for Business Server-Systemsteuerung, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Sie können die Systemsteuerung verwenden, um die Arten von Verwaltungsaufgaben auszuführen, die in früheren Versionen mithilfe der Microsoft Management Console ausgeführt wurden.
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804895"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung

Willkommen bei der Skype for Business Server-Systemsteuerung, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Sie können die Systemsteuerung verwenden, um die Arten von Verwaltungsaufgaben auszuführen, die in früheren Versionen mithilfe der Microsoft Management Console ausgeführt wurden.

Es gibt eine Reihe wichtiger Aufgaben, die sie nach der Bereitstellung von Skype for Business Server dringend ausführen sollten. Einige dieser Aufgaben sind anfängliche Konfigurationsschritte, die Sie möglicherweise bereits während der Bereitstellung ausgeführt haben, bei anderen Aufgaben handelt es sich um Optimierungen oder Änderungen an Standardeinstellungen oder Einstellungen, die Sie bei der Bereitstellung konfiguriert haben. Bei weiteren in diesem Thema beschriebenen Aufgaben werden die Konfigurationseinstellungen überprüft, die Sie während des Bereitstellungsprozesses vorgenommen haben.

> [!NOTE]
> Bevor Sie die Aufgaben in der folgenden Tabelle ausführen, stellen Sie sicher, dass Sie sich mit den richtigen Benutzerrechten, Berechtigungen und Rollen anmelden, wie im Abschnitt "Rollen und Bereich" des Themas "Rollenbasierte Zugriffssteuerung" [beschrieben.](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)

## <a name="first-run-checklist"></a>Prüfliste vor der erstmaligen Ausführung

Es wird dringend empfohlen, die in diesem Thema genannten Aufgaben zu überprüfen und dann die entsprechenden Verfahren für die Lync Server-Bereitstellung in Ihrer Organisation auszuführen.

|**Aufgabe**|**Systemsteuerungsgruppe**|**Dokumentation**|
|:-----|:-----|:-----|
|Überprüfen Sie, ob die in Ihrer Topologie installierten Dienste wie erwartet ausgeführt werden.  <br/> |**Topologie** <br/> |[Anzeigen von Details zu einem Dienst](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Aktivieren Sie Benutzer für Skype for Business Server. Optional und, wenn Sie von einer früheren Version migrieren, verschieben Sie Benutzer zu Skype for Business Server.  <br/> |**Benutzer** <br/> |[Verwalten von Benutzern](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben oder dies für die Zukunft planen, konfigurieren Sie eine SIP-Trunkverbindung, um Verbindungen mit dem Telefonfestnetz zu ermöglichen.  <br/> |**VoIP-Routing** <br/> |[Konfigurieren von Trunks und Übersetzungsregeln](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben, überprüfen Sie die Enterprise-VoIP-Routingeinstellungen.  <br/> |**VoIP-Routing** <br/> |[Testen des VoIP-Routings](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Wenn Sie einen Archivierungsserver bereitgestellt haben, überprüfen Sie, ob die Archivierungsrichtlinien und -einstellungen die Anforderungen im Hinblick auf die Einhaltung rechtlicher Bestimmungen Ihrer Organisation erfüllen.  <br/> |**Überwachung und Archivierung** <br/> |[Verwalten der Archivierung](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Wenn Sie einen Monitoring Server bereitgestellt haben, zeigen Sie die Monitoring Server-Berichte mit Nutzungs- und Diagnoseinformationen an.  <br/> |**Start** <br/> |[Verwalten der Integrität und Überwachung in Skype for Business Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


