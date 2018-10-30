---
title: 'Lync Server 2013: Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen'
TOCTitle: Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412865(v=OCS.15)
ms:contentKeyID: 49295142
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Einwahlkonferenzen sind eine optionale Funktion bei der Bereitstellung von Lync Server 2013-Konferenzen. Die Komponenten, die vor der Konfiguration von Einwahlkonferenzen installiert werden müssen, werden beim Verwenden des Topologie-Generators zum Entwerfen Ihrer Topologie und anschließenden Einrichtung der Front End-Pools und Standard Edition-Server bereitgestellt. In diesem Thema wird beschrieben, welche Aufgaben vor der Konfiguration von Einwahlkonferenzen ausgeführt werden müssen.

Es wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit Konferenzen und insbesondere mit Einwahlkonferenzen gelesen haben.

## Voraussetzungen für die Konfiguration von Einwahlkonferenzen

Für Einwahlkonferenzen sind die folgenden  Lync Server 2013-Komponenten erforderlich:

  - Unified Communications-Anwendungsdienst (auch nur *Anwendungsdienst* genannt)

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

  - Webseite mit Einstellungen für Einwahlkonferenzen

  - Mindestens ein  Lync Server 2013-Vermittlungsserver und ein PSTN-Gateway

Sie stellen diese Komponenten bereit, wenn Sie mit dem Topologie-Generator Ihre Topologie definieren und veröffentlichen und anschließend einen Front-End-Pool oder Standard Edition-Server bereitstellen. Wenn Sie Enterprise-VoIP bereitstellen, muss diese Bereitstellung vor der Konfiguration von Einwahlkonferenzen erfolgen. Wenn Sie Enterprise-VoIP nicht bereitstellen, können Sie einen Vermittlungsserver und ein PSTN-Gateway bei der Bereitstellung Ihres Front-End-Pools oder Standard Edition-Servers einrichten.


> [!NOTE]
> Stellen Sie bei einem Upgrade von Office Communications Server 2007 R2 auf Lync Server 2013 Einwahlkonferenzen in allen Pools bereit, die zum Hosten von Lync Server 2013-Konferenzen dienen sollen. Ausführliche Informationen zum Migrieren von Einwahlkonferenzen finden Sie unter&nbsp; <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration von Office Communications Server 2007 R2 zu Lync Server 2013</A>.



Dieser Abschnitt setzt voraus, dass Sie die folgenden Schritte ausgeführt haben:

  - Die neuesten Updates auf Ihre Office Communications Server 2007 R2-Umgebung angewendet haben, wenn Sie zu Lync Server 2013 migrieren.

  - Mit dem Topologie-Generator Ihre Topologie entworfen und konfiguriert haben und beim Angeben der Konferenzarbeitslast die Einwahlkonferenzoption ausgewählt haben. Ausführliche Informationen zum Definieren Ihrer Topologie finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation.

  - Die Topologie veröffentlicht sowie den Front-End-Pool oder Standard Edition-Server eingerichtet haben. Weitere Informationen zum Veröffentlichen der Topologie und Installieren von  Lync Server 2013 finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungdokumentation.
    

    > [!NOTE]
    > Bei der Installation Ihrer veröffentlichten Topologie wird die Webseite mit Einstellungen für Einwahlkonferenzen als Teil der Webdienste auf dem Front-End-Server oder Standard Edition-Server installiert.

    

    > [!IMPORTANT]
    > Wenn Sie nach der Bereitstellung von Lync Server 2013 im Topologie-Generator den Pfad zum Dateispeicher ändern, müssen Sie die Konferenzzentrale und die Konferenzankündigungsanwendung neu starten, damit der neue Pfad übernommen wird.



  - Enterprise-VoIP bereitgestellt. Wenn Sie Enterprise-VoIP nicht bereitstellen, haben Sie entweder einen Vermittlungsserver auf dem Enterprise Edition-Front-End-Server oder dem Standard Edition-Server verbunden oder einen eigenständigen Vermittlungsserver zusammen mit einem PSTN-Gateway bereitgestellt. Genauere Informationen zur Bereitstellung von Enterprise-VoIP finden Sie unter [Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation. Genauere Informationen zur Installation eines eigenständigen Vermittlungsservers zusammen mit einem PSTN-Gateway finden Sie unter [Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in der Bereitstellungsdokumentation.

Das folgende Flussdiagramm zeigt die Schritte, die erfolgen müssen, bevor Sie Einwahlkonferenzen konfigurieren können, und die Schritte, die Sie zum Konfigurieren von Einwahlkonferenzen ausführen müssen.

**Bereitstellen von Einwahlkonferenzen**

![Bereitstellung von Einwahlkonferenzen (Flussdiagramm)](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Bereitstellung von Einwahlkonferenzen (Flussdiagramm)")

## Berechtigungen für Einwahlkonferenzen

Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Verwaltungsprogramme verwenden:

  - Systemsteuerung für Lync Server 2013

  - Lync Server-Verwaltungsshell

Mithilfe dieser Verwaltungsprogramme konfigurieren Sie die Einwahlkonferenzeinstellungen, Wähleinstellungen, Richtlinien und anderen Einstellungen, die für Einwahlkonferenzen erforderlich sind.

Für das Konfigurieren von Einwahlkonferenzen ist, je nach Aufgabe, eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**   Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator**   Diese Administratorrolle kann Benutzer für Lync Server aktivieren oder deaktivieren und Benutzern vorhandene Richtlinien, z. B. Konferenz- und PIN-Richtlinien, zuweisen.

  - **CsAdministrator**   Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator" und "CsUserAdministrator" ausgeführt werden können.

## Siehe auch

#### Konzepte

[Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)

