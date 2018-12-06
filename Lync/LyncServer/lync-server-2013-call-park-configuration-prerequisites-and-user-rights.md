---
title: 'Lync Server 2013: Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen'
TOCTitle: Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425730(v=OCS.15)
ms:contentKeyID: 49293455
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen und Benutzerrechte für die Konfiguration zum Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Das Parken von Anrufen ist eine Funktion für die Anrufverwaltung, die bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert wird. In diesem Thema wird beschrieben, welche Voraussetzungen erfüllt sein müssen, bevor Sie das Parken von Anrufen konfigurieren können, und welche Benutzerrechte Sie zum Ausführen der Konfigurationsaufgaben benötigen.


> [!IMPORTANT]
> Angepasste Wartemusikdateien für die Anwendung zum Parken von Anrufen werden nicht im Rahmen des Lync Server 2013-Notfallwiederherstellungsprozesses gesichert. Die Dateien gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt oder gelöscht werden. Erstellen Sie immer eine separate Sicherungskopie der angepassten Wartemusikdateien, die Sie für das Parken von Anrufen hochgeladen haben.



In diesem Abschnitt wird davon ausgegangen, dass Sie die für das Parken von Anrufen relevanten Abschnitte in der Planungsdokumentation gelesen haben (siehe [Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

## Parken von Anrufenfea-rg-app-no-version

Für Parken von Anrufen sind folgende Komponenten erforderlich:

  - Anwendungsdienst

  - Anwendung zum Parken von Anrufen

Diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP automatisch installiert.

Wenn Sie möchten, dass Anrufer Wartemusik hören, solange der Anruf geparkt ist, wird zusätzlich eine Datei für die Wartemusik benötigt. Bei der Bereitstellung von Enterprise-VoIP wird automatisch eine Standarddatei für die Wartemusik installiert. Sie können die Standarddatei durch eine eigene Wartemusikdatei ersetzen. Die Funktion zum Parken von Anrufen verwendet den Dateispeicher zum Speichern der Audiodatei.

## Benutzerrechte für die Konfiguration zum Parken von Anrufen

Sie können Parken von Anrufen mithilfe der folgenden Verwaltungstools konfigurieren:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Sie verwenden diese Tools zum Einrichten der Orbittabelle für das Parken von Anrufen und zum Konfigurieren weiterer Einstellungen, die von der Funktion zum Parken von Anrufen verwendet werden.

Für das Konfigurieren der Funktion zum Parken von Anrufen ist je nach Aufgabe eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator :** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.

  - **CsUserAdministrator :** Diese Administratorrolle kann das Parken von Anrufen in der VoIP-Richtlinie aktivieren. Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.

  - **CsServerAdministrator :** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und eine Problembehandlung durchführen.

  - **CsAdministrator :** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator", "CsServerAdministrator" und "CsUserAdministrator" ausgeführt werden können.


> [!NOTE]
> Ausführliche Informationen zu Administratorrechten finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A>.



## Siehe auch

#### Konzepte

[Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Weitere Ressourcen

[Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

