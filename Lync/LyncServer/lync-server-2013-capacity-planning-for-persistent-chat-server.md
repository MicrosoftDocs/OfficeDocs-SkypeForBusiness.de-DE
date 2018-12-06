---
title: 'Lync Server 2013: Kapazitätsplanung für den Server für beständigen Chat'
TOCTitle: Kapazitätsplanung für den Server für beständigen Chat
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615006(v=OCS.15)
ms:contentKeyID: 49294490
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kapazitätsplanung für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Server für beständigen Chat kann ein Echtzeit-Chat mit mehreren Benutzern ausgeführt werden, für den eine spätere Wiederaufnahme und Suche möglich ist. Im Gegensatz zu Gruppenchats, die – falls ein Unterhaltungsverlauf konfiguriert ist – im Postfach des Benutzers gespeichert werden, bleibt eine Server für beständigen Chat-Sitzung länger geöffnet, und der Inhalt wird gemeinsam mit den Nachrichten, Dateien, URLs und anderen Daten, die Teil einer fortlaufenden Unterhaltung sind, auf einem Server gespeichert.

Wenn Sie die Bereitstellung von Server für beständigen Chat vorbereiten, ist die Kapazitätsplanung ein wichtiger Aspekt. Dieser Abschnitt umfasst ausführliche Informationen zu unterstützten Server für beständigen Chat-Topologien sowie Tabellen zur Kapazitätsplanung, anhand derer Sie die beste Konfiguration für Ihre Bereitstellung ermitteln können. Zudem wird beschrieben, wie Sie Server für beständigen Chat-Bereitstellungen am besten verwalten, für die zu Spitzenzeiten höhere Kapazitätsanforderungen erfüllt werden müssen.

Informationen zum Download von Server für beständigen Chat finden Sie in "Microsoft Lync Server 13 Server für beständigen Chat" unter [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).

