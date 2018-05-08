---
title: Bereitstellungsprozess für die Ansageanwendung in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 08a52569dede43bbe54b1bf7e62f37114ba68853
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Bereitstellungsprozess für die Ansageanwendung in Skype for Business 2015
 
Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.
  
Der ankündigungsanwendung ist eine Enterprise-VoIP-Funktion, mit der Benutzer konfigurieren, was geschieht, wenn Anrufe an nicht zugewiesene Durchwahlnummern (Durchwahlnummern, die für Ihre Organisation gültig sind, aber nicht an eine Person oder ein Telefon zugewiesen werden). Beispielsweise können Sie eine Nachricht wiedergegeben oder in ein anderes Ziel oder beides übertragen werden Anrufe bei nicht zugewiesenen Nummern konfigurieren.
  
Der ankündigungsanwendung wird als Feature von Anwendung "Reaktionsgruppe" auf dem Front-End-Server oder Standard Edition-Server installiert, bei der Bereitstellung von Enterprise-VoIP. Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der ankündigungsanwendung. Sie müssen Enterprise-VoIP bereitstellen, vor dem Konfigurieren von Ansagen. Von der Anwendung Ankündigung erforderlichen Komponenten werden installiert und bei der Bereitstellung von Enterprise-VoIP aktiviert.
  
**Bereitstellungsprozess für Ansagen**

|**Phase**|**Schritte**|**Rollen**|**Dokumentation zur Bereitstellung**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Ansageeinstellungen  <br/> | Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS) <br/>  Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu. <br/> |"RTCUniversalServerAdmins"  <br/> "Csvoiceadministrator"  <br/> CsServerAdministrator  <br/> "Csadministrator"  <br/> CsViewOnlyAdministrator  <br/> |[Erstellen oder Löschen einer Ankündigung in Skype für Business Server 2015](create-an-announcement.md) <br/> [Erstellen Sie oder ändern Sie einen Bereichs nicht zugewiesenen Nummern in Skype für Business Server 2015](create-or-modify-an-unassigned-number-range.md) <br/> |
|Überprüfen Ihrer Bereitstellung von Ansagen  <br/> |Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.  <br/> |-  <br/> |[(Optional) Überprüfen der ansagebereitstellung in Skype für Business 2015](optional-verify-announcement-deployment.md) <br/> |
   

