---
title: Planen von Standortrichtlinien für Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 'In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine erweiterte Bereitstellung von Notrufdiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP planen.'
---

# <a name="plan-location-policies-for-skype-for-business-server"></a>Planen von Standortrichtlinien für Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie Standortrichtlinien für eine erweiterte Bereitstellung von Notrufdiensten (E9-1-1) in Skype for Business Server Enterprise-VoIP planen. 
  
> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie die Informationen in ["Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md)" befolgen und [mehrere Notrufnummern in Skype for Business konfigurieren](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Sie erstellen Standortrichtlinien mithilfe der Skype for Business Systemsteuerung oder mit dem Cmdlet ["New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)". Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Jede Standortrichtlinie enthält die folgenden Informationen:
  
 **Aktivieren von erweiterten 9-1-1**
  
Wenn dieser Wert aktiviert ist, ist der Client für erweiterte Notrufdienste (E9-1-1) aktiviert. Wenn sich ein Client registriert, versucht er, einen Standort vom Standortinformationsdienst abzurufen, und schließt die Standortinformationen als Teil eines Notrufs ein.
  
 **Ort**
  
Diese Einstellung wird nur verwendet, wenn **"Erweitert 9-1-1 aktivieren** " aktiviert ist.
  
Sie können die **Einstellung "Speicherort** " so konfigurieren, dass das Clientverhalten wie folgt definiert wird:
  
- Das Festlegen des Werts auf **"Nein** " bedeutet, dass der Benutzer nicht zur Eingabe eines Speicherorts aufgefordert wird.
    
- Das Festlegen des Werts auf **"Ja** " bedeutet, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird, die Eingabeaufforderung jedoch geschlossen werden kann.
    
- Das Festlegen des Werts auf **"Haftungsausschluss** " bedeutet, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird und auch ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
> [!NOTE]
> Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. 
  
 **Haftungsausschluss der erweiterten Notrufdienste**
  
Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Skype for Business Server können Sie standortrichtlinien verwenden, um unterschiedliche Haftungsausschlüsse für unterschiedliche Gebietsschemas oder unterschiedliche Benutzergruppen festzulegen.
  
 **Notrufwählzeichenfolge (E9-1-1-Wählnummer)**
  
Diese Wählzeichenfolge (weniger das führende "+", aber einschließlich aller Normalisierungen durch den Wählplan des Benutzers) bedeutet, dass ein Anruf ein Notruf ist. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
  
> [!NOTE]
> Wenn Ihre Organisation kein Präfix für den externen Leitungszugriff verwendet, müssen Sie keine entsprechende Normalisierungsregel für den Wählplan erstellen, die der 911-Zeichenfolge ein "+" hinzufügt, bevor der Anruf an das ausgehende Routing auf einem Server gesendet wird, auf dem Skype for Business Server ausgeführt wird. Das "+" wird dem Skype for Business Client aufgrund der Standortrichtlinie automatisch vorangestellt. Wenn Ihre Website jedoch ein Präfix für den externen Zugriff verwendet, müssen Sie der entsprechenden Wählplanrichtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff entfernt und das "+" hinzufügt. Wenn Ihr Standort beispielsweise ein externes Zugriffspräfix 9 verwendet und ein Benutzer 9 911 wählt, um einen Notruf zu tätigen, verwendet der Client seine Wählplanrichtlinie, um dies auf +911 zu normalisieren, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird. 
  
 **Notfall-Wählzeichenfolgenmasken (E9-1-1-Wählmaske)**
  
Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene **Notrufwählzeichenfolge** übersetzt wird. Sie können z. B. 112 hinzufügen, was die Notrufnummer für die meisten Europäischen Länder ist. Ein Besuch Skype for Business Benutzer aus Europa weiß möglicherweise nicht, dass 911 die US-Notrufnummer ist, aber er kann 112 wählen und dasselbe Ergebnis erhalten. Fügen Sie wie bei der Notrufwählzeichenfolge vor jeder Nummer kein "+" ein. Wenn Sie externe Leitungen verwenden, stellen Sie sicher, dass die Wählplanrichtlinie des Benutzers Normalisierungsregeln enthält, um die Zugriffscode-Ziffer zu entfernen.
  
 **PSTN-Verwendung**
  
Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
  
> [!NOTE]
> Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Verwendung setzt die PSTN-Verwendungen außer Kraft, die der VoIP-Richtlinie des Benutzers zugewiesen sind, gilt jedoch nur für Anrufe, die an die Notrufwählzeichenfolge oder eine der Notwählzeichenfolgenmasken getätigt werden. 
  
 **Benachrichtigungs-URI**
  
Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.
  
 **Konferenz-URI**
  
Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll. 
  
 **Konferenzmodus**
  
Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. 
  
 **Standortaktualisierungsintervall**
  
Gibt den Zeitraum (in Stunden) zwischen Clientanforderungen für eine Standortaktualisierung vom Standortinformationsdienst an. Der Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert ist 4.
