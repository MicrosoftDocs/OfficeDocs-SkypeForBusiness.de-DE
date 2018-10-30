---
title: 'Lync Server 2013: Komponenten und Topologien für den Server für beständigen Chat'
TOCTitle: Komponenten und Topologien für den Server für beständigen Chat
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398500(v=OCS.15)
ms:contentKeyID: 49294291
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Server für beständigen Chat unterstützt sowohl Konfigurationen mit einem einzelnen Server als auch Konfigurationen mit mehreren Servern. Server für beständigen Chat kann auch auf einem Lync Server 2013Standard Edition-Server ausgeführt werden. Diese Konfigurationen bestehen aus den folgenden Server für beständigen Chat-Komponenten und -Topologien.

## Server für beständigen Chat-Komponenten

Für die Installation der aktuellen Version von Server für beständigen Chat sind die folgenden Komponenten erforderlich:

  - Mindestens ein Computer, auf dem Server für beständigen Chat ausgeführt wird und der über die folgenden Dienste verfügt:
    
      - Beständiger Chat-Dienst
    
      - Kompatibilitätsdienst, der eingeschaltet wird, wenn Kompatibilität aktiviert ist
    

    > [!IMPORTANT]
    > In Lync Server 2013 können die Beständiger Chat-Webdienste für das Hoch-/Herunterladen von Dateien jetzt gemeinsam mit Lync Server 2013Front-End-Server betrieben werden.<BR>Auch die Beständiger Chat-Webdienste für die Verwaltung von Chatrooms können gemeinsam mit der Lync Server 2013Front-End-Server betrieben werden.



  - Ein Server (oder mehrere Server, wenn Spiegelung eingesetzt wird), der als Host für die SQL Server-Back-End-Datenbank dient, in der die Beständiger Chat-Inhaltsdatenbank für Chatroominhalte, Räume und Kategorien gespeichert wird.
    

    > [!NOTE]
    > In der Back-End-Datenbank werden Chatverlaufsdaten gespeichert, die Informationen zu Kategorien und Beständiger Chat-Räumen enthalten, die erstellt werden.



  - Bei aktivierter Kompatibilität: Ein Server (oder mehrere, wenn Spiegelung eingesetzt wird), der als Host für die SQL Server-Back-End-Datenbank dient, in der sich die Beständiger Chat-Kompatibilitätsdatenbank befindet, die Kompatibilitätsereignisse und Chatinhalte für Kompatibilitätszwecke speichert.

Wenn Sie Server für beständigen Chat auf einem separaten Computer (z. B. einer Verwaltungskonsole) verwalten möchten, verwenden Sie das Lync Server-Systemsteuerung auf dem Computer. Dieser Computer muss dann in einer Active Directory-Domänendienste-Domäne mit mindestens einem globalen Katalogserver im Gesamtstruktur-Stamm bereitgestellt sein.

