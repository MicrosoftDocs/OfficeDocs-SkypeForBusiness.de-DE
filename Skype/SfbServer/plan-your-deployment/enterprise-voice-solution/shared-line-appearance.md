---
title: Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: In diesem Thema erfahren, wie für freigegebene Zeile Darstellung (SLA) in Skype Business Server 2015 November 2015 geplant kumulative Update.
ms.openlocfilehash: fa0d8923c234773e3b21ec43bca4c4d7aafde4df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913455"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
 
In diesem Thema erfahren, wie für freigegebene Zeile Darstellung (SLA) in Skype Business Server 2015 November 2015 geplant kumulative Update. 
  
Darstellung einer freigegebenen Linie ist ein Feature in Skype für Unternehmen für die Verarbeitung mehrerer Anrufe an eine bestimmte Anzahl freigegebenen aufgerufen. SLA konfigurieren kann Enterprise Voice aktiviert Skype für Geschäftsbenutzer als freigegebene Zahl mit mehrere Zeilen auf mehrere Aufrufe reagieren. Die Anrufe werden nicht auf die freigegebenen Anzahl tatsächlich empfangen, sie werden stattdessen an Benutzer, die eine Stellvertretung für die freigegebenen Anzahl übernehmen weitergeleitet. Keines der Stellvertretungen kann Anruf auswählen, während Sie der Rest der Delegaten erhalten eine Benachrichtigung über ein Telefon zu, die den Anruf entnommen und welcher Zeile dementsprechend ausgelastet ist. Sowohl die Anzahl der Zeilen und an die Stellvertretungen können für eine freigegebene Zahl in SLA konfiguriert werden. Darüber hinaus erweiterte Optionen an, wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen beschäftigt sind) und MissedCallOption (die Groß-/Kleinschreibung in welche die Stellvertretungen auswählen einen Aufruf keines), kann auch für eine freigegebene Anzahl konfiguriert werden.
  
SLA wird nur unter den folgenden Telefone unterstützt (es ist nicht für Skype für Business-Clients auf Computern, Mobiltelefone oder andere Geräte unterstützt): 
  
- Polycom VVX300 mit Firmwareupdate 5.4.1
    
- Polycom VVX400 mit Firmwareupdate 5.4.1
    
- Polycom VVX500 mit Firmwareupdate 5.4.1
    
- Polycom VVX600 mit Firmwareupdate 5.4.1
    
Vereinbarung zum SERVICELEVEL ist ein neues Feature in Skype für Business Server 2015 November Kumulatives Update. 
  
Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Liste der Funktionen

Das Einrichten einer SLA-Gruppe macht Folgendes möglich:
  
- Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.
    
- Stellvertretungen können Anrufe halten und annehmen.
    
- Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.
    
- Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.
    
- Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.
    
- Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.
    

