---
title: Planen von Standortrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine erweiterte Bereitstellung von Notfalldiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101451"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planen von Standortrichtlinien für Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine erweiterte Bereitstellung von Notfalldiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP. 
  
> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie den Informationen unter [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) und Configure multiple emergency numbers in Skype for Business [folgen.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 
  
Sie erstellen Standortrichtlinien mithilfe der Skype for Business-Systemsteuerung oder mithilfe des [Cmdlets New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Jede Standortrichtlinie enthält die folgenden Informationen:
  
 **Aktivieren von Enhanced 9-1-1**
  
Wenn dieser Wert aktiviert ist, ist der Client für erweiterte Notrufdienste (E9-1-1) aktiviert. Wenn sich ein Client registriert, versucht er, einen Standort vom Standortinformationsdienst zu erhalten und die Standortinformationen als Teil eines Notrufs zu verwenden.
  
 **Ort**
  
Diese Einstellung wird nur verwendet, wenn **Erweitertes Aktivieren von 9-1-1** aktiviert ist.
  
Sie können die Einstellung **Speicherort** so konfigurieren, dass das Clientverhalten wie folgt definiert wird:
  
- Das Festlegen des Werts **auf Nein** bedeutet, dass der Benutzer nicht zur Eingabe eines Speicherorts aufgefordert wird.
    
- Wenn Sie den Wert auf **Ja** festlegen, wird der Benutzer zur Eingabe eines Speicherorts aufgefordert, kann die Eingabeaufforderung jedoch schließen.
    
- Das Festlegen  des Werts auf Haftungsausschluss bedeutet, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird und auch ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
> [!NOTE]
> Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. 
  
 **Haftungsausschluss der erweiterten Notrufdienste**
  
Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Skype for Business Server können Sie standortrichtlinien verwenden, um unterschiedliche Haftungsausschlüsse für verschiedene Locales oder unterschiedliche Benutzergruppen zu setzen.
  
 **Notrufnummer (E9-1-1-Wählnummer)**
  
Diese Wählzeichenfolge (weniger das führende "+", aber einschließlich jeder Normalisierung durch den Wählplan des Benutzers) bedeutet, dass es sich bei einem Anruf um einen Notruf handelt. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
  
> [!NOTE]
> Wenn Ihre Organisation kein Präfix für den Externen Leitungszugriff verwendet, müssen Sie keine entsprechende Normalisierungsregel für den Wählplan erstellen, die der Zeichenfolge 911 ein "+" hinzufügt, bevor Sie den Anruf an ausgehendes Routing auf einem Server mit Skype for Business Server senden. Das "+" wird automatisch vom Skype for Business-Client als Ergebnis der Standortrichtlinie vorab verwendet. Wenn Ihre Website jedoch ein Präfix für den externen Zugriff verwendet, müssen Sie der entsprechenden Wählplanrichtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff entfernt und das "+" hinzufügt. Wenn Ihr Standort beispielsweise das Präfix 9 für den externen Zugriff verwendet und ein Benutzer 9 911 wählt, um einen Notruf zu setzen, normalisiert der Client dies mithilfe der Wählplanrichtlinie auf +911, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird. 
  
 **Zeichenfolgenmasken für Notrufwähler (E9-1-1-Wählmaske)**
  
Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene Notrufwählzeichenfolge **übersetzt wird.** Sie können beispielsweise 112 hinzufügen, d. h. die Notrufnummer für den größten Teil Von Europa. Ein Skype for Business-Besucher aus Europa weiß möglicherweise nicht, dass 911 die NOTFALLnummer der USA ist, aber er kann 112 wählen und dasselbe Ergebnis erzielen. Schließen Sie wie bei der Notrufwählzeichenfolge vor jeder Nummer kein "+" ein, und stellen Sie bei Verwendung externer Zeilenzugriffscodes sicher, dass in der Wählplanrichtlinie des Benutzers Normalisierungsregeln enthalten sind, um die Zugriffscodeziffer zu deaktivieren.
  
 **PSTN-Verwendung**
  
Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
  
> [!NOTE]
> Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung überschreibt die der Sprachrichtlinie des Benutzers zugewiesenen PSTN-Verwendungen, gilt jedoch nur für Anrufe, die an die Wählzeichenfolge für Notrufe oder eine der Wählzeichenfolgenmasken für Notrufe übergeben werden. 
  
 **Benachrichtigungs-URI**
  
Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.
  
 **Konferenz-URI**
  
Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll. 
  
 **Konferenzmodus**
  
Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. 
  
 **Standortaktualisierungsintervall**
  
Gibt den Zeitraum (in Stunden) zwischen Clientanforderungen für eine Standortaktualisierung vom Standortinformationsdienst an. Der Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert ist 4.
