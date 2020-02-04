---
title: 'Lync Server 2013: Kapazitätsplanung für beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Kapazitätsplanung für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Der beständige Chat Server kann mehr Benutzer-Echtzeitchats durchführen, die für zukünftiges abrufen und suchen beibehalten werden können. Im Gegensatz zu Gruppen-Sofortnachrichten (im), die im Postfach eines Benutzers gespeichert werden, wenn der Konversations Verlauf konfiguriert ist, bleibt eine dauerhafte Chat Server Sitzung länger geöffnet, und der Inhalt wird auf einem Server zusammen mit den Nachrichten, Dateien, URLs und anderen Daten gespeichert, die Teil einer laufende Unterhaltungen.

Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung auf die Bereitstellung des beständigen Chat Servers. Dieses Thema enthält Details zu unterstützten Topologien und Kapazitäts Planungstabellen für beständige Chat Server, mit denen Sie die beste Konfiguration für Ihre Bereitstellung ermitteln können. Darüber hinaus wird beschrieben, wie Sie die Bereitstellung beständiger Chat Server am besten verwalten, die zu Höchstzeiten eine größere Kapazität erfordern.

Informationen zum Herunterladen des [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)beständigen Chat Servers finden Sie unter "Microsoft lync Server 13-beständiger Chat Server" unter.

