---
title: Planen von Standortrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung planen.
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802805"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planen von Standortrichtlinien für Skype for Business Server
 
In diesem Thema erfahren Sie, wie Sie in Skype for Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung planen. 
  
> [!NOTE]
> Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client. Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie die Informationen unter [Planen mehrerer Notrufnummern in Skype for Business Server](multiple-emergency-numbers.md) und [Konfigurieren mehrerer Notrufnummern in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)befolgen. 
  
Sie erstellen Standortrichtlinien mithilfe des Skype Control Panels für Unternehmen oder mithilfe des Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Jede Standortrichtlinie enthält die folgenden Informationen:
  
 **Erweiterte Notfalldienste aktivieren**
  
Wenn dieser Wert aktiviert ist, ist der Client für erweiterte Notfalldienste (E9-1-1) aktiviert. Wenn ein Client registriert wird, versucht er, einen Standort vom standortinformationsdienst abzurufen, und die Standortinformationen werden als Teil eines Notrufs aufgenommen.
  
 **Standort**
  
Diese Einstellung wird nur verwendet, wenn **Erweiterte Notfalldienste aktivieren** aktiviert ist. 
  
Sie können die Einstellung **Standort** wie folgt konfigurieren, um das Clientverhalten zu definieren:   
  
- Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird.
    
- Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen.
    
- Wenn der Wert auf **Haftungsausschluss** festgelegt ist, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird. Zudem wird ihm ein Haftungsausschluss angezeigt, wenn er versucht, die Aufforderung zu verwerfen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
> [!NOTE]
> Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben.  
  
 **Haftungsausschluss der erweiterten Notfalldienste**
  
Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen. In Skype for Business Server können Sie mithilfe der ortungsrichtlinie unterschiedliche Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Gruppen von Benutzern festlegen.
  
 **Notruf-Wählzeichenfolge (Notfallnummer)**
  
Diese Wählzeichenfolge (abzüglich des führenden "+", aber einschließlich einer Normalisierung, die vom Wählplan des Benutzers ausgeführt wird) bedeutet, dass ein Anruf ein Notruf ist. Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.
  
> [!NOTE]
> Wenn in Ihrer Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet wird, müssen Sie keine entsprechende Normalisierungsregel für Wählpläne erstellen, die der 911-Zeichenfolge vor dem Senden des Anrufs an ausgehendes Routing auf einem Server mit Skype for Business Server ein "+" hinzufügt. Das "+" wird dem Skype for Business-Client automatisch als Folge der ortungsrichtlinie vorangestellt. Wenn Ihre Website jedoch ein externes Zugriffs Präfix verwendet, müssen Sie der entsprechenden Wähl Plan Richtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff abstreift und das "+" hinzufügt. Wenn Ihr Standort beispielsweise ein Präfix für den externen Zugriff von 9 verwendet und ein Benutzer 9 911 anwählt, um einen Notruf zu tätigen, wird der Client seine Wähl Plan Richtlinie verwenden, um diese auf + 911 zu normalisieren, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird. 
  
 **Notruf-Wählzeichenfolgenmasken (Notfallnummermaske)**
  
Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene **Notruf Zeichenfolge**übersetzt werden. So können Sie beispielsweise 112 hinzufügen, die für den größten Teil Europas die Notrufnummer ist. Ein Besuch von Skype for Business-Benutzern aus Europa weiß möglicherweise nicht, dass 911 die US-Notfallnummer ist, aber Sie können 112 anrufen und dasselbe Ergebnis erzielen. Geben Sie wie bei der Notruf Zeichenfolge keine "+" vor jeder Zahl ein, und wenn Sie die Zugriffscodes für externe Leitungen verwenden, stellen Sie sicher, dass in der Wähl Plan Richtlinie des Benutzers Normalisierungsregeln vorhanden sind, um die Zugriffscode Ziffer abzustreifen.
  
 **PSTN-Verwendung**
  
Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.
  
> [!NOTE]
> Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden. Diese PSTN-Nutzung überschreibt die PSTN-Nutzungen, die der VoIP-Richtlinie des Benutzers zugewiesen sind, gilt aber nur für Anrufe, die an die Notrufnummer oder an eine der Notruf-Zeichenfolgen Masken gestellt werden. 
  
 **Benachrichtigungs-URI**
  
Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.
  
 **Konferenz-URI**
  
Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.   
  
 **Konferenzmodus**
  
Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird.  
  
 **Standortaktualisierungsintervall**
  
Gibt die Zeitspanne (in Stunden) zwischen Clientanforderungen für ein Standort Update vom standortinformationsdienst an. Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden. Der Standardwert lautet 4.
  

