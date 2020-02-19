---
title: 'Lync Server 2013: Kapazitätsplanung für den Server für beständigen Chat'
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
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Kapazitätsplanung für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Der Server für beständigen Chat kann mehr Benutzer-Echtzeitchats ausführen, die für den zukünftigen Abruf und die Suche beibehalten werden können. Im Gegensatz zu Group Instant Messaging (im), die im Postfach eines Benutzers gespeichert wird, wenn der Unterhaltungsverlauf konfiguriert ist, bleibt eine Server Sitzung für beständigen Chat länger geöffnet, und der Inhalt wird auf einem Server zusammen mit den Nachrichten, Dateien, URLs und anderen Daten gespeichert, die Teil eines Laufende Unterhaltung.

Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung der Bereitstellung des Servers für beständigen Chat. Dieses Thema enthält Details zu unterstützten Topologien und Kapazitäts Planungstabellen für beständigen Chat Server, mit denen Sie die beste Konfiguration für Ihre Bereitstellung bestimmen können. Außerdem wird beschrieben, wie Sie Server Bereitstellungen mit persistentem Chat am besten verwalten, die zu Spitzenzeiten eine höhere Kapazität erfordern.

Informationen zum Herunterladen von [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)persistent Chat Server finden Sie unter "Microsoft lync Server 13 persistent Chat Server" unter.

