---
title: Konfiguration für die Integritätsüberwachung in Lync Server 2013
TOCTitle: Konfiguration für die Integritätsüberwachung in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205234(v=OCS.15)
ms:contentKeyID: 49295285
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfiguration für die Integritätsüberwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Mit den verschiedenen Websites, Microsoft Knowledge Base-Artikeln und Tools im Lync Server Resource Kit sind Administratoren, die bei der Ausführung von Lync Server auf Probleme stoßen, nie weit von einer Lösung dieser Probleme entfernt.

Es kann offensichtlich nicht ausgeschlossen werden, dass irgendwann einmal Probleme bei Lync Server 2013 auftreten, denn Lync Server kann durch viele Faktoren beeinträchtigt werden, wie z. B. Netzwerkabstürze und Hardwarefehler, die vom Produkt selbst nicht kontrolliert werden können. Durch die Implementierung der Zustandsüberwachung können Administratoren potenzielle Probleme ermitteln, bevor sie zu wirklichen Problemen werden. Beispielsweise können Administratoren mithilfe der Lync Server-Überwachung Trends und Tendenzen erkennen. So kann beispielsweise eine stete Zunahme der Anzahl von Audio-/Videokonferenzen ein Hinweis darauf sein, dass die Kapazität erhöht werden muss, um eine Überlastung des Systems zu verhindern.

Auf ähnliche Weise können Administratoren mithilfe von System Center Operations Manager beispielsweise Warnungen in Echtzeit ausstellen, wenn bestimmte Ereignisse eintreten, und synthetische Transaktionen ausführen, mit denen das System proaktiv getestet wird. Anhand synthetischer Transaktionen wird in Lync Server überprüft, ob Benutzer allgemeine Aufgaben wie z. B. das Anmelden am System, das Chatten oder das Tätigen von Anrufen im Telefonfestnetz (Public Switched Telephone Network, PSTN) erfolgreich durchführen können. Beispielsweise können Sie durch die regelmäßige Ausführung dieser Tests auf potenzielle Probleme mit Benutzern, die sich bei Lync Server anmelden, hingewiesen werden. Sie haben dann die Chance, das Problem zu beheben, bevor Ihr Supportteam mit Anrufen von Benutzern überschüttet wird, die keine Verbindung herstellen können. Durch die Verwendung von System Center Operations Manager zum Ausführen dieser synthetischen Transaktionen können Administratoren ihre Bereitstellung von Lync Server routinemäßig täglich rund um die Uhr überwachen, ohne dass dies mit viel Arbeitsaufwand verbunden ist. Sie müssen lediglich auf etwaige Warnungen reagieren.


> [!NOTE]
> Für Lync Server 2013 können mit dem Management Pack für System Center Operations Manager auch "externe" Probleme ermittelt werden, durch die Lync Server beeinträchtigt werden könnte. Beispielsweise können Administratoren benachrichtigt werden, falls Internetinformationsdienste (Internet Information Services, IIS) offline geschaltet wird, die Systemressourcen auf einem Lync Server-Computer unter einen bestimmten Wert fallen, oder falls auf einem Lync Server-Computer ein Hardwarefehler auftritt.



Die Zustandsüberwachung in Lync Server 2013 basiert auf System Center Operations Manager und der Verwendung der Lync Server Management Packs. Diese Management Packs weisen die folgenden neuen Features und Verbesserungen auf:

  - **Szenarioverfügbarkeit an jedem Standort.** Im Lync Server 2010 Management Pack wurde das Konzept der Überwachung der Szenarioverfügbarkeit für Endbenutzer durch synthetische Transaktionen eingeführt. In Lync Server 2013 weisen diese Agents mehr synthetische Transaktionen auf und können von einer Vielzahl von Standorten im Unternehmen, von entfernten geografischen Standorten außerhalb des Unternehmens, für Branch Office Appliances und für Lync Server 2010-Bereitstellungen ausgeführt werden, um Edgebereitstellungen der Vorversion abzudecken.

  - **Synthetische Transaktionsprotokolle.** Wenn bei einer synthetischen Transaktion ein Fehler auftritt, haben Administratoren Zugriff auf HTML-Protokolle, um die Ursache für den Fehler zu bestimmen. Hierzu gehört das Ermitteln der fehlgeschlagenen Aktion, die Wartezeit jeder Aktion, die zum Ausführen des Tests verwendete Befehlszeile sowie der gefundene Fehler.

  - **Höhere Anrufzuverlässigkeitsabdeckung.** Im Lync Server 2010 Management Pack wurden Anrufzuverlässigkeitswarnungen eingeführt, um schwerwiegende Konnektivitätsprobleme zu erkennen, durch die Audioanrufe von Endbenutzern beeinträchtigt werden. Die Lync Server 2013 Management Packs unterstützen nun Peer-zu-Peer-Chatnachrichten und sonstige grundlegende Konferenzfeatures, um die Abdeckung zu maximieren und gleichzeitig das Rauschen zu reduzieren.

  - **Abhängigkeitsüberwachung.** Lync Server-Szenarien können aufgrund einer Reihe von externen Faktoren fehlschlagen. Beispielsweise, weil IIS offline ist, aufgrund eingeschränkter CPU- und Arbeitsspeicherressourcen sowie aufgrund von Datenträgerproblemen. Die neuen Management Packs überprüfen mehrere kritische Abhängigkeiten, um sicherzustellen, dass sich die Administratoren über deren Auswirkungen bewusst sind.

  - **Erweiterte Berichterstellung.** Es gibt eine Reihe von Berichten, damit Administratoren die Szenarioverfügbarkeit abschätzen, die Kapazität planen sowie die Komponenten mit den meisten Problemen ermitteln können.

