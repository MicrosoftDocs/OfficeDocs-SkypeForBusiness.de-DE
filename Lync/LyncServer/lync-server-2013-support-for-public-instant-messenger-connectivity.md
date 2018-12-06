---
title: Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013
TOCTitle: Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59373612
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

## Unterstützen von Verbindungen mit öffentlichen Instant Messaging-Diensten

Dieser Artikel enthält Informationen zur Unterstützung der Verbindung zu öffentlichen Instant Messaging-Diensten (Public IM Connectivity, PIC). PIC ist ein Feature von Microsoft Lync, mit dem Organisation ihren Lync-Benutzern gestatten können, mit ihren Lync-Clients und Identitäten die Verbindung zu Benutzern in bestimmten öffentlichen Instant Messaging-Diensten herzustellen.

Die Endbenutzer profitieren von der Möglichkeit, zu ihren Bedingungen mit Kunden, Partnern und Lieferanten kommunizieren zu können, und die IT-Abteilung profitiert von der Unterstützung eines einzigen Clients für die Kommunikation in Echtzeit, während die gleichzeitig die Steuerungs-, Konformitäts- und Archivierungsfunktionen von Lync nutzen kann. Die Lync-Skype-Konnektivität, die [seit Mai 2013 allgemein verfügbar](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx) ist, setzt auf die alten Funktionen auf, die unter Lync/Office Communications Server (OCS)/Live Communications Server (LCS) mit PIC für die Herstellung der Verbindung zu MSN/Windows Live, AOL, and Yahoo genutzt wurden. Weitere Informationen zur Lync-Skype-Konnektivität finden Sie unter [Lync-Skype-Konnektivität](http://office.microsoft.com/de-de/lync/lync-skype-connectivity-fx103789635.aspx). Der Partnerverbund mit Windows Live, AOL und Yahoo wird demnächst eingestellt. Auf dieser Seite wird der Status des jeweiligen Diensts dokumentiert.

Zur Nutzung von PIC mussten die Kunden den Dienst für jeden öffentlichen Instant Messaging-Anbieter aktivieren. Die Anforderungen und detaillierten Vorgehensweisen sind vom jeweiligen Instant Messaging-Anbieter und dem vom Kunden geschlossenen Lizenzprogramm abhängig.

## Windows Live Messenger

Microsoft hat Windows Live Messenger und Skype zusammengeführt. Seit April 2013 werden Messenger-Kunden bei der Anmeldung nach Skype migriert. Lync-Kunden, die den Partnerverbund über Messenger nutzen, können weiterhin mit ihren Messenger-Kontakten kommunizieren, auch nachdem diese Kontakte auf Skype aktualisiert haben. Weder Lync-Administratoren noch Lync-Endbenutzer müssen irgendetwas tun, um den Fortbestand des Diensts sicherzustellen, und die Verwaltung dieser Funktion in Lync ist die gleiche wie die Verwaltung der Kommunikation mit Messenger.

Wenn sich Messenger-Benutzer mit ihren Microsoft-Konten (d. h. mit den gleichen Anmeldeinformationen wie für Messenger) bei Skype anmelden, werden alle Messenger-Kontakte einschließlich der Lync-Partnerverbundkontakte nach Skype migriert. Anschließend ist der Austausch von Anwesenheitsinformationen und Chatnachrichten zwischen Skype und Lync mit diesen Kontakte möglich.

Die Lync-Skype-Konnektivität, d. h. das Hinzufügen von Kontakten, der Austausch von Anwesenheitsinformationen, Chatnachrichten und Audioanrufe zwischen Lync- und Skype-Benutzer steht nun auch für alle Lync-Benutzer zur Verfügung.

## Yahoo\! und AOL Instant Messenger

Für Kunden von Lync (und Office Communications Server) wird der Partnerverbund mit Yahoo\! und AOL demnächst eingestellt. Die Fähigkeit von Microsoft, diese beiden Dienste bereitzustellen, war von der Unterstützung durch Yahoo\! und AOL abhängig, und die dieser Unterstützung zugrunde liegenden Vereinbarungen laufen demnächst aus. Der Dienst wird sowohl für Yahoo\! als auch für AOL noch bis Juni 2014 bereitgestellt.

  - **Yahoo\!:** Der Dienst wird bis Juni 2014 weiterhin bereitgestellt, und Kunden benötigen weiterhin eine Microsoft Lync PIC USL (Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten). Seit dem 1. September 2012 kann die PIC USL nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit Lizenzen, die vor diesem Datum erworben wurden, können den Partnerverbund mit Yahoo\! weiterhin nutzen, bis der Dienst entweder eingestellt wird oder die Lizenz abläuft. Lesen Sie [die Ankündigung](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) im Lync-Teamblog. Kunden mit PIC-Lizenzen aus Verträgen, die über den 30. Juni 2014 hinaus gültig sind, erhalten eine anteilige Gutschrift für bereits geleistete Zahlungen, die über den 30. Juni 2014 hinausgehen.

  - **AOL:** Ab dem 30. Juni 2014 steht der Lync-Konnektivitätsdienst zur Herstellung der Verbindung zu Anbietern von öffentlichen Instant Messaging-Diensten nicht mehr zur Verfügung. Um das Ausmaß der Störungen bei den Kunden möglichst gering zu halten, wurde die Bereitstellung weiterer Kundendomänen bereits eingestellt. Bis zum 30. Juni 2014 müssen die Kunden nichts unternehmen, um die Kommunikation im Partnerverbund mit AIM fortzusetzen. Nach diesem Datum (oder für Kunden, die in der Zwischenzeit weitere Domänen bereitstellen möchten) steht ein Ersatzdienst direkt von AOL zur Verfügung. Weitere Informationen zu dem neuen Dienst von AOL finden Sie unter [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php) (mit diesem Link wird eine neue Seite auf AOL.com geöffnet).  

## Anbieter von öffentlichen Instant Messaging-Diensten – Zusammenfassung

Die folgende Tabelle enthält eine Zusammenfassung der Anbieter von öffentlichen Instant Messaging-Diensten, der Funktionen für den Partnerverbund mit Lync und der Lizenzierungsanforderungen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anbieter von öffentlichen Instant Messaging-Diensten</th>
<th>Funktionen für den Partnerverbund</th>
<th>Lizenzierungsanforderungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Chat, Anwesenheitsinformationen, Audio</p></td>
<td><p>Lync Server-Clientzugriffslizenzen, Lync Online-Pläne 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Chat, Anwesenheitsinformationen, Audio/Video</p></td>
<td><p>Lync Server-Clientzugriffslizenzen (werden solange unterstützt, wie WLM noch auf dem Markt ist)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Chat, Anwesenheitsinformationen</p></td>
<td><p>Lync Server-Clientzugriffslizenzen; werden bis Juni 2014 für Bestandskunden unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Chat, Anwesenheitsinformationen</p></td>
<td><p>Setzt neben den Lync Server-Clientzugriffslizenzen eine Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten (&quot;PIC USL&quot;) voraus. Ab der Preisliste vom September 2012 steht die PIC USL nicht mehr zum Verkauf. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst am 30. Juni 2014 eingestellt wird.</p></td>
</tr>
</tbody>
</table>

