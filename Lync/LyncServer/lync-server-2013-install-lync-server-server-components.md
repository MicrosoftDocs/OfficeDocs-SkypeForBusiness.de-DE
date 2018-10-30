---
title: 'Lync Server 2013: Installieren von Lync Server-Serverkomponenten'
TOCTitle: Installieren von Lync Server-Serverkomponenten
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398239(v=OCS.15)
ms:contentKeyID: 49293315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Serverkomponenten für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-05-05_

Vergewissern Sie sich vor dem Ausführen dieser Arbeitsschritte, dass Sie beim Server unter einem Domänenkonto angemeldet sind, das lokale Administratorrechte besitzt und Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" von Active Directory ist.

Der Lync Server-Bereitstellungs-Assistent wird zum Installieren der Komponenten verwendet, die für jede Lync-Serverrolle und zum Aktivieren des Servers erforderlich sind. In diesem Artikel werden Sie durch die Schritte zum Bereitstellen des Standard Edition-Servers oder des Front-End-Servers in Ihrer Lync-Infrastruktur geführt.

## So installieren Sie Lync Server-Komponenten

1.  Wenn der Lync Server-Bereitstellungs-Assistent nicht bereits ausgeführt wird, starten Sie ihn auf dem Server, auf dem Lync installiert werden soll.

2.  Klicken Sie auf **Lync Server-System installieren oder aktualisieren**.

3.  Überprüfen Sie im Bereitstellungs-Assistenten, ob neben **Schritt 1: Installieren des lokalen Konfigurationsspeichers** ein grünes Häkchen angezeigt wird, da dies bedeutet, dass auf dem Server eine lokale Kopie des Speichers installiert wurde. Wird kein Häkchen angezeigt, müssen Sie zunächst den lokalen Konfigurationsspeicher auf dem Server installieren. Führen Sie dazu die Vorgehensweise unter [Installieren des lokalen Konfigurationsspeichers in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) aus und fahren Sie dann mit diesen Arbeitsschritten fort.

4.  Wenn Sie zur Installation der Lync Server 2013-Komponenten bereit sind, klicken Sie neben **Schritt 2: Einrichten oder Entfernen von Lync Server-Komponenten** auf **Ausführen**.

5.  Klicken Sie auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**, um die Komponenten gemäß der Definition in der veröffentlichten Topologie einzurichten.

6.  Auf der Seite **Befehle ausführen** werden während der Ausführung des Vorgangs eine Zusammenfassung der Befehle und Installationsinformationen angezeigt. Nach Abschluss des Vorgangs können Sie in der angezeigten Liste ein Protokoll auswählen und auf **Protokoll anzeigen** klicken.

7.  Nachdem die Lync Server 2013-Komponenten eingerichtet wurden und Sie die Protokolle ggf. geprüft haben, klicken Sie auf **Fertig stellen**, um diesen Installationsschritt abzuschließen.
    

    > [!NOTE]
    > Wenn Sie aufgefordert werden, den Server neu zu starten (dies ist der Fall, wenn Windows Desktop Experience installiert werden musste), sollten Sie dies unbedingt tun. Nach erfolgtem Neustart müssen Sie dann diese Schritte ab Schritt 3 oben noch einmal wiederholen (d.&nbsp;h. führen Sie Schritt 2 im Bereitstellungs-Assistenten noch einmal aus).


