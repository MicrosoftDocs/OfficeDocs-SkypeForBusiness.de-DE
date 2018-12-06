---
title: A/V-Edgeserver in Lync Server 2013
TOCTitle: A/V-Edgeserver in Lync Server 2013
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49890892
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# A/V-Edgeserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Zusätzlich zu Audio und Video bietet der A/V-Edgedienst beispielsweise Unterstützung für die Desktopfreigabe und die Dateiübertragung.

Der A/V-Edgeserverdienst wird primär durch die Verwendung der A/V-Edge-Konfiguration verwaltet. Mit diesen Einstellungen können Sie die maximale zuzuweisende Bandbreite pro Port und Benutzer verwalten und den Zeitraum definieren, in dem das Authentifizierungstoken verwendet werden kann, bevor es erneuert werden muss. A/V-Edge-Konfigurationseinstellungen können auf Standorte oder einzelne A/V-Edgeserver angewendet werden. Verwenden Sie beim Bestimmen der zu bevorzugenden Einstellungsauflistung die folgende Anleitung:

  - Auf Dienstebene konfigurierte Einstellungen (d. h. auf einem einzelnen Server) haben die höchste Priorität.

  - Auf Standortebene zugewiesene Einstellungen haben Vorrang vor den global zugewiesenen Einstellungen. Auf Dienstebene vorgenommene Einstellungen ersetzen jedoch ebenfalls auf Standortebene vorgenommene Einstellungen.

  - Einstellungen auf globaler Ebene werden nur verwendet, wenn auf dem einzelnen Server keine auf Dienstebene vorgenommenen Einstellungen konfiguriert wurden und wenn keine auf Standortebene vorgenommenen Einstellungen für den Standort, wo sich der Server befindet, vorliegen.

Der A/V-Edgedienst kann nur mithilfe der Lync Server-PowerShell und der Cmdlets "CsAVEdgeConfiguration" verwaltet werden.

## In diesem Abschnitt

  - [Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

