---
title: 'Lync Server 2013: Exportieren einer VoIP-Routenkonfigurationsdatei'
TOCTitle: Exportieren einer VoIP-Routenkonfigurationsdatei
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398081(v=OCS.15)
ms:contentKeyID: 49293002
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie diese Schritte aus, um mit den Export- und Importbefehlen der Lync Server-Systemsteuerung eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. Wenn Sie eine VoIP-Routingkonfiguration (VCFG-Datei) importieren, in der Zwischenzeit jedoch Änderungen an der VoIP-Routingkonfiguration auf dem Server vorgenommen wurden, werden Sie auf den Seiten in der Gruppe **VoIP-Routing** in der Lync Server-Systemsteuerung darauf hingewiesen, dass noch nicht übernommene Änderungen an der VoIP-Routingkonfiguration vorliegen. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.

Wenn Sie an den Einstellungen auf einer Seite in der Gruppe Änderungen durchgeführt, aber noch nicht per Commit übernommen haben, werden die Änderungen in der exportierten VoIP-Konfiguration (VCFG-Datei) gespeichert.

## So exportieren Sie eine VoIP-Routingkonfiguration

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.

5.  Geben Sie einen Speicherort und Dateinamen an, und klicken Sie auf **Speichern**.

## Siehe auch

#### Aufgaben

[Importieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)

