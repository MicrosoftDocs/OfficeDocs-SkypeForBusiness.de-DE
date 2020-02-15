---
title: 'Lync Server 2013: Integritäts Konfiguration in lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831dd021799f658ae9ce332935ff2381e5d79bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Integritäts Konfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Zwischen verschiedenen Websites, Microsoft Knowledge Base-Artikeln und lync Server Resource Kit-Tools sind Administratoren, die bei der Ausführung von lync Server auf Probleme stoßen, nie weit weg, um diese Probleme zu lösen.

Offensichtlich gibt es keine Möglichkeit sicherzustellen, dass Probleme mit lync Server 2013 nie auftreten, da lync Server von vielen Dingen wie Netzwerk abstürzen und Hardwarefehlern betroffen sein können, die das Produkt selbst nicht steuern kann. Durch die Implementierung der Zustandsüberwachung können Administratoren potenzielle Probleme ermitteln, bevor sie zu wirklichen Problemen werden. Administratoren können beispielsweise die lync Server Überwachung verwenden, um Trends und Tendenzen zu identifizieren. So kann beispielsweise eine stete Zunahme der Anzahl von Audio-/Videokonferenzen ein Hinweis darauf sein, dass die Kapazität erhöht werden muss, um eine Überlastung des Systems zu verhindern.

Auf ähnliche Weise können Administratoren System Center Operations Manager verwenden, um beim Auftreten bestimmter Ereignisse Echtzeitwarnungen auszugeben und synthetische Transaktionen auszuführen, mit denen das System proaktiv getestet wird. Synthetische Transaktionen werden in lync Server verwendet, um sicherzustellen, dass Benutzer allgemeine Aufgaben wie das Anmelden am System, das Austauschen von Chatnachrichten oder das Telefonieren von Anrufen im öffentlichen Telefonnetz (PSTN) erfolgreich ausführen können. Beispielsweise können Sie diese Tests regelmäßig ausführen, um potenzielle Probleme mit Benutzern bei der Anmeldung bei lync Server zu warnen, und Sie haben die Möglichkeit, das Problem zu beheben, bevor Ihr Support Team mit Anrufen von Benutzern überflutet wird, die keine Verbindung herstellen können. Durch die Verwendung von System Center Operations Manager zur Ausführung dieser synthetischen Transaktionen können Administratoren die Bereitstellung von lync Server routinemäßig 24 Stunden lang kontinuierlich überwachen, ohne vieles mehr tun zu müssen, als auf Warnungen zu reagieren, die möglicherweise ausgestellt werden.

<div>


> [!NOTE]  
> Für lync Server 2013 kann das Management Pack für System Center Operations Manager auch "externe" Probleme erkennen, die sich negativ auf lync Server auswirken können. Administratoren können beispielsweise benachrichtigt werden, wenn Internet Information Services (IIS) offline geht, Systemressourcen auf einem lync Server Computer unter einen bestimmten Betrag fallen oder wenn ein lync Server Computer einen Hardwarefehler auftritt.



</div>

Die Integritäts Konfiguration in lync Server 2013 ist um System Center Operations Manager und die Verwendung von lync Server Management Packs aufgebaut. Diese Management Packs weisen die folgenden neuen Features und Verbesserungen auf:

  - **Szenarioverfügbarkeit an jedem Standort.** Mit dem lync Server 2010 Management Pack wurde das Konzept der Überwachung der Verfügbarkeit von Endbenutzerszenarien mit synthetischen Transaktionen eingeführt. In lync Server 2013 haben diese Agents mehr synthetische Transaktionen und können an einer Vielzahl von Standorten innerhalb des Unternehmens, von Remote geografischen Standorten außerhalb des Unternehmens, gegenüber Zweigstellengeräten und gegen lync Server 2010 ausgeführt werden. Bereitstellungen zum Hinzufügen von Abdeckung zu Legacy-Edge-Bereitstellungen.

  - **Synthetische Transaktionsprotokolle.** Wenn bei einer synthetischen Transaktion ein Fehler auftritt, haben Administratoren Zugriff auf HTML-Protokolle, um die Ursache für den Fehler zu bestimmen. Hierzu gehört das Ermitteln der fehlgeschlagenen Aktion, die Wartezeit jeder Aktion, die zum Ausführen des Tests verwendete Befehlszeile sowie der gefundene Fehler.

  - **Höhere Anrufzuverlässigkeitsabdeckung.** Mit dem lync Server 2010 Management Packs wurde die Anruf Zuverlässigkeits Warnung zur Erkennung schwerer Verbindungsprobleme eingeführt, die sich auf die Audioanrufe von Endbenutzern auswirken. Die lync Server 2013 Management Packs bieten eine Abdeckung für Peer-zu-Peer-Sofortnachrichten (Instant Messaging) und andere grundlegende Konferenzfunktionen zur Maximierung der Reichweite bei gleichzeitiger Reduzierung des Rauschens.

  - **Abhängigkeitsüberwachung.** Lync Server Szenarien können aufgrund einer Vielzahl externer Faktoren wie IIS offline, CPU-und Arbeitsspeicherressourcen sowie Datenträgerproblemen fehlschlagen. Die neuen Management Packs überprüfen mehrere wichtige Abhängigkeiten, um sicherzustellen, dass Administratoren ihre Auswirkungen kennen.

  - **Erweiterte Berichterstellung.** Es gibt eine Reihe von Berichten, damit Administratoren die Szenarioverfügbarkeit abschätzen, die Kapazität planen sowie die Komponenten mit den meisten Problemen ermitteln können.

