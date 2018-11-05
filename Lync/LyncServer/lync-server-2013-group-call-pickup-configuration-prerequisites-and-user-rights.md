---
title: Voraussetzungen und Benutzerrechte für die Konfiguration der Gruppenanrufannahme
TOCTitle: Voraussetzungen und Benutzerrechte für die Konfiguration der Gruppenanrufannahme
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945641(v=OCS.15)
ms:contentKeyID: 52056380
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voraussetzungen und Benutzerrechte für die Konfiguration der Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2013-01-30_

Die Gruppenanrufannahme ist eine Anrufverwaltungsfunktion, die bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert wird. In diesem Thema werden die Voraussetzungen für die Konfiguration der Gruppenanrufannahme sowie die erforderlichen Benutzerrechte zum Ausführen von Konfigurationsaufgaben beschrieben.

In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur Gruppenanrufannahme (siehe [Planen der Gruppenanrufannahme in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)) gelesen haben.

## Konfigurationsvoraussetzungen für Gruppenanrufannahme

Die Gruppenanrufannahme erfordert folgende Komponenten:

  - Anwendungsdienst

  - Anwendung zum Parken von Anrufen

Diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP automatisch installiert.

## Benutzerrechte für die Konfiguration der Gruppenanrufannahme

Sie verwenden folgende Verwaltungstools für die Konfiguration der Gruppenanrufannahme:

  - Lync Server-Verwaltungsshell

  - SEFAUtil-Resource Kit-Tool

Verwenden Sie die Lync Server-Verwaltungsshell zum Erstellen und Verwalten von Anrufannahmegruppen in der Orbittabelle für das Parken von Anrufen. Verwenden Sie das SEFAUtil-Resource Kit-Tool, um eine Anrufannahmegruppe zuzuweisen und die Gruppenanrufannahme für Benutzer zu aktivieren oder zu deaktivieren.

Das Konfigurieren der Gruppenanrufannahme erfordert je nach Aufgabe einer der folgenden Administratorrollen:

  - **CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator:** Diese Administratorrolle kann die Gruppenanrufannahme für Benutzer aktivieren. Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.

  - **CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und eine Problembehandlung durchführen.

  - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator", "CsServerAdministrator" und "CsUserAdministrator" ausgeführt werden können.


> [!NOTE]
> Ausführliche Informationen zu Administratorrechten finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A>.



## Siehe auch

#### Konzepte

[Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Weitere Ressourcen

[Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