Details zum Installieren des beständigen Chat Servers finden Sie unter [Installieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) und [Konfigurieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in der Bereitstellungsdokumentation.

Support Tools wie das lync Server-Planungs Tool können Sie bei der Kapazitätsplanung weiter unterstützen. Details zum Planungs Tool finden Sie unter [Starten des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Unterstützte Topologien für beständigen Chat Server

Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem Pool oder mehreren Pools bereitstellen.

Wir unterstützen nun auch den Server für beständigen Chat auf dem Standard Edition-Server für neue lync Server 2013-Bereitstellungen. Allerdings sind Leistung und Skalierbarkeit davon betroffen, und da es für diese neue Bereitstellung keine Option für die Hochverfügbarkeit gibt, erwarten wir, dass Sie diese in erster Linie zum Nachweis des Konzepts, der Evaluierung usw. verwenden.

<div>


> [!NOTE]  
> Weitere Informationen zu beiden Topologien finden Sie unter <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planen des beständigen Chat Servers in lync Server 2013</A> in dieser Dokumentation und <A href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des beständigen Chat Servers in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="single-server-topology"></a>Topologie mit einem Server

Die Mindestkonfiguration und einfachste Bereitstellung für beständigen Chat Server ist eine einzelne Front-End-Server Topologie des beständigen Chat Servers. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der beständige Chat Server ausgeführt wird (wobei optional der Kompatibilitätsdienst ausgeführt wird, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server-Datenbank hostet, als auch die SQL Server-Datenbank zum Speichern des Kompatibilitätsdaten.

<div>


> [!IMPORTANT]  
> Sie können einem beständigen Chat Serverpool, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen. Wir empfehlen die Verwendung der Pooltopologie mit mehreren Servern, auch wenn Sie einen einzelnen Server verwenden. Dies ist so, dass Sie später weitere Server hinzufügen können, falls dies erforderlich ist. 


</div>

Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen beständigen Chat Server-Front-End-Server mit Compliance.

**Einzelner beständiger Chat Server**

![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie mit mehreren Servern

Um eine größere Kapazität und Zuverlässigkeit bereitzustellen, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer umfassen, auf denen der beständige Chat Server ausgeführt wird (für hoch Verfügbarkeits-und Disaster Recovery-Konfigurationen sind bis zu acht möglich, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem beständigen Chat Serverpool mit 4 Servern verbunden sind. Eine Topologie mit mehreren Servern entspricht der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den persistenten Chat Server hosten und höher skalieren können. Mehrere Computer, auf denen der beständige Chat Server ausgeführt wird, sollten sich in derselben Active Directory-Domänendienst Domäne wie lync Server und dem Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der beständige Chat Server, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.

**Mehrere beständige Chat Server**

![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

In einer persistent Chat Server-Bereitstellung mit vier Servern, bei der 80.000-Benutzer gleichzeitig bei und mithilfe des beständigen Chats angemeldet werden können, wird die Auslastung gleichmäßig bei 20.000-Benutzern pro Server verteilt. Wenn ein Server nicht mehr zur Verfügung steht, verlieren die Benutzer, die mit diesem Server verbunden sind, den Zugriff auf den beständigen Chat Server. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server wieder verfügbar ist. Je nach dem Umfang des beständigen Chat-Datenverkehrs im Netzwerk kann diese Übertragung einige Minuten oder länger dauern. Da jeder der verbleibenden Server möglicherweise so viele wie 30.000-Benutzer hostet, empfehlen wir, dass Sie den nicht verfügbaren Server so schnell wie möglich wiederherstellen, um Leistungsprobleme zu vermeiden. Andernfalls können Sie einen anderen beständigen Chat Server mithilfe des Topologie-Generators oder des Windows PowerShell-Cmdlets, " **CsPersistentChatActiveServer**", verfügbar machen.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Kapazitätsplanung für beständigen Chat Server

Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für beständigen Chat Server helfen. Sie modellieren, wie sich verschiedene Einstellungen für beständigen Chat Server auf die Kapazitäts Funktionen auswirken.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planen der maximalen Kapazität für beständigen Chat Server

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Beispiel für beständigen Chat Server Pool mit maximaler Kapazität

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Aktive persistent-Chat-Dienstinstanzen</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Dienstinstanzen für beständigen Chat</p></td>
<td><p><em>8 (4 muss inaktiv sein; nur maximal 4 kann aktiv sein)</em></p></td>
</tr>
<tr class="odd">
<td><p>Aktive verbundene Benutzer</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der bereitgestellten Benutzer</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der Endpunkte</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


Im vorangehenden Beispiel soll der Plan die maximale Anzahl von Benutzern unterstützen, die der beständige Chat Server zulässt: vier Server/Instanzen des beständigen Chat Diensts (können vier weitere passive Server mit beständigem Chat Server für hohe Verfügbarkeit und Disaster Recovery) und 20.000-Benutzer pro Server für insgesamt 80.000 aktive Benutzer bereitstellen.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Kapazitätsplanung zum Verwalten des Zugriffs auf beständigen Chatrooms

Die folgende Beispieltabelle kann Ihnen bei der Planung der Verwaltung des beständigen Chatrooms in einem Server Pool für beständigen Chat helfen.

### <a name="managing-chat-room-access-sample"></a>Verwalten des Access-Beispiels für Chatrooms

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
<td></td>
</tr>
<tr class="even">
<td><p>Chatrooms</p></td>
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>10</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>% der Chatrooms als Auditorium verwendet</p></td>
<td><p>1 %</p></td>
<td><p>1 %</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% der Chatrooms sind offen</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
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
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>Auditorium-Chatrooms (zusätzlicher Zugang für Referenten)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Über direkte Mitgliedschaft verwaltete Chatrooms</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Von Benutzergruppen verwaltete Chatrooms</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Chatrooms (nicht explizit angegeben)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in der Managerliste der einzelnen Chatrooms (für offene und nicht offene Chatrooms)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in der Referentenliste der einzelnen Auditorium-Chatrooms (für offene und nicht offene Chatrooms)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer- und benutzergruppenbasierte Entitäten für alle Auditorium-Chatrooms</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer- und benutzergruppenbasierte Managerentitäten für alle Chatroom-Managerlisten</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzer pro Chatroom</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
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
<td></td>
</tr>
<tr class="even">
<td><p>Von Benutzergruppen verwaltete Chatrooms</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms</p></td>
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten aller Chatrooms</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Zugriffssteuerungseinträge</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>Maximale Anzahl von Zugriffssteuerungseinträgen</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


Wenn Sie im vorangehenden Beispiel die beständigen Chat Server gemäß den empfohlenen Richtlinien bereitstellen, können Sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern mit aktivierter Kompatibilität verarbeiten.

In diesem Beispiel werden Chatrooms in kleine (30 aktive gleichzeitige Benutzer), mittelgroße (150 aktive Benutzer) und große Chatrooms (16.000 aktive Benutzer) unterteilt. Die Anzahl der Chatrooms einer bestimmten Größe wird basierend auf der Gesamtzahl der folgenden Werte berechnet:

  - Aktive Benutzer im System

  - Aktive Benutzer in Chatrooms der jeweiligen Größe

  - Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt

Die vorstehende Tabelle zur Kapazitätsplanung gibt für jeden Chatroom die Anzahl von Zugriffssteuerungseinträgen an, die dem jeweiligen Chatroom zugeordnet sind. Dies umfasst die Einträge, die dem Chatroom direkt zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms über Zugriffssteuerungslisten steuern. Darüber hinaus können Sie den Zugriff auf Kategorieebene steuern. In einer Zugriffssteuerungsliste kann es sich bei einem einzelnen Zugriffssteuerungseintrag entweder um eine Benutzergruppe (z. B. eine Sicherheitsgruppe oder Verteilerliste) oder einen einzelnen Benutzer handeln. Sie können Zugriffssteuerungseinträge für Manager, Referenten und Mitglieder eines Chatrooms definieren.

<div>


> [!IMPORTANT]  
> Bedenken Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl von zulässigen Zugriffssteuerungseinträgen zwei Millionen beträgt. Wenn die berechnete Anzahl von Zugriffssteuerungseinträgen eine Million überschreitet, kann die Leistung signifikant beeinträchtigt werden. Um dieses Problem zu verhindern, sollten Sie wenn möglich sicherstellen, dass Ihre Zugriffssteuerungseinträge keine einzelnen Benutzer, sondern Benutzergruppen umfassen.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Kapazitätsplanung für die Verwaltung des Chatroom-Zugriffs per Einladung

Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um zu verstehen, wie viele Einladungen der beständige Chat Server in der persistenten Chat Datenbank erstellt und speichert, wenn er zum Senden von Einladungen konfiguriert ist. Sie können Einladungen für die Kategorie verwalten, indem Sie die **Kategorie Einstellungen für Chatrooms** in der lync Server-Systemsteuerung verwenden oder das Windows PowerShell-Cmdlet " **csPersistentChatCategory**" verwenden. Sie können Einladungen in einem Chatroom verwalten (entsprechend der Kategorie), indem Sie die vom lync-Client gestartete **Raum Verwaltungs** Seite verwenden oder ein Windows PowerShell-Cmdlet, " **csPersistentChatRoom**", verwenden.

Für die Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die **Einladungsoption** auf der Seite mit den **Chatroomeinstellungen** für 50 % aller Chatrooms auf **Ja** festgelegt ist.

<div>


> [!IMPORTANT]  
> Wenn der berechnete Wert für die Anzahl von Einladungen, die der Server generiert, eine Million überschreitet, kann die Serverleistung signifikant beeinträchtigt werden. Um dieses Problem zu vermeiden, stellen Sie sicher, dass Sie die Anzahl der Chatrooms minimieren, die zum Senden von Einladungen konfiguriert sind, oder die Anzahl der Benutzer einschränken, die an Chatrooms teilnehmen können, die zum Senden von Einladungen konfiguriert wurden.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Beispiel für Chatroom-Zugriff per Einladung

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
<td></td>
</tr>
<tr class="even">
<td><p>Prozentsatz an Chatrooms mit Einladung</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Für das Senden von Einladungen konfigurierte Chatrooms</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer, die auf den Chatroom zugreifen können</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vom beständigen Chat Server generierte Einladungen</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>Maximal zulässige Anzahl von Einladungen</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>Modell 1: Start mit der erwarteten Anzahl an Nachrichten pro Chatroom und Tag</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
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
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modell 2: Start mit der Anzahl an veröffentlichten Nachrichten pro Benutzer und Tag</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Chatrate pro Benutzer und Tag</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Chatrate pro Chatroom (pro Tag)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate (pro Sekunde) für alle Chatrooms</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Benutzermodell für beständigen Chat Server

In der folgenden Tabelle wird das Benutzermodell für den beständigen Chat Server beschrieben. Dieses Modell bildet die Grundlage für die Kapazitätsplanungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.

### <a name="persistent-chat-server-performance-user-model"></a>Benutzermodell für beständigen Chat Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Anzahl der aktiven verbundenen Benutzer</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Server Dienstinstanzen für beständigen Chat</p></td>
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
<td><p>Gesamtzahl der Chatrooms</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl kleiner Chatrooms</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>Anzahl mittelgroßer Chatrooms</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl großer Chatrooms</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der Chatrooms pro Benutzer</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl kleiner Chatrooms pro Benutzer</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Anzahl mittelgroßer Chatrooms pro Benutzer</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl großer Chatrooms pro Benutzer</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der betretenen Chatrooms pro Benutzer</p></td>
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
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>Chatrate für mittelgroße Chatrooms</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate für große Chatrooms</p></td>
<td><p>~0.15/second</p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz der Chatrooms, die für Einladungen konfiguriert sind</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Prozentsatz der direkten Mitgliedschaften</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz der Gruppenmitgliedschaften</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von Vorgänger Verbindungen in Active Directory-Domänendiensten</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Anzahl abonnierter Kontakte pro Benutzer</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von Endpunkten pro Benutzer</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt</p></td>
<td><p>1.5</p></td>
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
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

