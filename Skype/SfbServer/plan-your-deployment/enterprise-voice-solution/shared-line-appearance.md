---
title: Planen der Gemeinsamen Leitungs darstellung in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: In diesem Thema erfahren Sie, wie Sie die Darstellung von gemeinsam genutzten Zeilen (Shared Line Appearance, SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015 planen.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813345"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planen der Gemeinsamen Leitungs darstellung in Skype for Business Server 2015
 
In diesem Thema erfahren Sie, wie Sie die Darstellung von gemeinsam genutzten Zeilen (Shared Line Appearance, SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015 planen. 
  
Die Funktion "Gemeinsame Leitung" ist eine Funktion in Skype for Business zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird. SLA kann jeden Skype for Business-aktivierten Skype for Business-Benutzer als freigegebene Nummer mit mehreren Zeilen konfigurieren, um auf mehrere Anrufe zu reagieren. Die Anrufe werden nicht tatsächlich für die freigegebene Nummer empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretung für die freigegebene Nummer fungieren. Jede Stellvertretung kann den Anruf an sich nehmen, während die restlichen Stellvertretung auf ihrem Telefon eine Benachrichtigung darüber erhalten, wer den Anruf aufgenommen hat und welche Leitung damit ausgelastet ist. Sowohl die Anzahl der Zeilen als auch die Stellvertreter können für eine freigegebene Nummer in SLA konfiguriert werden. Darüber hinaus können erweiterte Optionen wie BusyOption (was geschieht, wenn alle Zeilen besetzt sind) und MissedCallOption (der Fall, dass keine Stellvertretung einen Anruf anfordern) auch für eine freigegebene Nummer konfiguriert werden.
  
SLA wird nur auf den folgenden Telefongeräten unterstützt (für Skype for Business-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt): 
  
- Polycom VVX300 mit Firmwareupdate 5.4.1
    
- Polycom VVX400 mit Firmwareupdate 5.4.1
    
- Polycom VVX500 mit Firmwareupdate 5.4.1
    
- Polycom VVX600 mit Firmwareupdate 5.4.1
    
SLA ist ein neues Feature im kumulativen Update für Skype for Business Server vom November 2015. 
  
Weitere Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Featureliste

Das Einrichten einer SLA-Gruppe ermöglicht Folgendes:
  
- Alle Stellvertretung in der Gruppe kann eingehende Anrufe an dieselbe freigegebene Nummer beantworten. Die Anrufe können PSTN- oder SIP-basiert sein.
    
- Stellvertretung kann Anrufe halten und nehmen sie an.
    
- Stellvertretung kann Anrufe an eine Nummer außerhalb der GRUPPE "SLA" übertragen.
    
- Stellvertreter können sehen, wie viele Anrufe derzeit für die freigegebene Nummer stehen, und den Status der einzelnen Anrufe anzeigen.
    
- Sie können eine maximale Anzahl gleichzeitiger Anrufe für die freigegebene Nummer konfigurieren. Sie können auch festlegen, wie zusätzliche Anrufe verarbeitet werden sollen, nachdem dieser Maximalwert erreicht wurde. Überzählige Anrufe können mit einem Besetztzeichen abgelehnt, an eine alternative Nummer weitergeleitet oder an Voicemail weitergeleitet werden.
    
- Sie können konfigurieren, wie verpasste Anrufe (nach einer bestimmten Zeit nicht abgeholte Anrufe) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen verpasste Anrufe automatisch an Voicemail. Wenn Voicemail nicht für die Gruppenidentität (freigegebene Nummer) aktiviert ist, können Sie auswählen, dass verpasste Anrufe mit einem Besetztzeichen abgelehnt, an eine alternative Nummer weitergeleitet oder getrennt werden.
    