Die Management Packs weisen außerdem eine Reihe von Features auf, um Probleme zu erkennen und zu diagnostizieren und um eine Übersicht in Echtzeit über die Integrität Ihrer Lync Server-Bereitstellung zu erhalten. Eine Aufstellung dieser Features finden Sie in der folgenden Tabelle.

### Management Pack-Features

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Synthetische Transaktionen</p></td>
<td><p>Windows PowerShell-Cmdlets, die an verschiedenen Stellen ausgeführt werden können, um sicherzustellen, dass Endbenutzerszenarien wie z. B. Anmeldung, Anwesenheit, Chat und Konferenzen für die Endbenutzer jederzeit verfügbar sind.</p></td>
</tr>
<tr class="even">
<td><p>Warnungen zur Anrufzuverlässigkeit</p></td>
<td><p>Datenbankabfragen für Kommunikationsdatensätze (KDS). Diese Datensätze werden von Front-End-Servern geschrieben und geben an, ob Endbenutzer einen Anruf entgegennehmen konnten oder weshalb ein Anruf beendet wurde. Diese Abfragen führen zu Warnungen, wenn viele Endbenutzer Konnektivitätsprobleme bei Peer-zu-Peer-Anrufen oder einfacher Konferenzfunktionalität haben.</p></td>
</tr>
<tr class="odd">
<td><p>Warnungen zur Medienqualität</p></td>
<td><p>Datenbankabfragen für Berichte zu QoE-Daten (Quality of Experience), die von Clients am Ende jedes Anrufs veröffentlicht werden. Diese Abfragen führen zu Warnungen, die auf Szenarien hinweisen, bei denen Benutzer während Anrufen und Konferenzen wahrscheinlich eine mangelhafte Medienqualität feststellen. Die Daten basieren auf wichtigen Metriken wie z. B. Paketwartezeit und Paketverlust, die bekanntermaßen einen direkten Beitrag zur Anrufqualität leisten.</p></td>
</tr>
<tr class="even">
<td><p>Komponentenintegrität</p></td>
<td><p>Einzelne Serverkomponenten lösen mithilfe von Ereignisprotokollen und Leistungsindikatoren Warnungen aus. Diese Warnungen weisen auf Fehlerbedingungen hin, die beträchtliche negative Auswirkungen auf eines oder mehrere Endbenutzerszenarien haben können. Diese Warnungen können auch ein Hinweis auf eine Reihe anderer Fehlerbedingungen sein, wie z. B. nicht ausgeführte Dienste, hohe Fehlerraten, lange Nachrichtenwartezeiten oder Konnektivitätsprobleme.</p></td>
</tr>
<tr class="odd">
<td><p>Abhängigkeitsintegrität</p></td>
<td><p>Fehler können auf eine Reihe von externen Ursachen zurückzuführen sein. Mit den Management Packs werden nun Daten für einige der kritischen externen Abhängigkeiten überwacht und erfasst, die ein Hinweis auf schwerwiegende Probleme sein können. Beispielswiese IIS-Verfügbarkeit, CPU- und Arbeitsspeichernutzung von Servern und Prozessen sowie Datenträgermetriken.</p></td>
</tr>
</tbody>
</table>


Die vom System ausgelösten Warnungen wurden in die folgenden drei allgemeinen Kategorien unterteilt:

  - **Warnungen mit hoher Priorität.** Diese Warnungen weisen auf Bedingungen hin, die für große Benutzergruppen zu Dienstausfällen führen. Beispielsweise ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität, da Lync Server 2013 integrierte Features für hohe Verfügbarkeit aufweist. Warnungen mit hoher Priorität sind dagegen Probleme, die ernst genug sind, um "Administratoren nachts aus dem Bett zu holen". Von synthetischen Transaktionen und Offlinediensten festgestellte Ausfälle (z. B. Audio-/Videokonferenzen) gelten als Warnungen mit hoher Priorität.

  - **Warnungen mit mittlerer Priorität.**. Diese Warnungen sind ein Hinweis auf Bedingungen, die einen Teil der Benutzer betreffen, oder sie sind ein Hinweis auf eine beeinträchtigte Anrufqualität. Dies beinhaltet Probleme wie z. B. Komponentenfehler, Wartezeiten bei der Anrufverbindungsherstellung oder beeinträchtigte Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind statusbehaftet und verweisen auf den aktuellen Status des Problems. Angenommen, die Zeiten für die Anrufverbindungsherstellung überschreiten den Schwellenwert für Warnungen. Wenn die Zeiten für die Anrufverbindungsherstellung wieder den üblichen Werten entsprechen, werden diese Warnungen in System Center Operations Manager automatisch aufgelöst. Bei diesen Warnungen wird davon ausgegangen, dass sie von einem Administrator am selben Arbeitstag geprüft werden.

  - **Andere Warnungen.** Hierbei handelt es sich um Warnungen von Komponenten, die einen bestimmten Benutzer oder einen Teil der Benutzer betreffen können. Beispielsweise könnte es sein, dass der Adressbuchdienst den Active Directory-Eintrag eines bestimmten Benutzers nicht analysieren konnte. Bei diesen Warnungen wird davon ausgegangen, dass sie von Administratoren bearbeitet werden, sobald sie dafür Zeit haben.

## Inhalt dieses Abschnitts

  - [Konfigurieren von Lync Server zur Verwendung mit System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Verwenden von erweiterter Protokollierung für synthetische Transaktionen](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

