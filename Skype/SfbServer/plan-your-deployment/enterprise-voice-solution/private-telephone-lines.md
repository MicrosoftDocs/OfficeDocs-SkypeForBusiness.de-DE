---
title: Planen von privaten Telefonleitungen mit Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planen von privaten Telefonleitungen (sekundären) in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 527ebc75311fdab280d258c0fd7f331f78056717
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913600"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planen von privaten Telefonleitungen mit Skype für Unternehmen
 
Planen von privaten Telefonleitungen (sekundären) in Skype für Business Server Enterprise-VoIP.
  
Skype für Business Server können Sie Benutzern eine zweite private Telefonleitung neben ihren primären Telefonleitung zu erteilen. Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.
  
Private Telefonleitungen können nur mit der Skype für Business Server-Verwaltungsshell konfiguriert werden. Sie können nicht privaten Telefonleitungen mit der Skype Business Server-Systemsteuerung konfigurieren. Private Telefonleitungen sollte nur in Bereitstellungen von Skype für Business Server und nicht in gemischten Bereitstellungen konfiguriert werden.
  
## <a name="characteristics-of-private-telephone-lines"></a>Eigenschaften von Privatleitungen

Obwohl das Konzept von einem zweiten, private Telefonleitung grundlegend einfach ist, ist es wichtig zu verstehen, die Merkmale der privaten Zeilen und die Möglichkeiten, in denen ähnlich sind, und primären Telefonleitungen Benutzer unterscheidet.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Allgemeine Eigenschaften von Privatleitungen

- Ein Benutzer kann nur eine Privatleitung besitzen.
    
- Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.
    
- Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Chat-Identität). 
    
- Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung. Sie sind nicht mit gehostete Bereitstellungen von Skype für Business Server verfügbar.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Unterschiede zwischen Privatleitungen und primären Telefonleitungen

- Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.
    
- Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.
    
- Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.
    
- Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen „Nicht stören“-Regeln.
    
- Private Telefonleitungen sind nur eingehend und können nicht verwendet werden, um ausgehende Anrufe tätigen. Wenn ein Benutzer mit einer privatleitung aufruft, wird der Anruf stammt aus der primären Telefonleitung des Benutzers und wird nicht ausgeblendet, den Namen des Benutzers oder der Benutzer primäre Telefonnummer der Person, die aufgerufen.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen

- Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).
    
- Parken Sie und die Anrufannahme funktionieren bei privatleitungen genau die gleiche Weise, wie mit der primären Telefonleitung des Benutzers.
    
- Wenn die primäre Telefonleitung eines Benutzers Gleichzeitiges Klingeln aktiviert ist, ist es auch auf die privatleitung aktiviert.
    
- Die Telefonnummer für eine privatleitung ist die gleiche Weise wie die Telefonnummer für die primäre Telefonleitung eines Benutzers, wobei jedoch ein Hinweis darauf, dass es sich um eine private Telefonnummer ist in der Anruf Detaildatensatz eingetragen.
    
- Nachdem ein Benutzer behandelt Antworten, die ein Anruf auf eine privatleitung der Anruf wird als Anruf auf primäre Telefonleitung des Benutzers. Beispielsweise wenn ein Benutzer einen Anruf auf eine privatleitung empfängt den Anruf leitet oder andere Personen zu einer Telefonkonferenz eingeladen, den Namen des Benutzers in Skype für Unternehmen wird angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird angezeigt, in Anrufer-ID ein.
    
- Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. an ein Mobiltelefon oder eine private Rufnummer. 
    
    > [!NOTE]
    > Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden. 
  
    > [!NOTE]
    > Anrufen von einer Konferenz an die privatleitung haben einen Hinweis *privatleitung* nicht in der Benachrichtigung über eingehende System.
  
## <a name="administering-private-telephone-lines"></a>Verwalten von Privatleitungen

Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.
  
> [!NOTE]
> Die Privatleitung wird in Active Directory als Attribut „msRTCSIP-PrivateLine“ des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut. 
  
### <a name="assigning-telephone-numbers"></a>Zuweisen von Rufnummern

 Konten für neue Benutzer, die privatleitungen benötigen, werden in die gleiche Weise wie Konten ohne privatleitungen mit Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell erstellt.
  
Verwenden Sie das **Set-CsUser** -Cmdlet in der Skype für Business Server-Verwaltungsshell eine privatleitung für einen Benutzer eine Telefonnummer zuweisen **Set-CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.
  
Telefonnummern für den privaten Telefonleitungen kann zwischen 3 bis 15 Ziffern lang sein und muss mit der "TEL:" Präfix. Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet. 
  
Ausführliche Informationen zu Cmdlets und Skype für Business Server-Verwaltungsshell finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Privatleitungen in gemischten Bereitstellungen

Private Telefonleitungen sollte nur für die Bereitstellung von Skype für Business Server oder Lync Server 2013 konfiguriert werden. In einer Bereitstellung, in der stehen, Servern, auf denen frühere Versionen von Lync Server, wenn ein Benutzer in einer früheren Version der versucht, eine privatleitung aufrufen, fällt routing des Anrufs, da der Server eine inverssuche für eine privatleitung durchführen kann nicht aus.
  

