---
title: 'Lync Server 2013: Konfigurationsvoraussetzungen und -rollen für Ansagen'
TOCTitle: Konfigurationsvoraussetzungen und -rollen für Ansagen
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398658(v=OCS.15)
ms:contentKeyID: 49294598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurationsvoraussetzungen und -rollen für Ansagen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Ansagen sind eine Enterprise-VoIP-Funktion für die Anrufverwaltung. In diesem Thema wird beschrieben, welche Voraussetzungen erfüllt sein müssen, bevor Sie Ansagen konfigurieren können, und welche Rollenzuweisungen Sie zum Ausführen der Konfigurationsaufgaben benötigen.

Hierbei wird davon ausgegangen, dass Sie die Planungsdokumentation im Zusammenhang mit Ansagen gelesen haben (siehe [Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

## Konfigurationsvoraussetzungen für Ansagen

Für die Ansageanwendung sind die folgenden Komponenten erforderlich:

  - Anwendungsdienst

  - Reaktionsgruppenanwendung

  - Dateispeicher für Audiodateien

All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.

## Rollen für die Konfiguration von Ansagen

Sie können Ansagen mithilfe der folgenden Verwaltungstools konfigurieren:

  - Lync Server-Systemsteuerung

  - Lync Server-Verwaltungsshell

Für die Konfiguration der Ansageanwendung ist eine der folgenden Administratorrollen erforderlich:

  - **CsVoiceAdministrator**   Diese Administratorrolle kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten (einschließlich aller Ansageeinstellungen).

  - **CsServerAdministrator**   Mit dieser Administratorrolle können Sie Server und Dienste verwalten und überwachen, eine Problembehandlung für diese Server und Dienste durchführen sowie alle Ansageeinstellungen konfigurieren.

  - **CsAdministrator**   Mit dieser Administratorrolle können Sie sämtliche Verwaltungsaufgaben ausführen und alle Einstellungen ändern.

  - **CsViewOnlyAdministrator**   Mit dieser Administratorrolle können Sie die Bereitstellung anzeigen, um die Integrität zu überwachen.


> [!NOTE]
> Ausführliche Informationen zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</A> in der Planungsdokumentation.



## Siehe auch

#### Konzepte

[Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  

#### Weitere Ressourcen

[Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)

