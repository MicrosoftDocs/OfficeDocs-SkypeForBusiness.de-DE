---
title: Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Willkommen bei der Skype for Business Server-Systemsteuerung, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Sie können die Systemsteuerung verwenden, um die Typen von Administrativen Aufgaben auszuführen, die in früheren Versionen mithilfe der Microsoft Management Console ausgeführt wurden.
ms.openlocfilehash: 3e8fee53c37079c46862e05f246d984c621b57ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100441"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Checkliste vor dem ersten Ausführen für die Skype for Business Server-Systemsteuerung

Willkommen bei der Skype for Business Server-Systemsteuerung, der webbasierten Benutzeroberfläche für die Verwaltung und Verwaltung von Skype for Business Server. Sie können die Systemsteuerung verwenden, um die Typen von Administrativen Aufgaben auszuführen, die in früheren Versionen mithilfe der Microsoft Management Console ausgeführt wurden.

Es gibt eine Reihe wichtiger Aufgaben, die Sie dringend nach der Bereitstellung von Skype for Business Server ausführen sollten. Einige dieser Aufgaben sind anfängliche Konfigurationsschritte, die Sie möglicherweise bereits während der Bereitstellung ausgeführt haben, bei anderen Aufgaben handelt es sich um Optimierungen oder Änderungen an Standardeinstellungen oder Einstellungen, die Sie bei der Bereitstellung konfiguriert haben. Bei weiteren in diesem Thema beschriebenen Aufgaben werden die Konfigurationseinstellungen überprüft, die Sie während des Bereitstellungsprozesses vorgenommen haben.

> [!NOTE]
> Bevor Sie die Aufgaben in der folgenden Tabelle ausführen, stellen Sie sicher, dass Sie sich mit den richtigen Benutzerrechten, Berechtigungen und Rollen anmelden, wie im Abschnitt "Rollen und Bereich" des Themas Rollenbasierte Zugriffssteuerung [beschrieben.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)

## <a name="first-run-checklist"></a>Prüfliste vor der erstmaligen Ausführung

Es wird dringend empfohlen, die in diesem Thema genannten Aufgaben zu überprüfen und dann die entsprechenden Verfahren für die Bereitstellung in Ihrer Organisation auszuführen.

|**Aufgabe**|**Systemsteuerungsgruppe**|**Dokumentation**|
|:-----|:-----|:-----|
|Überprüfen Sie, ob die in Ihrer Topologie installierten Dienste wie erwartet ausgeführt werden.  <br/> |**Topologie** <br/> |[Anzeigen von Details zu einem Dienst](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|Aktivieren Sie Benutzer für Skype for Business Server. Optional und, wenn Sie von einer früheren Version migrieren, verschieben Sie Benutzer zu Skype for Business Server.  <br/> |**Benutzer** <br/> |[Verwalten von Benutzern](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben oder dies für die Zukunft planen, konfigurieren Sie eine SIP-Trunkverbindung, um Verbindungen mit dem Telefonfestnetz zu ermöglichen.  <br/> |**VoIP-Routing** <br/> |[Konfigurieren von Trunks und Übersetzungsregeln](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|Wenn Sie Enterprise-VoIP bereitgestellt haben, überprüfen Sie die Enterprise-VoIP-Routingeinstellungen.  <br/> |**VoIP-Routing** <br/> |[Testen des VoIP-Routings](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|Wenn Sie einen Archivierungsserver bereitgestellt haben, überprüfen Sie, ob die Archivierungsrichtlinien und -einstellungen die Anforderungen im Hinblick auf die Einhaltung rechtlicher Bestimmungen Ihrer Organisation erfüllen.  <br/> |**Überwachung und Archivierung** <br/> |[Verwalten der Archivierung](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|Wenn Sie einen Monitoring Server bereitgestellt haben, zeigen Sie die Monitoring Server-Berichte mit Nutzungs- und Diagnoseinformationen an.  <br/> |**Start** <br/> |[Verwalten von Integrität und Überwachung in Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |