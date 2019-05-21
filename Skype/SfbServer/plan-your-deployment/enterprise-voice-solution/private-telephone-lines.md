---
title: Planen privater Telefonanschlüsse mit Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planen privater (sekundärer) Telefonleitungen in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 38dd81bb0fae9f7edd062e111db462d264dda1d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276560"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planen privater Telefonanschlüsse mit Skype for Business
 
Planen privater (sekundärer) Telefonleitungen in Skype for Business Server Enterprise-VoIP
  
Mit Skype for Business Server können Sie Benutzern zusätzlich zu Ihrer primären Telefonleitung eine zweite private Telefonleitung zur Verfügung stellen. Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.
  
Private Telefonleitungen können nur mit der Skype for Business Server-Verwaltungsshell konfiguriert werden. Mit der Skype for Business Server-Systemsteuerung können Sie keine privaten Telefonanschlüsse konfigurieren. Private Telefonleitungen sollten nur in Bereitstellungen von Skype for Business Server und nicht in gemischten Bereitstellungen konfiguriert werden.
  
## <a name="characteristics-of-private-telephone-lines"></a>Eigenschaften von Privatleitungen

Obwohl das Konzept einer zweiten privaten Telefonleitung grundlegend einfach ist, ist es wichtig, die Eigenschaften privater Linien und die Art und Weise zu verstehen, wie Sie sich von den primären Telefonleitungen der Benutzer unterscheiden.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Allgemeine Eigenschaften von Privatleitungen

- Ein Benutzer kann nur eine Privatleitung besitzen.
    
- Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.
    
- Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Chat-Identität). 
    
- Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung. Sie sind in gehosteten Bereitstellungen von Skype for Business Server nicht verfügbar.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Unterschiede zwischen Privatleitungen und primären Telefonleitungen

- Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.
    
- Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.
    
- Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.
    
- Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen „Nicht stören“-Regeln.
    
- Private Telefonleitungen sind nur eingehend und können nicht für ausgehende Anrufe genutzt werden. Wenn ein Benutzer mit einer privaten Telefonleitung einen Anruf tätigt, wird der Anruf von der primären Telefonleitung des Nutzers abgezogen und der Name des Nutzers oder die primäre Telefonnummer des Nutzers von der Person, die angerufen wird, nicht verborgen.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen

- Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).
    
- Anruf parken und Anruf Abholung arbeiten mit privaten Telefonleitungen auf die gleiche Weise wie bei der primären Telefonleitung des Benutzers.
    
- Wenn das gleichzeitige Klingeln auf der primären Telefonleitung eines Benutzers aktiviert ist, ist es auch auf der privaten Telefonleitung aktiviert.
    
- Die Telefonnummer für eine private Telefonleitung wird im Anruf Detailsatz auf die gleiche Weise wie die Telefonnummer für die primäre Telefonleitung eines Benutzers aufgezeichnet, jedoch mit dem Hinweis, dass es sich um eine private Telefonnummer handelt.
    
- Nachdem ein Nutzer einen Anruf auf einer privaten Telefonleitung beantwortet hat, wird der Anruf mit einem Anruf auf der primären Telefonleitung des Benutzers behandelt. Wenn beispielsweise ein Benutzer, der einen Anruf über eine private Telefonleitung erhält, den Anruf weiterleitet oder andere zu einem Konferenzanruf auffordert, wird der Name des Benutzers in Skype for Business angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird in der Rufnummernanzeige angezeigt.
    
- Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. an ein Mobiltelefon oder eine private Rufnummer. 
    
    > [!NOTE]
    > Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden. 
  
    > [!NOTE]
    > Anrufe von einer Konferenz an den privaten Telefonanschluss haben in der Benachrichtigung über das eingehende System keine *Privat Leitungs* Anzeige.
  
## <a name="administering-private-telephone-lines"></a>Verwalten von Privatleitungen

Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.
  
> [!NOTE]
> Die Privatleitung wird in Active Directory als Attribut „msRTCSIP-PrivateLine“ des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut. 
  
### <a name="assigning-telephone-numbers"></a>Zuweisen von Rufnummern

 Konten für neue Benutzer, die private Telefonleitungen benötigen, werden auf die gleiche Weise wie Konten ohne private Telefonleitungen erstellt, und zwar über die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell.
  
Verwenden Sie das Cmdlet " **CsUser** " in der Skype for Business Server-Verwaltungsshell, um einer privaten Telefonleitung für einen Benutzer eine Telefonnummer zuzuweisen, beispielsweise " **CsUser-Identity" SIP:Joe@Contoso.com "-Privatsphäre" Tel: + 14255551212 "**.
  
Telefonnummern für private Telefonleitungen können zwischen 3 und 15 Nummern lang sein und müssen dem Präfix "Tel:" vorangestellt werden. Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet. 
  
Details zu Cmdlets und der Skype for Business Server-Verwaltungsshell finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Privatleitungen in gemischten Bereitstellungen

Private Telefonleitungen sollten nur für die Bereitstellung von Skype for Business Server oder lync Server 2013 konfiguriert werden. In einer Bereitstellung, in der es Server gibt, auf denen frühere Versionen von lync Server ausgeführt werden, wenn ein Benutzer mit einer früheren Version versucht, eine private Telefonleitung anzurufen, schlägt das Routing des Anrufs fehl, da der Server keine umgekehrte Nummernsuche auf einer privaten Telefonleitung durchführen kann.
  