Die Management Packs enthalten auch eine Vielzahl von Funktionen, die Ihnen bei der Erkennung und Diagnose zur Verfügung stehen, um in Echtzeit einen Einblick in die Integrität ihrer lync Server Bereitstellung zu geben. Eine Aufstellung dieser Features finden Sie in der folgenden Tabelle.

### <a name="management-pack-features"></a>Management Pack-Features

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
<td><p>Windows PowerShell-Cmdlets, die von verschiedenen Standorten aus ausgeführt werden können, um sicherzustellen, dass Endbenutzerszenarien wie Anmeldung, Anwesenheitsinformationen, Chatnachrichten und Konferenzen bereit stehen.</p></td>
</tr>
<tr class="even">
<td><p>Warnungen zur Anrufzuverlässigkeit</p></td>
<td><p>Datenbankabfragen für Kommunikationsdatensätze (KDS). Diese Einträge werden von Front-End-Servern geschrieben, um zu reflektieren, ob Endbenutzer eine Verbindung mit einem Anruf herstellen konnten oder warum ein Anruf beendet wurde. Diese Abfragen führen zu Warnungen, wenn viele Endbenutzer Konnektivitätsprobleme bei Peer-zu-Peer-Anrufen oder einfacher Konferenzfunktionalität haben.</p></td>
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
<td><p>Fehler können aus einer Vielzahl von externen Gründen auftreten. Die Management Packs überwachen und erfassen nun Daten für einige der wichtigen externen Abhängigkeiten, die auf schwerwiegende Probleme hindeuten können, einschließlich der Verfügbarkeit von IIS, der CPU-und Speicherauslastung von Servern und Prozessen sowie Datenträger Metriken.</p></td>
</tr>
</tbody>
</table>


Die vom System ausgelösten Warnungen wurden in die folgenden drei allgemeinen Kategorien unterteilt:

  - **Warnungen mit hoher Priorität.** Diese Warnungen weisen auf Bedingungen hin, die für große Benutzergruppen zu Dienstausfällen führen. Beispielsweise ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität, da lync Server 2013 über integrierte Features für hohe Verfügbarkeit verfügt. Warnungen mit hoher Priorität sind dagegen Probleme, die ernst genug sind, um "Administratoren nachts aus dem Bett zu holen". Von synthetischen Transaktionen und Offlinediensten festgestellte Ausfälle (z. B. Audio-/Videokonferenzen) gelten als Warnungen mit hoher Priorität.

  - **Warnungen mittlerer Priorität.**. Diese Warnungen sind ein Hinweis auf Bedingungen, die einen Teil der Benutzer betreffen, oder sie sind ein Hinweis auf eine beeinträchtigte Anrufqualität. Dies beinhaltet Probleme wie z. B. Komponentenfehler, Wartezeiten bei der Anrufverbindungsherstellung oder beeinträchtigte Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind statusbehaftet und verweisen auf den aktuellen Status des Problems. Angenommen, die Zeiten für die Anrufverbindungsherstellung überschreiten den Schwellenwert für Warnungen. Wenn die Anruf Erstellungszeiten wieder normal sind, werden diese Warnungen automatisch in System Center Operations Manager aufgelöst. Bei diesen Warnungen wird davon ausgegangen, dass sie von einem Administrator am selben Arbeitstag geprüft werden.

  - **Andere Warnungen.** Hierbei handelt es sich um Warnungen von Komponenten, die einen bestimmten Benutzer oder einen Teil der Benutzer betreffen können. Beispielsweise könnte es sein, dass der Adressbuchdienst den Active Directory-Eintrag eines bestimmten Benutzers nicht analysieren konnte. Bei diesen Warnungen wird davon ausgegangen, dass sie von Administratoren bearbeitet werden, sobald sie dafür Zeit haben.

<div>

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

  - [Konfigurieren lync Server 2013 für die Verwendung mit System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank für lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