Ausführliche Informationen zum Installieren des Servers für beständigen Chat finden Sie unter [Installing persistent Chat Server in lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) und [Configuring persistent Chat Server in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in der Bereitstellungsdokumentation.

Support Tools wie lync Server Planungs Tool können Ihnen bei der Kapazitätsplanung behilflich sein. Ausführliche Informationen zum Planungs Tool finden Sie unter [Beginn des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Unterstützte Topologien für beständigen Chat Server

Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem oder mehreren Pools bereitstellen.

Wir unterstützen nun auch den Server für beständigen Chat auf Standard Edition-Server für neue lync Server 2013-Bereitstellungen. Leistung und Skalierung sind jedoch betroffen, und da es für diese neue Bereitstellung keine Option für hohe Verfügbarkeit gibt, erwarten wir, dass Sie dies in erster Linie für die Machbarkeitsstudie, Evaluierung usw. verwenden.

<div>


> [!NOTE]  
> Weitere Details zu beiden Topologien finden Sie unter <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent Chat Server in lync Server 2013</A> in dieser Dokumentationsgruppe und <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent Chat Server in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="single-server-topology"></a>Einzelservertopologie

Die minimale Konfiguration und die einfachste Bereitstellung für den Server für beständigen Chat ist ein einzelner Server für beständigen Chat Front-End-Server Topologie. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der Server für beständigen Chat ausgeführt wird (optional wird der Kompatibilitätsdienst ausgeführt, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server Datenbank hostet, als auch die erforderliche Kompatibilität, die SQL Server Datenbank zum Speichern des Compliance-Daten.

<div>


> [!IMPORTANT]  
> Sie können keinem Serverpool für beständigen Chat, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen. Es wird empfohlen, die Topologie mit mehreren Server Pools zu verwenden, auch wenn Sie einen einzelnen Server verwenden. Dies bedeutet, dass Sie später weitere Server hinzufügen können, falls dies erforderlich ist. 


</div>

Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen Server für beständigen Chat Front-End-Server mit Compliance.

**Einzelner dauerhafter Chatserver**

![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologie mit mehreren Servern

Um eine höhere Kapazität und Zuverlässigkeit zu bieten, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben. Die Topologie mit mehreren Servern kann bis zu vier aktive Computer mit persistent Chat Server umfassen (Hochverfügbarkeit und Notfall Wiederherstellungs Konfigurationen ermöglichen bis zu acht, aber nur vier können aktiv sein und die restlichen vier im Standbymodus). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem Serverpool für beständigen Chat mit 4 Servern verbunden sind. Eine Topologie mit mehreren Servern ist identisch mit der Einzelservertopologie, mit dem Unterschied, dass mehrere Server den Server für beständigen Chat hosten und höher skalieren können. Mehrere Computer mit persistent Chat Server sollten sich in derselben Active Directory-Domänendienste Domäne wie lync Server und dem Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank läuft.

**Mehrere dauerhafte Chatserver**

![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

In einer Bereitstellung mit vier Servern für beständigen Chat, bei der 80.000 Benutzer gleichzeitig bei und mit dem beständigen Chat angemeldet werden können, wird die Last gleichmäßig auf 20.000 Benutzer pro Server verteilt. Wenn ein Server nicht mehr verfügbar ist, verlieren die Benutzer, die mit diesem Server verbunden sind, Ihren Zugriff auf den Server für beständigen Chat. Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server erneut verfügbar ist. In Abhängigkeit von der Menge des beständigen Chat Datenverkehrs im Netzwerk kann diese Übertragung einige Minuten oder länger dauern. Da jeder der verbleibenden Server möglicherweise so viele wie 30.000-Benutzer hostet, wird empfohlen, den nicht verfügbaren Server so schnell wie möglich wiederherzustellen, um Leistungsprobleme zu vermeiden. Andernfalls können Sie einen weiteren Server für beständigen Chat mithilfe des Topologie-Generators oder des Windows PowerShell **-Cmdlets festlegen-CsPersistentChatActiveServer**verfügbar machen.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Kapazitätsplanung für den Server für beständigen Chat

Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für den Server für beständigen Chat helfen. Sie modellieren, wie sich verschiedene Einstellungen für den Server für beständigen Chat auf Kapazitäts Funktionen auswirken

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planen der maximalen Kapazität für den Server für beständigen Chat

Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Beispiel für den Server Pool für beständigen Chat mit maximaler Kapazität

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Aktive persistent Chat-Dienstinstanzen</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Dienstinstanzen für beständigen Chat</p></td>
<td><p><em>8 (4 muss inaktiv sein; nur maximal 4 kann aktiv sein)</em></p></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzer verbunden</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Gesamtanzahl der Benutzer</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der Endpunkte</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


Im vorherigen Beispiel soll die maximale Anzahl von Benutzern unterstützt werden, die der Server für beständigen Chat zulässt: vier Server/Instanzen des Diensts für beständigen Chat (können vier weitere passive Server mit persistent Chat Server für hohe Verfügbarkeit und Notfallwiederherstellung) und 20.000 Benutzer pro Server für insgesamt 80.000 aktive Benutzer haben.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Kapazitätsplanung für die Verwaltung des Zugriffs auf beständigen Chatroom

Die folgende Beispieltabelle hilft Ihnen bei der Planung der Verwaltung des Zugriffs auf beständigen Chatrooms in einem Server Pool für beständigen Chat.

### <a name="managing-chat-room-access-sample"></a>Beispiel für die Verwaltung des Chatroomzugriffs

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
<td><p>Größe der Chatrooms (Anzahl der miteinander verbundenen Benutzer)</p></td>
<td><p>30 pro Zimmer</p></td>
<td><p>150 pro Zimmer</p></td>
<td><p>16.000 pro Zimmer</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chatrooms</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10 </p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% der Räume, die Auditorium sind</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% der geöffneten Räume</p></td>
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Offene Räume (keine explizite Mitgliedschaft)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Nicht geöffnete Räume (reguläre Räume mit expliziter Mitgliedschaft)</p></td>
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Auditoriumräume (zusätzlicher Referenten Eintrag)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Durch direkte Mitgliedschaft verwaltete Räume</p></td>
<td><p>50%</p></td>
<td><p>10 %</p></td>
<td><p>0 %</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Von Benutzergruppen verwaltete Chatrooms</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100 %</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Räume (nicht explizit angegeben)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Räume</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Räume</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in den Manager Listen der einzelnen Chatrooms (für offene und nicht offene Räume)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in den Referentenlisten der einzelnen Auditorium-Chatrooms (für offene und nicht offene Räume)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzerbasierte Mitgliedschafts Entitäten in allen nicht offenen Räumen</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzergruppen basierte Mitgliedschafts Entitäten in allen nicht offenen Räumen</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen basierte Entitäten in allen Auditorium-Chatrooms</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen basierte Manager-Entitäten in allen Chatrooms-Manager Listen</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzer pro Chatroom</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16.000</em></p></td>
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
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer und Benutzergruppen in allen Manager-, Referenten-und Bereichslisten für Chatrooms</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
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
<td></td>
<td></td>
<td></td>
<td><p>2 Millionen</p></td>
</tr>
</tbody>
</table>


Wenn Sie im vorherigen Beispiel die Server für beständigen Chat gemäß den empfohlenen Richtlinien bereitstellen, können Sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern mit aktivierter Kompatibilität verarbeiten.

In diesem Beispiel werden Chatrooms kategorisiert, die als klein (30 aktive Benutzer zu einem bestimmten Zeitpunkt), mittlere (150 aktive Benutzer) und groß (16.000 aktive Benutzer) kategorisiert sind. Die Anzahl von Chatrooms einer bestimmten Größe wird basierend auf der Gesamtzahl der folgenden Elemente berechnet:

  - Aktive Benutzer im System

  - Aktive Benutzer in Chatrooms der jeweiligen Größe

  - Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt

Für jeden Chatroom gibt die vorhergehende Kapazitätsplanungstabelle die Anzahl der Zugriffssteuerungseinträge an, die dem Chatroom zugeordnet sind, einschließlich der Einträge, die direkt dem Chatroom zugeordnet sind. Sie können den Zugriff auf einzelne Chatrooms mithilfe von Zugriffssteuerungslisten (Access Control Lists, ACLs) steuern. Sie können den Zugriff auch auf Kategorienebene steuern. In einer ACL kann ein einzelner Zugriffssteuerungseintrag entweder eine Benutzergruppe sein (beispielsweise eine Sicherheitsgruppe, eine Verteilerliste oder ein einzelner Benutzer). Sie können Zugriffssteuerungseinträge für Chatroom-Manager, Referenten und Mitglieder definieren.

<div>


> [!IMPORTANT]  
> Beachten Sie bei der Planung ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl der zulässigen Zugriffssteuerungseinträge 2 Millionen ist. Wenn die berechneten Zugriffssteuerungseinträge 2 Millionen überschreiten, kann sich die Serverleistung erheblich vermindern. Um dieses Problem zu vermeiden, stellen Sie nach Möglichkeit sicher, dass Ihre Zugriffssteuerungseinträge Benutzergruppen und nicht einzelne Benutzer sind.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Kapazitätsplanung für die Verwaltung des Chatroomzugriffs über eine Einladung

Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um die Anzahl der Einladungen zu verstehen, die der Server für beständigen Chat erstellt und in der Datenbank für beständigen Chat gespeichert wird, wenn er zum Senden von Einladungen konfiguriert ist. Sie können Einladungen für die Kategorie verwalten, indem Sie auf der Seite mit den **Chatroom-Kategorieeinstellungen** im lync Server-Systemsteuerung oder mithilfe des Cmdlets Windows PowerShell **festlegen-csPersistentChatCategory**. Sie können Einladungen in einem Chatroom verwalten (entsprechend der Vorgehensweise der Kategorie), indem Sie die auf dem lync-Client gestartete **Raum Verwaltungs** Seite oder mithilfe eines Windows PowerShell-Cmdlets **festlegen-csPersistentChatRoom**verwenden.

Bei den Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die Option **Einladungen** auf der Seite **chatroomeinstellungen** für 50 Prozent aller Chatrooms auf **Ja**festgelegt ist.

<div>


> [!IMPORTANT]  
> Wenn der berechnete Wert für die Anzahl von Einladungen, die vom Server generiert werden, 1 Million überschreitet, kann sich die Serverleistung erheblich vermindern. Um dieses Problem zu vermeiden, müssen Sie die Anzahl der Chatrooms minimieren, die zum Senden von Einladungen konfiguriert sind, oder die Anzahl der Benutzer einschränken, die Chatrooms beitreten können, die zum Senden von Einladungen konfiguriert wurden.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Beispiel für den Chatroomzugriff über eine Einladung

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
<td><p>Benutzer, die auf Chatroom zugreifen können</p></td>
<td><p>30 pro Zimmer</p></td>
<td><p>150 pro Zimmer</p></td>
<td><p>16.000 pro Zimmer</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Prozentsatz der Räume mit Einladungen</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Für das Senden von Einladungen konfigurierte Chatrooms</p></td>
<td><p><em>16.000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Benutzer, die auf den Chatroom zugreifen können</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vom Server für beständigen Chat generierte Einladungen</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80,000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Maximal zulässige Anzahl von Einladungen</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 Millionen</p></td>
</tr>
<tr class="odd">
<td><p>Modell 1 – beginnen mit der erwarteten Anzahl von Nachrichten pro Raum pro Tag</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat Rate pro Zimmer (pro Tag)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate (pro Sekunde) in allen Räumen</p></td>
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modell 2 – Start mit der Anzahl von Nachrichten, die pro Benutzer pro Tag bereitgestellt werden</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Chat Rate pro Benutzer pro Tag</p></td>
<td><p>15 </p></td>
<td><p>5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Chat Rate pro Zimmer (pro Tag)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1.213</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate (pro Sekunde) in allen Räumen</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Server Leistung für beständigen Chat-Benutzermodell

In der folgenden Tabelle wird das Benutzermodell für den Server für beständigen Chat beschrieben. Sie bildet die Grundlage für die Kapazitäts Planungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.

### <a name="persistent-chat-server-performance-user-model"></a>Server Leistung für beständigen Chat-Benutzermodell

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Anzahl der verbundenen aktiven Benutzer</p></td>
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
<td><p>16.000 Benutzer</p></td>
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
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl von Chatrooms pro Benutzer</p></td>
<td><p>16 </p></td>
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
<td><p>Anzahl der hinzugefügten Chatrooms pro Benutzer</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Beitrittsrate</p></td>
<td><p>10/Sekunde</p></td>
</tr>
<tr class="even">
<td><p>Gesamtchatrate</p></td>
<td><p>24/Sekunde</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate für kleine Chatrooms</p></td>
<td><p>0.00/Second</p></td>
</tr>
<tr class="even">
<td><p>Chatrate für mittelgroße Chatrooms</p></td>
<td><p>1.67/Sekunde</p></td>
</tr>
<tr class="odd">
<td><p>Chatrate für große Chatrooms</p></td>
<td><p>~ 0.15/Second</p></td>
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
<td><p>Durchschnittliche Anzahl von Vorgänger Zuordnungen in Active Directory-Domänendienste</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von abonnierten Kontakten pro Benutzer</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl der Endpunkte pro Benutzer</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Anzahl von sichtbaren Chatrooms pro Benutzer</p></td>
<td><p>2,25 (50% für 1 Zimmer und 50% für 2 Zimmer); Bis zu 6 geöffnete Zimmer, eine pro Monitor</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Teilnehmern, die pro Intervall abgerufen werden</p></td>
<td><p>25 pro sichtbarem Chatroom</p></td>
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
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde</p></td>
<td><p>133,33</p></td>
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

