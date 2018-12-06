---
title: 'Lync Server 2013: Importieren einer VoIP-Routenkonfigurationsdatei'
TOCTitle: Importieren einer VoIP-Routenkonfigurationsdatei
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398301(v=OCS.15)
ms:contentKeyID: 49293930
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie diese Schritte aus, um mit den Export- und Importbefehlen der Lync Server-Systemsteuerung eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. Wenn Sie eine VoIP-Routingkonfiguration (VCFG-Datei) importieren, in der Zwischenzeit jedoch Änderungen an der VoIP-Routingkonfiguration auf dem Server vorgenommen wurden, werden Sie auf den Seiten in der Gruppe **VoIP-Routing** in der Lync Server-Systemsteuerung darauf hingewiesen, dass noch nicht übernommene Änderungen an der VoIP-Routingkonfiguration vorliegen. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.

Wenn Sie an den Einstellungen auf einer Seite in der Gruppe Änderungen durchgeführt, aber noch nicht per Commit übernommen haben, werden die Änderungen in der exportierten VoIP-Konfiguration (VCFG-Datei) gespeichert.

## So importieren Sie eine VoIP-Routingkonfiguration

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** .

4.  Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren** .

5.  Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen** .

6.  Klicken Sie auf **Commit** und anschließend auf **Commit für alle** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.



## Siehe auch

#### Aufgaben

[Exportieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

