---
title: Planen von Privatleitungen mit Skype for Business
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
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planen privater (sekundärer) Telefonleitungen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813595"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planen von Privatleitungen mit Skype for Business
 
Planen privater (sekundärer) Telefonleitungen in Skype for Business Server Enterprise-VoIP.
  
Mit Skype for Business Server können Sie Benutzern zusätzlich zu ihrer primären Telefonleitung eine zweite Privatleitung zur Verfügung stellen. Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.
  
Privatleitungen können nur mit der Skype for Business Server-Verwaltungsshell konfiguriert werden. Sie können keine Privatleitungen mit der Skype for Business Server-Systemsteuerung konfigurieren. Privatleitungen sollten nur in Bereitstellungen von Skype for Business Server und nicht in gemischten Bereitstellungen konfiguriert werden.
  
## <a name="characteristics-of-private-telephone-lines"></a>Eigenschaften von Privatleitungen

Obwohl das Konzept einer zweiten Privatleitung grundsätzlich einfach ist, ist es wichtig, die Merkmale von Privatleitungen zu verstehen und zu verstehen, wie sie den primären Telefonleitungen der Benutzer ähneln und sich von ihnen unterscheiden.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Allgemeine Eigenschaften von Privatleitungen

- Ein Benutzer kann nur eine Privatleitung besitzen.
    
- Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.
    
- Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse, und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Instant Messaging-Identität). 
    
- Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung. Sie sind bei gehosteten Bereitstellungen von Skype for Business Server nicht verfügbar.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Unterschiede zwischen Privatleitungen und primären Telefonleitungen

- Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.
    
- Für eine Privatleitung ist keine der folgenden Funktionen verfügbar: Anrufanruf, Teamanruf, Delegierung, Teamring, Gruppenanrufannahme und Reaktionsgruppe.
    
- Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf, und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.
    
- Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen "Nicht stören"-Regeln.
    
- Privatleitungen sind nur eingehende Telefone und können nicht für ausgehende Anrufe verwendet werden. Wenn ein Benutzer mit einer Privatleitung einen Anruf führt, geht der Anruf von der primären Telefonleitung des Benutzers aus und blendet den Namen des Benutzers oder die primäre Telefonnummer des Benutzers nicht vor der angerufenen Person aus.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen

- Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).
    
- Das Parken von Anrufen und die Anrufannahme funktionieren bei Privatleitungen genauso wie bei der primären Telefonleitung des Benutzers.
    
- Wenn für die primäre Telefonleitung eines Benutzers gleichzeitiges Klingeln aktiviert ist, wird es auch auf der Privatleitung aktiviert.
    
- Die Telefonnummer für eine Privatleitung wird auf die gleiche Weise im Anrufdetaildatensatz aufgezeichnet wie die Rufnummer für die primäre Telefonleitung eines Benutzers, jedoch mit dem Hinweis, dass es sich um eine private Telefonnummer handelt.
    
- Nachdem ein Benutzer einen Anruf über eine Privatleitung beantwortet hat, wird der Anruf genauso behandelt wie ein Anruf auf der primären Telefonleitung des Benutzers. Wenn beispielsweise ein Benutzer, der einen Anruf über eine Privatleitung erhält, den Anruf weiter oder andere zu einem Telefonkonferenzanruf einlä lädt, wird der Name des Benutzers in Skype for Business angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird in der Anrufer-ID angezeigt.
    
- Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. ein Mobiltelefon oder eine private Rufnummer. 
    
    > [!NOTE]
    > Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden. 
  
    > [!NOTE]
    > Anrufe von einer Konferenz an die Privatleitung haben keine  *Privatleitungsanzeige*  in der eingehenden Systembenachrichtigung.
  
## <a name="administering-private-telephone-lines"></a>Verwalten von Privatleitungen

Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.
  
> [!NOTE]
> Die Privatleitung wird in Active Directory als msRTCSIP-PrivateLine-Attribut des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut. 
  
### <a name="assigning-telephone-numbers"></a>Zuweisen von Rufnummern

 Konten für neue Benutzer, die Privatleitungen benötigen, werden auf die gleiche Weise wie Konten ohne Privatleitungen mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell erstellt.
  
Verwenden Sie das **Cmdlet "Set-CsUser"** in der Skype for Business Server-Verwaltungsshell, um einer Privatleitung für einen Benutzer eine Telefonnummer zuzuordnen, z. B. **"Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212".**
  
Telefonnummern für Privatleitungen können zwischen 3 und 15 Nummern lang sein und müssen mit dem Präfix "TEL:" beginnen. Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet. 
  
Ausführliche Informationen zu Cmdlets und der Skype for Business Server-Verwaltungsshell finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Privatleitungen in gemischten Bereitstellungen

Privatleitungen sollten nur für Bereitstellungen von Skype for Business Server oder Lync Server 2013 konfiguriert werden. In einer Bereitstellung, in der Server vorhanden sind, auf denen frühere Versionen von Lync Server ausgeführt werden, schlägt das Routing des Anrufs fehl, wenn ein Benutzer mit einer früheren Version versucht, eine Privatleitung an anruft, da der Server keine umgekehrte Nummernumschlage für eine Privatleitung durchführen kann.
  

