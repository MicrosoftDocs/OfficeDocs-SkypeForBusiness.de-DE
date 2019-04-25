---
title: Bereitstellungsprozess für die ansageanwendung in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 96925df57a36373ee6f031b953f1933b3bac5681
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223041"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Bereitstellungsprozess für die ansageanwendung in Skype für Business Server
 
Bereitstellungsprozess und Schritte für die ansageanwendung in Skype für Business Server Enterprise-VoIP.
  
Der ankündigungsanwendung ist eine Enterprise-VoIP-Funktion, mit der Benutzer konfigurieren, was geschieht, wenn Anrufe an nicht zugewiesene Durchwahlnummern (Durchwahlnummern, die für Ihre Organisation gültig sind, aber nicht an eine Person oder ein Telefon zugewiesen werden). Beispielsweise können Sie eine Nachricht wiedergegeben oder in ein anderes Ziel oder beides übertragen werden Anrufe bei nicht zugewiesenen Nummern konfigurieren.
  
Der ankündigungsanwendung wird als Feature von Anwendung "Reaktionsgruppe" auf dem Front-End-Server oder Standard Edition-Server installiert, bei der Bereitstellung von Enterprise-VoIP. Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der ankündigungsanwendung. Sie müssen Enterprise-VoIP bereitstellen, vor dem Konfigurieren von Ansagen. Von der Anwendung Ankündigung erforderlichen Komponenten werden installiert und bei der Bereitstellung von Enterprise-VoIP aktiviert.
  
**Bereitstellungsprozess für Ansagen**

|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Ansageeinstellungen  <br/> | Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS) <br/>  Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Erstellen oder Löschen einer Ankündigung in Skype für Business Server](create-an-announcement.md) <br/> [Erstellen Sie oder ändern Sie einen Bereichs nicht zugewiesenen Nummern in Skype für Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Überprüfen Ihrer Bereitstellung von Ansagen  <br/> |Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.  <br/> |-  <br/> |[(Optional) Überprüfen der ansagebereitstellung in Skype für Unternehmen](optional-verify-announcement-deployment.md) <br/> |
   

