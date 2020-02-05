---
title: Bereitstellungsprozess für die Ankündigungs Anwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Bereitstellungsprozess und Schritte zur Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 89f01ed4c9488aa74b07bfae41f3bf27032b552e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767398"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Bereitstellungsprozess für die Ankündigungs Anwendung in Skype for Business Server
 
Bereitstellungsprozess und Schritte zur Ankündigungs Anwendung in Skype for Business Server Enterprise-VoIP
  
Bei der Ankündigungs Anwendung handelt es sich um ein Enterprise-VoIP-Feature, mit dem Sie konfigurieren können, was mit Anrufen zu nicht zugewiesenen Erweiterungen geschieht (Erweiterungen, die für Ihre Organisation gültig sind, aber keiner Person oder einem Telefon zugeordnet sind). So können Sie beispielsweise Anrufe an nicht zugewiesene Nummern konfigurieren, um eine Nachricht wiederzugeben oder an ein anderes Ziel oder beides übertragen zu werden.
  
Die Ankündigungs Anwendung wird auf dem Front-End-Server oder Standard Edition-Server als Feature der reaktionsgruppenanwendung installiert, wenn Sie Enterprise-VoIP bereitstellen. Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.
  
Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen der Ankündigungs Anwendung erforderlich sind. Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ankündigungen konfigurieren. Die von der Ankündigungs Anwendung benötigten Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.
  
**Bereitstellungsprozess für Ansagen**

|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Ansageeinstellungen  <br/> | Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS) <br/>  Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Erstellen oder Löschen einer Ankündigung in Skype for Business Server](create-an-announcement.md) <br/> [Erstellen oder Ändern eines nicht zugewiesenen Nummernbereichs in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Überprüfen Ihrer Bereitstellung von Ansagen  <br/> |Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.  <br/> |-  <br/> |[Optional Überprüfen der Ankündigungs Bereitstellung in Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

