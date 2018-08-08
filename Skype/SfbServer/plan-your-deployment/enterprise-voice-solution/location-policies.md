---
title: Planen von Standortrichtlinien für Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lesen Sie in diesem Thema erfahren, wie Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung in Skype planen.
ms.openlocfilehash: cbc4bdbf552c3839cef0701dcf3e47e4603a270e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971167"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planen von Standortrichtlinien für Skype für Business Server
 
Lesen Sie in diesem Thema erfahren, wie Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung in Skype planen. 
  
> [!NOTE]
> Skype für Business Server unterstützt jetzt die Konfiguration von mehreren Notfall Zahlen für einen Client an. Wenn Sie mehrere Notfall Nummern konfigurieren möchten, müssen Sie die Informationen in [mehrere Notfall Zahlen in Skype für Business Server planen](multiple-emergency-numbers.md) und [Konfigurieren von mehreren Notfall Zahlen in Skype für Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)befolgen. 
  
Erstellen von ortungsrichtlinien mithilfe der Skype für die Business-Systemsteuerung oder mit dem [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) -Cmdlet. Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype für Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Jede Standortrichtlinie enthält die folgenden Informationen:
  
 **Erweiterte Notfalldienste aktivieren**
  
Wenn dieser Wert aktiviert ist, wird der Client für erweiterte Notfalldienste (E9-1-1) aktiviert. Wenn ein Client registriert, versucht, einen Speicherort aus dem Dienst Standortinformationen zu erhalten und berücksichtigt die Standortinformationen als Teil eines Notrufs.
  
 **Standort**
  
Diese Einstellung wird nur verwendet, wenn **Erweiterte Notfalldienste aktivieren** aktiviert ist. 
  
Sie können die Einstellung **Standort** wie folgt konfigurieren, um das Clientverhalten zu definieren:   
  
- Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird.
    
- Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen.
    
- Wenn der Wert auf **Haftungsausschluss** festgelegt ist, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird. Zudem wird ihm ein Haftungsausschluss angezeigt, wenn er versucht, die Aufforderung zu verwerfen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
> [!NOTE]
> Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben.  
  
 **Haftungsausschluss der erweiterten Notfalldienste**
  
Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Skype für Business Server können Sie ortungsrichtlinie verwenden, um verschiedene Haftungsausschlüsse für unterschiedliche Gebietsschemas oder andere Gruppen von Benutzern festzulegen.
  
 **Notruf-Wählzeichenfolge (Notfallnummer)**
  
Diese Zeichenfolge Dial (weniger das führende Plus "+", aber einschließlich des Benutzers Dial Plan dazu Normalisierung) gibt an, dass ein Anruf ein Notruf ist. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
  
> [!NOTE]
> Wenn Ihre Organisation ein Präfix für den externen Zeile nicht verwendet, müssen Sie keine entsprechende Dial Plan Normalisierungsregel erstellen, die ein "+" der 911 Zeichenfolge vor dem Senden des Anrufs an das Ausgangsrouting auf einem Server mit Skype für Business Server; hinzufügt "+" wird automatisch von der Skype für Business-Client als Ergebnis der Standortrichtlinie vorangestellt werden. Jedoch, wenn der Website ein Präfix für den externen Zugriff verwendet wird, müssen Sie eine Normalisierungsregel der betreffenden Dial Plan Richtlinie hinzuzufügen, die das Präfix für externen Zugriff entfernt und fügt die "+". Beispielsweise wenn Ihres Standorts für ein Präfix für externen Zugriff von 9 verwendet wird und ein Benutzer 9 911 anwählt um ein Notruf platzieren, der Client verwendet seine Dial Plan Richtlinie dies normalisieren auf +911 vor der die gewählte Nummer durch die Routen im Standortprofil des Anrufers ausgewertet wird. 
  
 **Notruf-Wählzeichenfolgenmasken (Notfallnummermaske)**
  
Eine durch Semikolons getrennte Liste mit Wählzeichenfolgen, die in die angegebene **Notrufwählzeichenfolge**übersetzt wird. Beispielsweise kann hinzuzufügenden 112, also die Anzahl der notrufunterstützung für die meisten Europa. Eine Website besucht Skype für Geschäftsbenutzer in Europa wissen möglicherweise nicht, dass 911 die Notrufnummer US ist, aber sie können 112 einwählen und erhalten dasselbe Ergebnis. Achten Sie wie ein "+" vor jeder Zahl nicht mit der Emergency Dial Zeichenfolge einschließen, und wenn Sie externe Zeile Zugriffscodes verwenden, darauf, dass in der Richtlinie des Benutzers Dial Plan an die Ziffer Zugriffscode entfernt Normalisierungsregeln vorhanden sind.
  
 **PSTN-Verwendung**
  
Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
  
> [!NOTE]
> Eine ortungsrichtlinie kann nur jeweils einmal zugewiesen werden. In diesem PSTN-Verwendung überschreibt die PSTN-Verwendungen des Benutzers VoIP-Richtlinie zugewiesen, aber gilt nur für die Emergency DFÜ-Zeichenfolge oder auf eine der Emergency Dial Zeichenfolge Masken getätigte Anrufe. 
  
 **Benachrichtigungs-URI**
  
Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.
  
 **Konferenz-URI**
  
Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.   
  
 **Konferenzmodus**
  
Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird.  
  
 **Standortaktualisierungsintervall**
  
Gibt die Zeitdauer (in Stunden) zwischen Clientanforderungen für ein Location-Update aus dem Dienst Standortinformationen an. Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert lautet 4.
  