Details zu Hardware- und Softwareanforderungen für Server für beständigen Chat finden Sie unter [Technische Anforderungen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) und [Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation.

## Unterstützte Kollokation

Lync Server 2013 unterstützt eine Vielzahl an Kollokationsszenarien, was sich günstig auf die Hardwarekosten auswirkt. So können auf einem Server mehrere Komponenten nebeneinander betrieben werden, was für kleinere Unternehmen interessant ist. Größere Unternehmen können auch bestimmte Komponenten auf einzelnen Servern ausführen, was wichtig ist, wenn es auf Skalierbarkeit und Leistung ankommt. Bei der Entscheidung, ob und welche Komponenten nebeneinander auf dem gleichen Computer arbeiten sollen, ist die Skalierbarkeit sicherlich das wichtigste Kriterium.

Der Beständiger Chat-Kompatibilitätsdienst (wenn Kompatibilität aktiviert ist) kann gemeinsam mit der Lync Server 2013Front-End-Server ausgeführt werden.

Server für beständigen Chat kann auf dem Standard Edition-Server bereitgestellt werden. Der Server für beständigen ChatBack-End-Server und die Beständiger Chat-Kompatibilitätsdatenbank können gemeinsam auf der Standard Edition-Server auf der lokalen SQL Server ExpressBack-End-Server betrieben werden. Nähere Informationen über Komponenten, die dort nebeneinander arbeiten können, finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

Für Lync Server 2013Enterprise Edition kann Server für beständigen Chat nicht gemeinsam auf dem Enterprise Edition-Server ausgeführt werden. Die SQL Server-Datenbank für Server für beständigen Chat kann gemeinsam mit der Back-End-Server-Datenbank eines Enterprise EditionFront-End-Pool betrieben werden. Die SQL Server-Datenbank für Beständiger Chat-Kompatibilität kann auch zusammen mit der Back-End-Server-Datenbank eines Enterprise Edition-Pools betrieben werden.


> [!IMPORTANT]
> Der Server mit der Beständiger Chat-Datenbank kann auch andere Datenbanken aufnehmen. Sollten Sie jedoch in Betracht ziehen, die Beständiger Chat-Datenbank gemeinsam mit anderen Datenbanken zu betreiben, müssen Sie Folgendes berücksichtigen: Wenn Sie die Nachrichten von einer größeren Anzahl von Benutzern speichern, kann der Bedarf an Speicherplatz für die Beständiger Chat stark ansteigen. Daher ist davon abzuraten, die Beständiger Chat-Datenbank zusammen mit der Back-End-Datenbank zu betreiben.



Wenn Sie die Beständiger Chat-Datenbank zusammen mit der Back-End-Datenbank betreiben, können Sie entweder für alle Datenbanken eine einzige Instanz von SQL Server oder für jede Datenbank eine eigene Instanz von SQL Server verwenden, wobei es die folgende Einschränkung gibt:

  - Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank und eine einzige Beständiger Chat-Datenbank enthalten.

Nähere Informationen zum gemeinsamen Betrieb aller Serverrollen und Datenbanken finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

## Server für beständigen Chat-Topologien

Server für beständigen Chat unterstützt die folgenden Topologien:

  - Lync Server 2013 Enterprise Edition - einzelner Server Server für beständigen ChatFront-End-Server

  - Lync Server 2013 Enterprise Edition - mehrere Server Server für beständigen ChatFront-End-Server

  - Lync Server 2013Standard Edition-Server mit SQL Server Express

  - Lync Server 2013Standard Edition-Server und Server für beständigen Chat auf einem separaten Server mit Standard Edition-Server als nächstem Hopserver.

Sie können Server für beständigen Chat Ihrer Lync Server 2013-Bereitstellung mit dem Topologie-Generator hinzufügen. Sie können einen einzelnen oder mehrere Server- Serverpool für beständigen Chat Ihrer Topologie hinzufügen.


> [!IMPORTANT]
> Nachdem Sie einen Serverpool für beständigen Chat mit einem Einzelserver mithilfe von Topologie-Generator erstellt haben, können Sie dem Pool keine weiteren Server mehr hinzufügen.



## Einzelservertopologie

Die Mindestkonfiguration und einfachste Bereitstellung für Server für beständigen Chat ist eine Einzel- Server für beständigen ChatFront-End-Server-Topologie. Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem Server für beständigen Chat (auf dem bei aktivierter Kompatibilität optional auch der Kompatibilitätsdienst ausgeführt wird) ausgeführt wird, sowie ein Server, der als Host für die SQL Server-Datenbank und, wenn Kompatibilität erforderlich ist, für die SQL Server-Datenbank zum Speichern der Kompatibilitätsdaten dient.


> [!IMPORTANT]
> Einem Serverpool für beständigen Chat, der als Einzelserver-Bereitstellung im Topologie-Generator gestartet wird, können Sie keine weiteren Server hinzufügen. Daher sollten Sie auch dann, wenn Sie nur einen einzigen Server haben, die Multiserver-Pool-Topologie verwenden, da Sie dann später weitere Server hinzufügen können, falls erforderlich.



Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie mit einem einzelnen Server für beständigen ChatFront-End-Server mit Kompatibilität.

**Einzelner dauerhafter Chatserver**

![Topologie mit einem einzelnen Server und Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem einzelnen Server und Kompatibilitätsdienst")

## Topologie mit mehreren Servern

Für eine größere Kapazität und Zuverlässigkeit können Sie eine Topologie mit mehreren Servern (wie in [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) beschrieben) bereitstellen. Die Multiserver-Topologie kann bis zu vier aktive Computer enthalten, auf denen Server für beständigen Chat ausgeführt wird. (In Hochverfügbarkeits- und Notfallwiederherstellungskonfigurationen sind bis zu acht Computer möglich, von denen jedoch nur vier aktiv und die anderen vier in Bereitschaft sind.). Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, was bei einem Serverpool für beständigen Chat mit 4 Servern insgesamt 80.000 gleichzeitige Benutzer ergibt. Eine Multiserver-Topologie ist das Gleiche wie eine Einzelserver-Topologie, nur dass Server für beständigen Chat auf mehreren Servern gehostet wird und höher skaliert werden kann. Wenn Server für beständigen Chat auf mehreren Computern ausgeführt wird, sollten sich diese in der gleichen Active Directory-Domänendienste-Domäne wie Lync Server und der Kompatibilitätsdienst befinden.

Die folgende Abbildung zeigt alle Komponenten einer Multiserver-Topologie mit mehreren Computern, auf denen Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.

**Mehrere dauerhafte Chatserver**

![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")

Topologien mit mehreren Servern ermöglichen es, Serverfunktionen zu einem Pool zusammenzufassen. In einem Serverpool kommunizieren die Beständiger Chat-Dienste miteinander und geben sich gegenseitig Daten frei. So ist zum Beispiel der Chatverlauf, der ursprünglich an einen Beständiger Chat-Dienst gesendet wurde, in jedem Beständiger Chat-Dienst in dem System verfügbar. Eine Datei, die über einen Beständiger Chat-Dienst hochgeladen wird, ist für jeden Beständiger Chat-Dienst zugreifbar. Benutzer können mit unterschiedlichen Server für beständigen ChatFront-End-Server verbunden sein und trotzdem miteinander chatten und kommunizieren.

Der Standardport von TCP 8011 wird von Servern verwendet, um Verbindungen zu einem Serverpool herzustellen. Und für den Beständiger Chat-Dienst wird er zur gegenseitigen Kommunikation oder für Verwaltungszwecke verwendet.

