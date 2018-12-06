---
title: 'Lync Server 2013: Neue Funktionen der Reaktionsgruppenanwendung'
TOCTitle: Neue Funktionen der Reaktionsgruppenanwendung
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398373(v=OCS.15)
ms:contentKeyID: 49294048
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen der Reaktionsgruppenanwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Mithilfe der Reaktionsgruppenanwendung können Sie eingehende Anrufe an benannte Personen mit speziellen Aufgabenbereichen weiterleiten – z. B. an den Kundendienst, ein internes Helpdesk oder die allgemeine Telefonunterstützung für eine Abteilung – oder den Anruf in der Warteschleife platzieren.

Die folgenden Funktionen der Reaktionsgruppenanwendung sind neu in Lync Server 2013:

  - **Manager-Rolle**
    
    In Lync Server 2013 wird eine neue Reaktionsgruppe Manager-Rolle eingeführt. Damit sind nun zwei Verwaltungsrollen für Reaktionsgruppen vorhanden: Reaktionsgruppe-Manager und Reaktionsgruppe-Administrator. Reaktionsgruppe-Administratoren können weiterhin alle Elemente für alle Reaktionsgruppen konfigurieren, Manager können dagegen nur bestimmte Elemente für Reaktionsgruppen in ihrem Besitz konfigurieren.
    
    Dies stellt – insbesondere mit Blick auf umfangreiche Bereitstellungsszenarien – eine Verbesserung im Verwaltungsmodell bezüglich der Skalierbarkeit von Reaktionsgruppen dar.

  - **Hochverfügbarkeit**
    
    Die Unterstützung hoher Verfügbarkeit für die Reaktionsgruppenanwendung durch SQL Server-Spiegelung wird im Rahmen der allgemeinen Konfiguration und der Bereitstellung hoher Verfügbarkeit für Lync Server 2013 aktiviert. Wenn Sie Ihre Konfiguration auf hohe Verfügbarkeit auslegen und es zu einer Unterbrechung der Verbindung zum primären Back-End-Server kommt, ist die Reaktionsgruppenfunktion davon nicht beeinträchtigt, weil auf einen gespiegelten Back-End-Server zugegriffen werden kann.
    
    Die Unterstützung der SQL Server-Spiegelung von Reaktionsgruppenanwendung kann nicht außerhalb bzw. unabhängig von der gesamten Konfiguration für hohe Verfügbarkeit von Lync Server 2013 aktiviert oder konfiguriert werden.

  - **Notfallwiederherstellung**
    
    In Reaktionsgruppenanwendung wird die Unterstützung der Notfallherstellung im Rahmen der Konfiguration und der Bereitstellung der kombinierten Front-End-Pools aktiviert, die Teil der gesamten Konfiguration für die Notfallwiederherstellung von Lync Server 2013 sind. Darüber hinaus unterstützen die Cmdlets der Reaktionsgruppe den Failoverprozess zum Sicherungspool sowie den Failbackprozess zum primären oder zu einem neuen Pool. Bei einem Ausfall des primären Pools kann für die Reaktionsgruppen ein Failover zum Sicherungspool durchgeführt werden, und nach der Wiederherstellung kann ein Failback zum primären oder zu einem neuen Pool durchgeführt werden.

## Siehe auch

#### Weitere Ressourcen

[Planen von Reaktionsgruppen in Lync Server 2013](lync-server-2013-planning-for-response-groups.md)

