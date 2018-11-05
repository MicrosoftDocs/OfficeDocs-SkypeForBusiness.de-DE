---
title: 'Lync Server 2013: Erforderliche Software für Enterprise-VoIP'
TOCTitle: Erforderliche Software für Enterprise-VoIP
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425916(v=OCS.15)
ms:contentKeyID: 49293798
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erforderliche Software für Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Stellen Sie sicher, dass die zur Bereitstellung von Enterprise-VoIP vorgesehene Infrastruktur die folgenden Softwareanforderungen erfüllt:

  - Lync Server 2013 Standard Edition oder Enterprise Edition ist im Netzwerk installiert und wird ausgeführt.

  - Alle Edgeserver und Reverseproxys wurden in Ihrem Umkreisnetzwerk bereitgestellt und sind betriebsbereit - die Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und ein Reverseproxy eingeschlossen.

  - Zur Integration von Exchange Unified Messaging in Lync Server sowie zur Bereitstellung von detaillierten Benachrichtigungen und Anrufprotokollinformationen für die Lyncendpunkte ist entweder Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 oder Microsoft Exchange Server 2013 erforderlich.

  - Es wurden Benutzer für Lync Server erstellt und aktiviert.

  - Lync-Clients und -Geräte wurden erfolgreich bereitgestellt.

  - Der Topologie-Generator wurde auf einem Server in Ihrem Netzwerk installiert.

## Nächste Schritte: Überprüfen der Anforderungen an Sicherheit und Konfiguration

Nachdem Sie sich vergewissert haben, dass die Softwareanforderungen für Enterprise-VoIP erfüllt wurden, können Sie anhand der folgenden Dokumentation die Bereitstellung von Enterprise-VoIP weiter vorbereiten:

1.  Überprüfen Sie die Anforderungen hinsichtlich Sicherheit, Benutzerkonfiguration und Hardware, wie beschrieben unter [Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Installieren Sie den Vermittlungsserver, wie beschrieben unter [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md). Dies gilt *nur* , wenn Sie einen eigenständigen Vermittlungsserver oder -pool bereitstellen möchten, da Vermittlungsserver, wenn sie verbunden werden, im Rahmen der Front-End-Pool- oder Standard Edition-Server-Bereitstellung installiert werden.

3.  Konfigurieren Sie Trunkverbindungen zur Bereitstellung einer PSTN-Anbindung für die Benutzer, wie beschrieben unter [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

