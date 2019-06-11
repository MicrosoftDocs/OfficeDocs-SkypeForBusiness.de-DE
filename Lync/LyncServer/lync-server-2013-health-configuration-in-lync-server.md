---
title: 'Lync Server 2013: Integritäts Konfiguration in lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Integritäts Konfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Zwischen verschiedenen Websites, Microsoft Knowledge Base-Artikeln und lync Server Resource Kit-Tools sind Administratoren, die Probleme bei der Ausführung von lync Server haben, nie weit davon entfernt, diese Probleme zu lösen.

Es gibt natürlich keine Möglichkeit, sicherzustellen, dass Sie nie Probleme mit lync Server 2013 haben, da lync Server von vielen Dingen wie Netzwerk abstürzen und Hardwarefehlern betroffen sein kann, die das Produkt selbst nicht kontrollieren kann. Durch die Implementierung der Integritätsüberwachung können Administratoren potenzielle Probleme erkennen, bevor Sie zu tatsächlichen Problemen werden. Administratoren können beispielsweise mithilfe der lync Server-Überwachung Trends und Tendenzen erkennen. Eine stetige Zunahme der Anzahl von Audio-und Videokonferenzen könnte beispielsweise darauf hindeuten, dass Kapazität hinzugefügt werden muss, bevor das System überladen wird.

Auf ähnliche Weise können Administratoren System Center Operations Manager verwenden, um in Echtzeit Warnungen zu erhalten, wenn bestimmte Ereignisse auftreten, und synthetische Transaktionen auszuführen, die das System proaktiv testen. Synthetische Transaktionen werden in lync Server verwendet, um sicherzustellen, dass Benutzer häufige Aufgaben wie die Anmeldung am System, den Austausch von Sofortnachrichten oder Anrufe an ein Telefon im öffentlichen Telefonnetz (PSTN) erfolgreich durchführen können. So können Sie beispielsweise in regelmäßigen Abständen mithilfe dieser Tests auf mögliche Probleme bei der Anmeldung von Benutzern bei lync Server hingewiesen werden, und Sie erhalten eine Möglichkeit, das Problem zu beheben, bevor das Support Team mit Anrufen von Benutzern überflutet wird, die keine Verbindung herstellen können. Durch die Verwendung von System Center Operations Manager zum Ausführen dieser synthetischen Transaktionen können Administratoren ihre Bereitstellung von lync Server täglich 24 Stunden lang kontinuierlich überwachen, ohne vieles mehr zu tun, als auf Warnungen zu reagieren, die möglicherweise ausgestellt werden.

<div>


> [!NOTE]  
> Für lync Server 2013 ist das Management Pack für System Center Operations Manager auch in der Lage, "externe" Probleme zu erkennen, die sich negativ auf lync Server auswirken können. Beispielsweise können Administratoren benachrichtigt werden, wenn Internet Informationsdienste (IIS) offline geschaltet werden, Systemressourcen auf einem lync Server-Computer unter einen bestimmten Betrag fallen oder ein Hardwarefehler bei einem lync Server-Computer auftritt.



</div>

Die Integritäts Konfiguration in lync Server 2013 basiert auf System Center Operations Manager und der Verwendung von lync Server-Verwaltungs Paketen. Diese Management Packs umfassen eine Reihe neuer Features und Verbesserungen, einschließlich:

  - **Verfügbarkeit von Szenarien von einem beliebigen Ort aus.** Das lync Server 2010-Management Pack hat das Konzept der Überwachung der Verfügbarkeit von Endbenutzerszenarien mit synthetischen Transaktionen eingeführt. In lync Server 2013 verfügen diese Agents über mehr synthetische Transaktionen und können von einer Vielzahl von Speicherorten innerhalb des Unternehmens, von Remote-geografischen Standorten außerhalb des Unternehmens, mit Zweigstellen-Appliances und gegen lync Server 2010 ausgeführt werden. Bereitstellungen zum Hinzufügen von Coverage zu Legacy Edge-Bereitstellungen

  - **Synthetische Transaktionsprotokolle.** Wenn eine synthetische Transaktion fehlschlägt, können Administratoren auf HTML-Protokolle zugreifen, um zu ermitteln, welche Fehler aufgetreten sind. Dies umfasst das Verständnis der fehlgeschlagenen Aktion, die Latenz der einzelnen Aktionen, die für die Ausführung des Tests verwendete Befehlszeile und der aufgetretene Fehler.

  - **Erhöhte Anruf Zuverlässigkeit.** Das lync Server 2010-Management Pack führte zu einer Anruf Zuverlässigkeits Warnung, um schwerwiegende Verbindungsprobleme zu erkennen, die sich auf die Audioanrufe von Endbenutzern auswirken. Die lync Server 2013-Verwaltungspakete bieten eine Abdeckung für Peer-to-Peer-Instant Messaging (im) und andere grundlegende Konferenzfeatures, um die Abdeckung zu maximieren und gleichzeitig Rauschen zu verringern.

  - **Abhängigkeitsüberwachung.** Lync Server-Szenarien können aufgrund einer Vielzahl externer Faktoren, wie IIS offline, begrenzte CPU-und Speicherressourcen sowie Datenträgerprobleme, fehlschlagen. Die neuen Management Packs überprüfen verschiedene kritische Abhängigkeiten, um sicherzustellen, dass Administratoren sich ihrer Auswirkungen bewusst sind.

  - **Verbesserte Berichterstellung.** Eine Reihe von Berichten, die Administratoren dabei helfen, die Verfügbarkeit von Szenarien zu schätzen, Kapazitätspläne zu planen und zu sehen, welche Komponenten die meisten Probleme auftreten.

