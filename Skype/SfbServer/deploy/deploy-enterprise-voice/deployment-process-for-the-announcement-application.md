---
title: Bereitstellungsprozess für die Ankündigungsanwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812305"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Bereitstellungsprozess für die Ankündigungsanwendung in Skype for Business Server
 
Bereitstellungsprozess und Schritte für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP.
  
Die Ansageanwendung ist ein Enterprise-VoIP-Feature, mit dem Sie konfigurieren können, was mit Anrufen an nicht zugewiesene Durchsagen geschieht (Durchsagen, die für Ihre Organisation gültig sind, aber nicht einer Person oder einem Telefon zugewiesen sind). Sie können z. B. Anrufe an nicht zugewiesene Nummern so konfigurieren, dass eine Nachricht abspielt oder an ein anderes Ziel oder beides übertragen wird.
  
Die Ansageanwendung wird als Feature der Reaktionsgruppe auf dem Front-End-Server oder Standard Edition-Server installiert, wenn Sie Enterprise-VoIP. Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion konfigurieren und die Tabelle nicht zugewiesener Nummern definieren.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der Ankündigungsanwendung. Sie müssen die Enterprise-VoIP bereitstellen, bevor Sie Ansagen konfigurieren. Die für die Ankündigungsanwendung erforderlichen Komponenten werden installiert und aktiviert, wenn Sie Enterprise-VoIP.
  
**Bereitstellungsprozess für Ansagen**

|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Ansageeinstellungen  <br/> | Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS) <br/>  Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Erstellen oder Löschen einer Ansage in Skype for Business Server](create-an-announcement.md) <br/> [Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Überprüfen Ihrer Bereitstellung von Ansagen  <br/> |Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.  <br/> |-  <br/> |[(Optional) Überprüfen der Ansagebereitstellung in Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

