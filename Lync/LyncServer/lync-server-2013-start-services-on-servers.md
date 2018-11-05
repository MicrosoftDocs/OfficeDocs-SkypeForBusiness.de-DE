---
title: 'Lync Server 2013: Starten von Diensten auf Servern'
TOCTitle: Starten von Diensten auf Servern
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413059(v=OCS.15)
ms:contentKeyID: 49295965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Starten von Diensten auf Servern für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-09-03_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein oder es müssen geeignete Berechtigungen an Sie delegiert worden sein. Ausführliche Informationen zum Delegieren von Berechtigungen finden Sie unter dem Thema [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Nachdem Sie den lokalen Konfigurationsspeicher auf Ihren Servern installiert, die Lync Server 2013-Komponenten installiert und die Zertifikate auf einem Front-End-Server oder Front-End-Server konfiguriert haben, müssen Sie die Lync Server 2013-Dienste auf dem Server starten. Verwenden Sie das folgende Verfahren, um die Dienste auf jedem Front-End-Server in Ihrer Bereitstellung zu starten.

## So starten Sie Dienste auf einem Standard Edition- oder Front-End-Server

1.  Klicken Sie im Lync Server-Bereitstellungs-Assistenten auf der Seite **Lync Server 2013** auf die Schaltfläche **Ausführen** neben **Schritt 4: Dienste starten** .

2.  Klicken Sie auf der Seite **Dienste starten** auf **Weiter** , um die Lync Server-Dienste auf dem Server zu starten.

3.  Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen** .
    

    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Best-Effort-Methode zum Anzeigen, dass die Dienste wirklich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt <STRONG>Dienststatus (optional)</STRONG> unmittelbar nach Ausführung des Schritts <STRONG>Dienste starten</STRONG> auszuführen und mithilfe der Microsoft Management Console (MMC) zu bestätigen, dass die Dienste erfolgreich gestartet wurden. Wenn ein Lync Server-Dienst nicht gestartet wurde, klicken Sie in der MMC mit der rechten Maustaste auf den Dienst, und klicken Sie anschließend auf <STRONG>Starten</STRONG> .


