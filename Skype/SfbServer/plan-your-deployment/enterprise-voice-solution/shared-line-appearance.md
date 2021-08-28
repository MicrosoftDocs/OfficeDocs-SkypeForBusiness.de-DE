---
title: Plan for Shared Line Appearance in Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Funktion "Gemeinsame Leitungen" (Shared Line Appearance, SLA) in Skype for Business Server kumulativen Update vom November 2015 planen.
ms.openlocfilehash: b3ec50ff74ee246be892636dac4cdb910a2588d7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614035"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Plan for Shared Line Appearance in Skype for Business Server 2015
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie die Funktion "Gemeinsame Leitungen" (Shared Line Appearance, SLA) in Skype for Business Server kumulativen Update vom November 2015 planen. 
  
Die Gemeinsame Leitungen-Darstellung ist ein Feature in Skype for Business für die Behandlung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird. SLA kann jede Enterprise-VoIP konfigurieren, die Skype for Business Benutzer als gemeinsame Nummer mit mehreren Zeilen aktiviert ist, um auf mehrere Anrufe zu reagieren. Die Anrufe werden nicht tatsächlich über die freigegebene Nummer empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretungen für die freigegebene Nummer fungieren. Jeder der Stellvertretungen kann den Anruf annehmen, während die restlichen Stellvertretungen auf ihrem Telefon eine Benachrichtigung darüber erhalten, wer den Anruf angenommen hat und welche Leitung dadurch ausgelastet ist. Sowohl die Anzahl der Zeilen als auch die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden. Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen ausgelastet sind) und MissedCallOption (in dem keiner der Stellvertretungen einen Anruf entgegennimmt) auch für eine freigegebene Nummer konfiguriert werden.
  
SLA wird nur auf den folgenden Telefongeräten unterstützt (es wird nicht für Skype for Business Clients auf Computern, Mobiltelefonen oder anderen Geräten unterstützt): 
  
- Polycom VVX300 mit Firmwareupdate 5.4.1
    
- Polycom VVX400 mit Firmwareupdate 5.4.1
    
- Polycom VVX500 mit Firmwareupdate 5.4.1
    
- Polycom VVX600 mit Firmwareupdate 5.4.1
    
SLA ist ein neues Feature in Skype for Business Server kumulativen Update vom November 2015. 
  
Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)
  
## <a name="feature-list"></a>Featureliste

Das Einrichten einer SLA-Gruppe ermöglicht Folgendes:
  
- Alle Stellvertretungen in der Gruppe können eingehende Anrufe mit derselben freigegebenen Nummer beantworten. Die Anrufe können PSTN- oder SIP-basiert sein.
    
- Stellvertretungen können Anrufe halten und entgegennehmen.
    
- Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe übertragen.
    
- Stellvertretungen können sehen, wie viele Anrufe derzeit auf der freigegebenen Nummer liegen, und den Status der einzelnen Anrufe anzeigen.
    
- Sie können eine maximale Anzahl gleichzeitiger Anrufe für die freigegebene Nummer konfigurieren. Sie können auch festlegen, wie zusätzliche Anrufe verarbeitet werden sollen, nachdem dieser Höchstwert erreicht wurde. Überzählige Anrufe können mit einem Besetzt-Signal abgelehnt, an eine alternative Nummer oder an Voicemail weitergeleitet werden.
    
- Sie können konfigurieren, wie verpasste Anrufe (Anrufe, die nach einer bestimmten Zeit nicht aufgenommen werden) verarbeitet werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen verpasste Anrufe automatisch zu Voicemail. Wenn Voicemail für die Gruppenidentität (freigegebene Nummer) nicht aktiviert ist, können Sie auswählen, ob verpasste Anrufe mit einem Besetzt-Signal abgelehnt, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.
    

