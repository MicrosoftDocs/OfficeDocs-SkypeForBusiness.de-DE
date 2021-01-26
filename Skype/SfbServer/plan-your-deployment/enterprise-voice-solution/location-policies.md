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
description: In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine Bereitstellung mit erweiterten Notrufdiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825535"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planen von Standortrichtlinien für Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine Bereitstellung mit erweiterten Notrufdiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP. 
  
> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie die Informationen unter "Planen mehrerer Notrufnummern [in Skype for Business Server"](multiple-emergency-numbers.md) und "Konfigurieren mehrerer Notrufnummern in Skype for [Business" befolgen.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 
  
Sie erstellen Standortrichtlinien mithilfe der Skype for Business-Systemsteuerung oder mithilfe des [Cmdlets "New-CsLocationPolicy".](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Weitere Informationen finden Sie unter ["Erstellen von Standortrichtlinien in Skype for Business Server".](../../deploy/deploy-enterprise-voice/create-location-policies.md)
  
Jede Standortrichtlinie enthält die folgenden Informationen:
  
 **Aktivieren der erweiterten 9-1-1-Funktion**
  
Wenn dieser Wert aktiviert ist, wird der Client für erweiterte Notrufdienste (E9-1-1) aktiviert. Wenn sich ein Client registriert, versucht er, einen Standort vom Standortinformationsdienst zu erhalten und enthält die Standortinformationen als Teil eines Notrufs.
  
 **Ort**
  
Diese Einstellung wird nur verwendet, wenn **"Erweitert 9-1-1** aktivieren" aktiviert ist.
  
Sie können die Einstellung **"Speicherort"** so konfigurieren, dass das Clientverhalten wie folgt definiert wird:
  
- Das Festlegen des **Werts auf "Nein"** bedeutet, dass der Benutzer nicht zur Eingabe eines Standorts aufgefordert wird.
    
- Das Festlegen des **Werts auf "Ja"** bedeutet, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird, die Eingabeaufforderung jedoch schließen kann.
    
- Das Festlegen  des Werts auf "Haftungsausschluss" bedeutet, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird und auch ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
> [!NOTE]
> Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. 
  
 **Haftungsausschluss der erweiterten Notrufdienste**
  
Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Skype for Business Server können Sie standortrichtlinien verwenden, um unterschiedliche Haftungsausschlüsse für unterschiedliche Länder- oder Benutzergruppen zu setzen.
  
 **Notrufwählzeichenfolge (E9-1-1-Wählnummer)**
  
Diese Wählzeichenfolge (ohne das führende "+", aber einschließlich aller Normalisierungen durch den Wählplan des Benutzers) bedeutet, dass es sich bei einem Anruf um einen Notruf handelt. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
  
> [!NOTE]
> Wenn Ihre Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet, müssen Sie keine entsprechende Wählplannormalisierungsregel erstellen, die der 911-Zeichenfolge ein "+" hinzufügt, bevor der Anruf an das ausgehende Routing auf einem Server mit Skype for Business Server gesendet wird. Das "+" wird dem Skype for Business-Client als Ergebnis der Standortrichtlinie automatisch vorgeschaltet. Wenn Ihre Website jedoch ein Präfix für den externen Zugriff verwendet, müssen Sie der entsprechenden Wählplanrichtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff entfernt und das "+" hinzufügt. Wenn ihr Standort beispielsweise das Präfix 9 für den externen Zugriff verwendet und ein Benutzer 9 911 wählt, um einen Notruf zu führen, normalisiert der Client dies mithilfe der Wählplanrichtlinie auf +911, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird. 
  
 **Notrufwählzeichenfolgenmasken (E9-1-1-Wählmaske)**
  
Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene Notrufwählzeichenfolge **übersetzt wird.** Sie können beispielsweise "112" hinzufügen, die Notrufnummer für die meisten Benutzer in Europa. Ein Benutzer, der Skype for Business aus Europa besucht, weiß möglicherweise nicht, dass 911 die US-Notrufnummer ist, aber er kann 112 wählen und dasselbe Ergebnis erhalten. Schließen Sie wie bei der Notrufwählzeichenfolge vor jeder Nummer kein "+" ein, und stellen Sie sicher, dass in der Wählplanrichtlinie des Benutzers Normalisierungsregeln enthalten sind, um die Zugriffscodeziffer zu deaktivieren.
  
 **PSTN-Verwendung**
  
Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
  
> [!NOTE]
> Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese Festnetzverwendung setzt die pstN-Verwendungen außer Kraft, die der Sprachrichtlinie des Benutzers zugewiesen sind, gilt jedoch nur für Anrufe, die an die Notrufwählzeichenfolge oder eine der Notrufwählzeichenfolgenmasken übergeben werden. 
  
 **Benachrichtigungs-URI**
  
Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.
  
 **Konferenz-URI**
  
Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll. 
  
 **Konferenzmodus**
  
Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. 
  
 **Standortaktualisierungsintervall**
  
Gibt den Zeitraum (in Stunden) zwischen Clientanforderungen für eine Standortaktualisierung vom Standortinformationsdienst an. Der Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert ist 4.
  

