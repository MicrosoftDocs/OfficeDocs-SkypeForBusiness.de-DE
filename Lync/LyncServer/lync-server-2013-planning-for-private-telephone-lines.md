---
title: 'Lync Server 2013: Planen von privaten Telefonleitungen'
TOCTitle: Planen von privaten Telefonleitungen
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412728(v=OCS.15)
ms:contentKeyID: 49294895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von privaten Telefonleitungen mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-11_

In der Lync Server 2013 wird die Möglichkeit eingeführt, Benutzern zusätzlich zu ihrer primären Telefonleitung eine zweite, private Telefonleitung einzurichten. Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.

Privatleitungen können nur über die Lync Server-Verwaltungsshell konfiguriert werden. Sie können Privatleitungen nicht mit der Lync Server-Systemsteuerung konfigurieren. Privatleitungen sollten nur in Bereitstellungen von Lync Server und nicht in gemischten Bereitstellungen konfiguriert werden.

## Eigenschaften von Privatleitungen

Auch wenn das Konzept einer zweiten, privaten Telefonleitung grundsätzlich einfach zu verstehen ist, müssen Sie die Eigenschaften von Privatleitungen kennen und wissen, inwieweit sie den primären Telefonleitungen der Benutzer gleichen bzw. sich von diesen unterscheiden.

## Allgemeine Eigenschaften von Privatleitungen

  - Ein Benutzer kann nur eine Privatleitung besitzen.

  - Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.

  - Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse, und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Instant Messaging-Identität).

  - Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung. Sie sind nicht in gehosteten Bereitstellungen von Lync Server verfügbar.

## Unterschiede zwischen Privatleitungen und primären Telefonleitungen

  - Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.

  - Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.

  - Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf, und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.

  - Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen "Nicht stören"-Regeln.

  - Privatleitungen sind nur eingehend und können nicht zum Tätigen ausgehender Anrufe verwendet werden. Wenn ein Benutzer mit einer Privatleitung einen Anruf tätigt, geht der Anruf von der primären Telefonleitung des Benutzers aus. Der Benutzername oder die primäre Telefonnummer des Benutzers werden dabei nicht vor dem angerufenen Teilnehmer verborgen.

## Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen

  - Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).

  - Das Parken von Anrufen und die Anrufannahme funktionieren bei Privatleitungen genauso wie bei der primären Telefonleitung des Benutzers.

  - Wenn für die primäre Telefonleitung eines Benutzers gleichzeitiges Klingeln aktiviert ist, gilt dies auch für die Privatleitung.

  - Die Rufnummer für eine Privatleitung wird im Kommunikationsdatensatz ebenso aufgezeichnet wie die Rufnummer für die primäre Telefonleitung eines Benutzers, jedoch mit dem Hinweis, dass es sich um eine private Rufnummer handelt.

  - Nachdem ein Benutzer einen Anruf auf einer Privatleitung angenommen hat, wird der Anruf genau wie ein Anruf auf der primären Telefonleitung des Benutzers behandelt. Wenn beispielsweise ein Benutzer, der einen Anruf auf einer Privatleitung erhält, den Anruf weiterleitet oder andere zu einem Konferenzanruf einlädt, wird der Name des Benutzers in Lync 2013 angezeigt, und die Rufnummer für die primäre Telefonleitung des Benutzers wird als Anrufer-ID angezeigt.

  - Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. ein Mobiltelefon oder eine private Rufnummer.
    

    > [!NOTE]
    > Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden.

    

    > [!NOTE]
    > Anrufe von einer Konferenz an die Privatleitung werden in der eingehenden Systembenachrichtigung nicht mit dem Hinweis <EM>Privatleitung</EM> markiert.



## Verwalten von Privatleitungen

Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.


> [!NOTE]
> Die Privatleitung wird in Active Directory als msRTCSIP-PrivateLine-Attribut des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut.



## Zuweisen von Rufnummern

Konten für neue Benutzer, die Privatleitungen benötigen, werden ebenso erstellt wie Konten ohne Privatleitungen: mithilfe der Lync Server-Systemsteuerung oder der Lync Server-Verwaltungsshell.

Weisen Sie einer Privatleitung für einen Benutzer mithilfe des Cmdlets **Set-CsUser** in der Lync Server-Verwaltungsshell eine Rufnummer zu. Beispiel: **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"** .

Rufnummern für Privatleitungen können zwischen drei und fünfzehn Ziffern umfassen und müssen das Präfix "TEL:" aufweisen. Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet.

Ausführliche Informationen zu Cmdlets und die Lync Server-Verwaltungsshell finden Sie in der Dokumentation zur [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

## Privatleitungen in gemischten Bereitstellungen

Privatleitungen sollten nur in Bereitstellungen von Lync Server konfiguriert werden. In einer Bereitstellung, in der sowohl Lync Server- als auch Office Communications Server 2007- oder Office Communications Server 2007 R2-Server eingesetzt werden, tritt beim Routing des Anrufs ein Fehler auf, wenn ein Benutzer einer früheren Version eine Privatleitung anzurufen versucht, da der Server auf einer Privatleitung keine umgekehrte Nummernsuche durchführen kann.