Die Management Packs beinhalten auch eine Reihe von Funktionen, die Ihnen helfen, den Status Ihrer lync Server-Bereitstellung in Echtzeit zu erkennen und zu diagnostizieren. Diese Features sind in der folgenden Tabelle aufgelistet.

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
<td><p>Windows PowerShell-Cmdlets, die von verschiedenen Speicherorten aus ausgeführt werden können, um sicherzustellen, dass Endbenutzerszenarien wie Anmeldung, Anwesenheit, Chat und Konferenz problemlos für Endbenutzer verfügbar sind.</p></td>
</tr>
<tr class="even">
<td><p>Benachrichtigungen zur Anruf Zuverlässigkeit</p></td>
<td><p>Datenbankabfragen für Anruf Detail Datensätze (CDR). Diese Einträge werden von Front-End-Servern geschrieben, um zu reflektieren, ob Endbenutzer eine Verbindung mit einem Anruf herstellen konnten oder warum ein Anruf beendet wurde. Diese Abfragen führen zu Warnungen, die angeben, dass für eine breite Palette von Endbenutzern Verbindungsprobleme für Peer-to-Peer-Anrufe oder einfache Konferenzfunktionen auftreten.</p></td>
</tr>
<tr class="odd">
<td><p>Benachrichtigungen über Medienqualität</p></td>
<td><p>Datenbankabfragen, die die von Kunden am Ende jedes Anrufs veröffentlichten QoE-Berichte (Quality of Experience) anzeigen. Diese Abfragen führen zu Warnungen, in denen Szenarien lokalisiert werden, in denen Benutzer bei Anrufen und Konferenzen wahrscheinlich eine schlechte Medienqualität aufweisen. Die Daten basieren auf wichtigen Metriken wie Paket Latenz und-Verlust, Metriken, die bekanntermaßen direkt zur Anrufqualität beitragen.</p></td>
</tr>
<tr class="even">
<td><p>Komponentenstatus</p></td>
<td><p>Einzelne Server Komponenten lösen Warnungen mithilfe von Ereignisprotokollen und Leistungsindikatoren aus. Diese Warnungen zeigen Fehlerbedingungen an, die ein oder mehrere Endbenutzerszenarien stark beeinträchtigen können. Diese Benachrichtigungen können auch auf eine Vielzahl anderer Fehlerbedingungen hinweisen, einschließlich der nicht ausgeführten Dienste, der großen Fehlerraten, der großen Nachrichtenlatenz oder der Verbindungsprobleme.</p></td>
</tr>
<tr class="odd">
<td><p>Abhängigkeitsstatus</p></td>
<td><p>Fehler können aus verschiedenen externen Gründen auftreten. Die Management Packs überwachen und sammeln nun Daten für einige der wichtigen externen Abhängigkeiten, die möglicherweise auf schwerwiegende Probleme hindeuten, einschließlich IIS-Verfügbarkeit, CPU-und Speicherauslastung von Servern und Prozessen sowie Datenträger Metrik.</p></td>
</tr>
</tbody>
</table>


Die vom System ausgestellten Benachrichtigungen wurden in drei allgemeine Kategorien unterteilt:

  - **Benachrichtigungen mit hoher Priorität.** Diese Warnungen weisen auf Bedingungen hin, die zu Dienstunterbrechungen für große Benutzergruppen führen können. Beispielsweise ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität, da lync Server 2013 integrierte Funktionen für hohe Verfügbarkeit besitzt. Stattdessen stellen Benachrichtigungen mit hoher Priorität Probleme dar, die schwerwiegend genug sind, um Administratoren nachts zu wecken. Ausfälle, die von synthetischen Transaktionen und Offline Diensten (beispielsweise Audio/Videokonferenzen) erkannt werden, werden als Benachrichtigungen mit hoher Priorität angezeigt.

  - **Benachrichtigungen mit mittlerer Priorität.**. Diese Benachrichtigungen deuten auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken oder auf die Verschlechterung der Anrufqualität hindeuten. Dazu gehören Probleme wie Komponentenausfälle, Latenz in der Anrufeinrichtung oder beeinträchtigte Audioqualität bei anrufen. Benachrichtigungen in dieser Kategorie sind Stateful und geben den aktuellen Status des Problems an. Nehmen wir beispielsweise an, dass Ihre Anrufzeiten den Warnungsschwellenwert überschreiten. Wenn die Zeiten der Anrufeinrichtung wieder normal sind, werden diese Benachrichtigungen in System Center Operations Manager automatisch aufgelöst. Die Erwartung für diese Benachrichtigungen liegt darin, dass ein Administrator Sie am gleichen Arbeitstag ansieht.

  - **Andere Benachrichtigungen.** Hierbei handelt es sich um Warnungen von Komponenten, die sich auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken können. Beispielsweise konnte der Adressbuchdienst den Active Directory-Eintrag eines bestimmten Benutzers nicht analysieren. Die Erwartung für diese Benachrichtigungen liegt darin, dass Administratoren darauf zugreifen können, wenn Ihnen Zeit zur Verfügung steht.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Verwenden von Microsoft SQL Server 2008 R2 als Ihre System Center Operations Manager-Datenbank für lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

