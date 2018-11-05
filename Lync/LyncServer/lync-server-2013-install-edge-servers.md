---
title: 'Lync Server 2013: Installieren von Edgeservern'
TOCTitle: Installieren von Edgeservern
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398230(v=OCS.15)
ms:contentKeyID: 49293289
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Edgeservern für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Sie installieren Lync Server 2013 auf Edgeservern, indem Sie den Lync Server-Bereitstellungs-Assistenten verwenden. Durch Ausführung des Bereitstellungs-Assistenten auf jedem Edgeserver können Sie die meisten Aufgaben ausführen, die zur Einrichtung des Edgeservers erforderlich sind. Zur Bereitstellung von Lync Server 2013 auf einem Edgeserver müssen Sie bereits den Topologie-Generator ausgeführt haben, um Ihre Edgeservertopologie zu definieren und zu veröffentlichen, und Sie müssen die Topologie auf Medien exportiert haben, auf die vom Edgeserver aus zugegriffen werden kann. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und [Exportieren der Lync Server 2013-Topologie und Kopieren auf externe Medien zur Edgeinstallation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Wenn Sie alle Edgeserver mit dem Bereitstellungs-Assistenten installiert und die erforderlichen Zertifikate installiert und zugewiesen haben, können Sie das Setup mithilfe der Informationen unter [Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dazu verwenden, den externen Benutzerzugriff zu aktivieren und zu konfigurieren. Mithilfe der Informationen unter [Überprüfen der Edgebereitstellung in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) können Sie das Setup einschließlich Server- und Clientkonnektivität überprüfen.

## So installieren Sie einen Edgeserver

1.  Melden Sie sich als Mitglied der lokalen Administratorgruppe bei dem Computer an, auf dem Sie den Edgeserver installieren möchten, oder verwenden Sie ein Konto mit gleichwertigen Benutzerrechten und -berechtigungen.

2.  Stellen Sie sicher, dass die Topologiekonfigurationsdatei, die Sie mit dem Topologie-Generator erstellt und auf externe Medien kopiert haben, auf dem Edgeserver verfügbar ist (schließen Sie beispielsweise das USB-Laufwerk, auf das Sie die Topologiekonfigurationsdatei kopiert haben, an den Edgeserver an, oder gewähren Sie Zugriff auf die Netzwerkfreigabe, auf die die Datei kopiert wurde).

3.  Starten Sie den Bereitstellungs-Assistenten.
    

    > [!NOTE]
    > Wenn Sie in einer Meldung dazu aufgefordert werden, Microsoft Visual C++ Redistributable zu installieren, klicken Sie auf <STRONG>Ja</STRONG> . Im nächsten Dialogfeld können Sie den vorgegebenen <STRONG>Installationsspeicherort</STRONG> akzeptieren oder auf <STRONG>Durchsuchen</STRONG> klicken, um einen alternativen Speicherort anzugeben. Klicken Sie anschließend auf <STRONG>Installieren</STRONG> . Aktivieren Sie im nächsten Dialogfeld das Kontrollkästchen <STRONG>Ich stimme den Bedingungen des Lizenzvertrags zu</STRONG> , und klicken Sie auf <STRONG>OK</STRONG> .



4.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren** .

5.  Klicken Sie nach Abschluss der Bereitstellungsphase durch den Assistenten unter **Schritt 1. Lokalen Konfigurationsspeicher installieren** auf **Ausführen** , und führen Sie die folgenden Schritte aus:
    
      - Klicken Sie im Dialogfeld **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** auf **Aus Datei importieren (für Edgeserver empfohlen)** , wechseln Sie zum Speicherort der exportierten Topologiekonfigurationsdatei, wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen** und anschließend auf **Weiter** .
    
      - Der Bereitstellungs-Assistent liest die Konfigurationsinformationen aus der Konfigurationsdatei aus und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
      - Nachdem der Prozess **Befehle ausführen** abgeschlossen wurde, klicken Sie auf **Fertig stellen** .

6.  Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** , um die Lync Server 2013-Edgekomponenten zu installieren, die in der lokal gespeicherten XML-Konfigurationsdatei angegeben sind.

7.  Verwenden Sie nach Abschluss der Installation die Informationen unter [Einrichten von Edgezertifikaten für Lync Server 2013](lync-server-2013-set-up-edge-certificates.md), um vor dem Start der Dienste die erforderlichen Zertifikate zu installieren und zuzuweisen.

