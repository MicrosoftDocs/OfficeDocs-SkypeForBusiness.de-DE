---
title: 'Lync Server 2013: Planen privater Telefonleitungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4287e4b80b146e26fe5e548c07e5df189b1960e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Planen privater Telefonleitungen mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-11_

Lync Server 2013 führt die Möglichkeit ein, Benutzern zusätzlich zu Ihrer primären Telefonleitung eine zweite private Telefonleitung zur Verfügung zu stellen. Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.

Private Telefonleitungen können nur mit der lync Server-Verwaltungsshell konfiguriert werden. Mit der lync Server-Systemsteuerung können keine privaten Telefonanschlüsse konfiguriert werden. Private Telefonleitungen sollten nur in Bereitstellungen von lync Server und nicht in gemischten Bereitstellungen konfiguriert werden.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Eigenschaften von Privatleitungen

Auch wenn das Konzept einer zweiten, privaten Telefonleitung grundsätzlich einfach zu verstehen ist, müssen Sie die Eigenschaften von Privatleitungen kennen und wissen, inwieweit sie den primären Telefonleitungen der Benutzer gleichen bzw. sich von diesen unterscheiden.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Allgemeine Eigenschaften von Privatleitungen

  - Ein Benutzer kann nur eine Privatleitung besitzen.

  - Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.

  - Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Chat-Identität).

  - Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung. Sie sind für gehostete Bereitstellungen von lync Server nicht verfügbar.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Unterschiede zwischen Privatleitungen und primären Telefonleitungen

  - Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.

  - Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.

  - Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.

  - Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen „Nicht stören“-Regeln.

  - Privatleitungen sind nur eingehend und können nicht zum Tätigen ausgehender Anrufe verwendet werden. Wenn ein Benutzer mit einer Privatleitung einen Anruf tätigt, geht der Anruf von der primären Telefonleitung des Benutzers aus. Der Benutzername oder die primäre Telefonnummer des Benutzers wird dabei nicht vor dem angerufenen Teilnehmer verborgen.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen

  - Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).

  - Das Parken von Anrufen und die Anrufannahme funktionieren bei Privatleitungen genauso wie bei der primären Telefonleitung des Benutzers.

  - Wenn für die primäre Telefonleitung eines Benutzers gleichzeitiges Klingeln aktiviert ist, gilt dies auch für die Privatleitung.

  - Die Rufnummer für eine Privatleitung wird im Kommunikationsdatensatz ebenso aufgezeichnet wie die Rufnummer für die primäre Telefonleitung eines Benutzers, jedoch mit dem Hinweis, dass es sich um eine private Rufnummer handelt.

  - Nachdem ein Benutzer einen Anruf auf einer Privatleitung angenommen hat, wird der Anruf genau wie ein Anruf auf der primären Telefonleitung des Benutzers behandelt. Wenn beispielsweise ein Benutzer, der einen Anruf über eine private Telefonleitung erhält, den Anruf weiterleitet oder andere zu einem Konferenzanruf auffordert, wird der Name des Benutzers in lync 2013 angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird in der Rufnummernanzeige angezeigt.

  - Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. an ein Mobiltelefon oder eine private Rufnummer.
    
    <div>
    

    > [!NOTE]  
    > Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Anrufe von einer Konferenz an die Privatleitung werden in der eingehenden Systembenachrichtigung nicht mit dem Hinweis <EM>Privatleitung</EM> markiert.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Verwalten von Privatleitungen

Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.

<div>


> [!NOTE]  
> Die Privatleitung wird in Active Directory als Attribut „msRTCSIP-PrivateLine“ des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Zuweisen von Rufnummern

Konten für neue Benutzer, die private Telefonleitungen benötigen, werden auf die gleiche Weise wie Konten ohne private Telefonleitungen erstellt, und zwar mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell.

Verwenden Sie das Cmdlet " **CsUser** " in der lync Server-Verwaltungsshell, um einer privaten Telefonleitung für einen Benutzer eine Telefonnummer zuzuweisen, beispielsweise " **CsUser-Identity" SIP:Joe@Contoso.com "-Privatsphäre" Tel: + 14255551212 "**.

Telefonnummern für private Telefonleitungen können zwischen 3 und 15 Nummern lang sein und müssen dem Präfix "Tel:" vorangestellt werden. Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet.

Details zu Cmdlets und zur lync Server-Verwaltungsshell finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Privatleitungen in gemischten Bereitstellungen

Private Telefonleitungen sollten nur für Bereitstellungen von lync Server konfiguriert werden. Bei einer Bereitstellung, bei der sowohl lync Server-als auch Office Communications Server 2007-oder Office Communications Server 2007 R2-Server vorhanden sind, schlägt das Routing des Anrufs fehl, da der Server bei einer früheren Version versucht, eine private Telefonleitung anzurufen Führen Sie eine Reverse-Number-Suche auf einem privaten Telefonanschluss durch.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