Ausführliche Informationen zur Installation von Server für beständigen Chat finden Sie unter [Installieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) und [Konfigurieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in der Bereitstellungsdokumentation.

Supporttools wie das Planungstool für Lync Server bieten weitere Unterstützung bei der Kapazitätsplanung. Ausführliche Informationen zum Planungstool finden Sie unter [Beginnen des Planungsprozesses für Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

## Unterstützte Topologien für Server für beständigen Chat

Sie können Server für beständigen Chat in einem Pool mit einem einzelnen Server oder in einem Pool mit mehreren Servern sowie in einer Topologie mit einem einzelnen Pool bzw. mit mehreren Pools bereitstellen.

Ab sofort wird für neue Lync Server 2013-Bereitstellungen auch Server für beständigen Chat unter Standard Edition-Server unterstützt. Allerdings kann dies zu einer Beeinträchtigung bei der Leistung und Skalierung führen. Da für diese neue Bereitstellung keine Option mit hoher Verfügbarkeit besteht, empfehlen wir die Verwendung dieser Option in erster Linie für Machbarkeitsstudien, für Bewertungen usw.


> [!NOTE]
> Zusätzliche Informationen zu beiden Topologien finden Sie unter <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planen für den Server für beständigen Chat in Lync Server 2013</A> in dieser Dokumentation und unter <A href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des Servers für beständigen Chat in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## Einzelservertopologie

Die Mindestkonfiguration und einfachste Bereitstellung für Server für beständigen Chat ist eine Einzel- Server für beständigen ChatFront-End-Server-Topologie. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem Server für beständigen Chat (auf dem bei aktivierter Kompatibilität optional auch der Kompatibilitätsdienst ausgeführt wird) ausgeführt wird, sowie ein Server, der als Host für die SQL Server-Datenbank und, wenn Kompatibilität erforderlich ist, für die SQL Server-Datenbank zum Speichern der Kompatibilitätsdaten dient.


> [!IMPORTANT]
> Sie können einem Serverpool für beständigen Chat, der als Bereitstellung mit einem Server im Topologie-Generator eingerichtet wurde, keine zusätzlichen Server hinzufügen. Wir empfehlen die Verwendung einer Bereitstellung einer Pool-Topologie mit mehreren Servern, selbst wenn Sie einen einzelnen Server verwenden, sodass Sie bei Bedarf zu einem späteren Zeitpunkt weitere Server hinzufügen können.



Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie mit einem einzelnen Server für beständigen ChatFront-End-Server mit Kompatibilität.

**Einzelner dauerhafter Chatserver**

![Topologie mit einem einzelnen Server und Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem einzelnen Server und Kompatibilitätsdienst")

## Topologie mit mehreren Servern

Für eine größere Kapazität und Zuverlässigkeit können Sie eine Topologie mit mehreren Servern (wie in [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) beschrieben) bereitstellen. Die Multiserver-Topologie kann bis zu vier aktive Computer enthalten, auf denen Server für beständigen Chat ausgeführt wird. (In Hochverfügbarkeits- und Notfallwiederherstellungskonfigurationen sind bis zu acht Computer möglich, von denen jedoch nur vier aktiv und die anderen vier in Bereitschaft sind.). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, was bei einem Serverpool für beständigen Chat mit 4 Servern insgesamt 80.000 gleichzeitige Benutzer ergibt. Eine Multiserver-Topologie ist das Gleiche wie eine Einzelserver-Topologie, nur dass Server für beständigen Chat auf mehreren Servern gehostet wird und höher skaliert werden kann. Wenn Server für beständigen Chat auf mehreren Computern ausgeführt wird, sollten sich diese in der gleichen Active Directory-Domänendienste-Domäne wie Lync Server und der Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Multiserver-Topologie mit mehreren Computern, auf denen Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.

**Mehrere dauerhafte Chatserver**

![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

In einer Server für beständigen Chat-Bereitstellung mit vier Servern, in der 80.000 Benutzer gleichzeitig angemeldet sein können und Beständiger Chat verwendet wird, wird die Last gleichmäßig verteilt (20.000 Benutzer pro Server). Wenn ein Server nicht länger verfügbar ist, können die mit dem Server verbundenen Benutzer nicht mehr auf Server für beständigen Chat zugreifen. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server erneut verfügbar ist. Abhängig von der Menge an Beständiger Chat-Datenverkehr im Netzwerk kann diese Übergabe zwischen einigen Minuten oder auch länger dauern. Da auf jedem der übrigen Server möglicherweise bis zu 30.000 Benutzer gehostet werden, sollte der ausgefallene Server so schnell wie möglich erneut verfügbar gemacht werden, um Leistungsprobleme zu vermeiden. Alternativ können Sie einen anderen Server für beständigen Chat verfügbar machen, indem Sie den Topologie-Generator oder das Windows PowerShell-Cmdlet **set-CsPersistentChatActiveServer** verwenden.

## Kapazitätsplanung für Server für beständigen Chat

Die folgenden Tabellen unterstützen Sie bei der Kapazitätsplanung für Server für beständigen Chat. In den Tabellen wird veranschaulicht, wie sich Änderungen an verschiedenen Server für beständigen Chat-Einstellungen auf die verfügbare Kapazität auswirken.

## Planen der maximalen Kapazität für den Server für beständigen Chat

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.

### Beispiel für die maximale Kapazität für den Serverpool für beständigen Chat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Aktive Beständiger Chat-Dienstinstanzen</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Beständiger Chat-Dienstinstanzen</p></td>
<td><p><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></p></td>
</tr>
<tr class="odd">
<td><p>Aktive verbundene Benutzer</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der bereitgestellten Benutzer</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der Endpunkte</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


Im vorstehenden Beispiel soll die maximale Anzahl von Benutzern unterstützt werden, die in Server für beständigen Chat zulässig ist: vier Server/Instanzen des Beständiger Chat-Diensts (für Konfigurationen mit hoher Verfügbarkeit und für die Notfallwiederherstellung können weitere vier passive Server mit Server für beständigen Chat eingebunden werden) und 20.000 Benutzer pro Server, sodass eine Gesamtzahl von 80.000 aktiven Benutzern unterstützt wird.

## Kapazitätsplanung für die Verwaltung des Chatroomzugriffs in Beständiger Chat

Die folgende Beispieltabelle ist hilfreich, um die Verwaltung des Beständiger Chat-Chatroomzugriffs in einem Serverpool für beständigen Chat zu planen.

### Beispiel für die Verwaltung des Chatroomzugriffs

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Kleine Chatrooms</th>
<th>Mittlere Chatrooms</th>
<th>Große Chatrooms</th>
<th>Gesamt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Größe der Chatrooms (Anzahl der verbundenen Benutzer)</p></td>
<td><p>30 pro Chatroom</p></td>
<td><p>150 pro Chatroom</p></td>
<td><p>16.000 pro Chatroom</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Chatrooms</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% der Chatrooms als Auditorium verwendet</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>% der Chatrooms sind offen</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Offene Chatrooms (ohne explizite Mitgliedschaft)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Nicht offene Chatrooms (herkömmliche Chatrooms mit expliziter Mitgliedschaft)</p></td>
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Auditorium-Chatrooms (zusätzlicher Zugang für Referenten)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Über direkte Mitgliedschaft verwaltete Chatrooms</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Von Benutzergruppen verwaltete Chatrooms</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Chatrooms (nicht explizit angegeben)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in der Managerliste der einzelnen Chatrooms (für offene und nicht offene Chatrooms</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in der Referentenliste der einzelnen Auditorium-Chatrooms (für offene und nicht offene Chatrooms</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzer- und benutzergruppenbasierte Entitäten für alle Auditorium-Chatrooms</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzer- und benutzergruppenbasierte Managerentitäten für alle Chatroom-Managerlisten</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzer pro Chatroom</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Chatrooms pro Benutzer</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Von Benutzergruppen verwaltete Chatrooms</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten aller Chatrooms</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Zugriffssteuerungseinträge</p></td>
<td><p>704.160</p></td>
<td><p>26.768</p></td>
<td><p>160</p></td>
<td><p>731.088</p></td>
</tr>
<tr class="even">
<td><p>Maximale Anzahl von Zugriffssteuerungseinträgen</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2.000.000</p></td>
</tr>
</tbody>
</table>


Wenn Sie im vorstehenden Beispiel die Server für beständigen Chat gemäß den Empfehlungen bereitstellen, können innerhalb des Pools aus vier Servern und mit aktiviertem Kompatibilitätsdienst bis zu 80.000 aktive Benutzer unterstützt werden.

In diesem Beispiel werden Chatrooms in kleine (30 aktive gleichzeitige Benutzer), mittelgroße (150 aktive Benutzer) und große Chatrooms (16.000 aktive Benutzer) unterteilt. Die Anzahl von Chatrooms einer bestimmten Größe wird basierend auf der Gesamtzahl der folgenden Elemente berechnet:

  - Aktive Benutzer im System

  - Aktive Benutzer in Chatrooms der jeweiligen Größe

  - Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt

Die vorstehende Tabelle zur Kapazitätsplanung gibt für jeden Chatroom die Anzahl von Zugriffssteuerungseinträgen an, die dem jeweiligen Chatroom zugeordnet sind. Dies umfasst die Einträge, die dem Chatroom direkt zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms über Zugriffssteuerungslisten steuern. Darüber hinaus können Sie den Zugriff auf Kategorieebene steuern. In einer Zugriffssteuerungsliste kann es sich bei einem einzelnen Zugriffssteuerungseintrag entweder um eine Benutzergruppe (z. B. eine Sicherheitsgruppe oder Verteilerliste) oder einen einzelnen Benutzer handeln. Sie können Zugriffssteuerungseinträge für Manager, Referenten und Mitglieder eines Chatrooms definieren.


> [!IMPORTANT]
> Bedenken Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl von zulässigen Zugriffssteuerungseinträgen zwei Millionen beträgt. Wenn die berechnete Anzahl von Zugriffssteuerungseinträgen eine Million überschreitet, kann die Leistung signifikant beeinträchtigt werden. Um dieses Problem zu verhindern, sollten Sie wenn möglich sicherstellen, dass Ihre Zugriffssteuerungseinträge keine einzelnen Benutzer, sondern Benutzergruppen umfassen.



## Kapazitätsplanung für die Verwaltung des Chatroomzugriffs über eine Einladung

Anhand der folgenden Tabelle zur Kapazitätsplanung können Sie die Anzahl von Einladungen berechnen, die von Server für beständigen Chat in der Beständiger Chat-Datenbank erstellt und gespeichert werden, wenn die Funktion für das Senden von Einladungen konfiguriert ist. Sie verwalten Einladungen nach Kategorien, indem Sie die Seite mit den Chatroom-Kategorieeinstellungen in der Lync Server-Systemsteuerung oder das Windows PowerShell-Cmdlet **set-csPersistentChatCategory** verwenden. Sie können Einladungen in einem Chatroom verwalten (entsprechend den durch die Kategorie zulässigen Optionen), indem Sie die Seite für die Chatroomverwaltung verwenden, die über den Lync-Client gestartet wird, oder indem Sie das Windows PowerShell-Cmdlet **set-csPersistentChatRoom** verwenden.

Für die Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die Einladungsoption auf der Seite mit den Chatroomeinstellungen für 50 % aller Chatrooms auf **Ja** festgelegt ist.


> [!IMPORTANT]
> Wenn der berechnete Wert für die Anzahl von Einladungen, die der Server generiert, eine Million überschreitet, kann die Serverleistung signifikant beeinträchtigt werden. Um dieses Problem zu vermeiden, minimieren Sie die Anzahl von Chatrooms, die für das Senden von Einladungen konfiguriert sind, oder schränken Sie die Anzahl von Benutzern ein, die Chatrooms betreten können, die für das Senden von Einladungen konfiguriert sind.



### Beispiel für den Chatroomzugriff über eine Einladung

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Kleine Chatrooms</th>
<th>Mittlere Chatrooms</th>
<th>Große Chatrooms</th>
<th>Gesamt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Benutzer, die auf den Chatroom zugreifen können</p></td>
<td><p>30 pro Chatroom</p></td>
<td><p>150 pro Chatroom</p></td>
<td><p>16.000 pro Chatroom</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz an Chatrooms mit Einladung</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Für das Senden von Einladungen konfigurierte Chatrooms</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Benutzer, die auf den Chatroom zugreifen können</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Vom Server für beständigen Chat generierte Einladungen</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80.000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Maximal zulässige Anzahl von Einladungen</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>2.000.000</p></td>
</tr>
<tr class="odd">
<td><p>Modell 1 - Start mit der erwarteten Anzahl an Nachrichten pro Chatroom pro Tag</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Chatrate pro Chatroom (pro Tag)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate (pro Sekunde) für alle Chatrooms</p></td>
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modell 2 - Start mit der Anzahl an veröffentlichten Nachrichten pro Benutzer pro Tag</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Chatrate pro Benutzer pro Tag</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Chatrate pro Chatroom (pro Tag)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1.213</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate (pro Sekunde) für alle Chatrooms</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


## Benutzermodell für die Leistung des Server für beständigen Chats

In der folgenden Tabelle wird das Benutzermodell für Server für beständigen Chat beschrieben. Dieses Modell bildet die Grundlage für die Kapazitätsplanungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern bei der Verwendung von vier Servern dar.

### Benutzermodell für die Leistung des Server für beständigen Chats

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Anzahl von aktiven verbundenen Benutzern</p></td>
<td><p>80.000</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Server für beständigen Chat-Dienstinstanzen</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Umfang kleiner Chatrooms</p></td>
<td><p>30 Benutzer</p></td>
</tr>
<tr class="even">
<td><p>Umfang mittelgroßer Chatrooms</p></td>
<td><p>150 Benutzer</p></td>
</tr>
<tr class="odd">
<td><p>Umfang großer Chatrooms</p></td>
<td><p>16.000 Benutzer</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl von Chatrooms</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von kleinen Chatrooms</p></td>
<td><p>32.000</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von mittelgroßen Chatrooms</p></td>
<td><p>1.067</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von großen Chatrooms</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl von Chatrooms pro Benutzer</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von kleinen Chatrooms pro Benutzer</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von mittelgroßen Chatrooms pro Benutzer</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von großen Chatrooms pro Benutzer</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Chatrooms, denen ein einzelner Benutzer beitritt</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Beitrittsrate</p></td>
<td><p>10/s</p></td>
</tr>
<tr class="even">
<td><p>Gesamtchatrate</p></td>
<td><p>24/s</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate für kleine Chatrooms</p></td>
<td><p>22,22/s</p></td>
</tr>
<tr class="even">
<td><p>Chatrate für mittelgroße Chatrooms</p></td>
<td><p>1,67/s</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate für große Chatrooms</p></td>
<td><p>~ 0,15/s</p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz von Chatrooms, die für Einladungen konfiguriert sind</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Prozentsatz von direkten Mitgliedschaften</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz von Gruppenmitgliedschaften</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von Zugehörigkeiten zu Vorgängerobjekten in Active Directory-Domänendienste</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von abonnierten Kontakten pro Benutzer</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von Endpunkten pro Benutzer</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von sichtbaren Chatrooms pro Benutzer</p></td>
<td><p>2,25 (50 % für 1 Chatroom und 50 % für 2 Chatrooms); bis zu 6 Chatrooms offen, ein Chatroom pro Bildschirm</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Teilnehmern, die pro Intervall abgerufen werden</p></td>
<td><p>25 pro sichtbarem Chatroom</p></td>
</tr>
<tr class="odd">
<td><p>Länge des Abrufintervalls</p></td>
<td><p>5 Minuten</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Teilnehmern, die pro Sekunde abgerufen werden</p></td>
<td><p>15.000</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde</p></td>
<td><p>133,33</p></td>
</tr>
</tbody>
</table>

