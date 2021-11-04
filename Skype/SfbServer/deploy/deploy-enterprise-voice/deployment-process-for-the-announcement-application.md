---
title: Bereitstellungsprozess für die Ankündigungsanwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: e579ca3877b35ae5cdbb85582516a3bfbac8c354
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745361"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Bereitstellungsprozess für die Ankündigungsanwendung in Skype for Business Server
 
Bereitstellungsprozess und Schritte für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP.
  
Die Ankündigungsanwendung ist ein Enterprise-VoIP Feature, mit dem Sie konfigurieren können, was mit Anrufen an nicht zugewiesene Erweiterungen geschieht (Erweiterungen, die für Ihre Organisation gültig sind, aber keiner Person oder einem Telefon zugewiesen sind). Sie können z. B. Anrufe an nicht zugewiesene Nummern so konfigurieren, dass eine Nachricht wiedergegeben oder an ein anderes Ziel oder beides übertragen wird.
  
Die Ankündigungsanwendung wird als Feature der Reaktionsgruppenanwendung auf dem Front-End-Server oder Standard Edition-Server installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion konfigurieren und die Tabelle nicht zugewiesener Nummern definieren.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte, die bei der Bereitstellung der Ankündigungsanwendung erforderlich sind. Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ankündigungen konfigurieren. Die für die Ankündigungsanwendung erforderlichen Komponenten werden installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.
  
**Bereitstellungsprozess für Ansagen**

|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Ansageeinstellungen  <br/> | Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS) <br/>  Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Erstellen oder Löschen einer Ankündigung in Skype for Business Server](create-an-announcement.md) <br/> [Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Überprüfen Ihrer Bereitstellung von Ansagen  <br/> |Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.  <br/> |-  <br/> |[(Optional) Überprüfen der Ankündigungsbereitstellung in Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

