---
title: 'Lync Server 2013: Installieren der Dateien für den Vermittlungsserver'
TOCTitle: Installieren der Dateien für den Vermittlungsserver
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412998(v=OCS.15)
ms:contentKeyID: 49295855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren der Dateien für den Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-06_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" ist.

Führen Sie den Lync Server 2013-Bereitstellungs-Assistenten anhand der hier beschriebenen Schritte aus, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie beim Definieren und Veröffentlichen des Pools mithilfe des Topologie-Generators einem Vermittlungsserverpool hinzugefügt haben. Während der Installation der Dateien für den Vermittlungsserver installieren Sie auch die Zertifikate, die alle Computer in einem Vermittlungsserverpool benötigen, und weisen diese zu.

Wenn Sie an diesem Standort bereits Vermittlungsserver bereitgestellt haben, die in den Front-End-Pools oder auf dem Standard Edition-Server gemeinsam ausgeführt werden, können Sie dieses Thema überspringen und stattdessen mit [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) fortfahren.


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen Vermittlungsserverpool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Definieren eines Vermittlungsservers im Topologie-Generator in Lync Server 2013</A> und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in Lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben. Ferner wird vorausgesetzt, dass Sie sichergestellt haben, dass die Computer im Vermittlungsserverpool die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Erforderliche Software für Enterprise-VoIP in Lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Lync Server 2013</A> beschriebenen Voraussetzungen erfüllen.



## So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool

1.  Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf *\<Installationsmedium\>* **\\Setup\\amd64\\Setup.exe** , und klicken Sie anschließend auf **Als Administrator ausführen** .

2.  Klicken Sie auf der Seite **Installationsspeicherort** auf **OK** .

3.  Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** , und klicken Sie anschließend auf **OK** . (Dieser Schritt ist erforderlich, um fortfahren zu können.)

4.  Klicken Sie auf der Seite **Lync Server 2010-Bereitstellungs-Assistent** auf **Lync Server-System installieren oder aktualisieren** .

5.  Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** , und folgen Sie den Anweisungen auf dem Bildschirm.

6.  Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** , und klicken Sie auf **Weiter** .

7.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen** .

8.  Klicken Sie neben **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** auf **Ausführen** und anschließend auf **Weiter** .

9.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen** .

10. Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen** . Folgen Sie den Anweisungen auf dem Bildschirm, und übernehmen Sie die Standardeinstellungen. Der Vermittlungsserver benötigt ein Zertifikat, Sie müssen **Schritt 3** also zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.

11. Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** , und folgen Sie den Anweisungen auf dem Bildschirm.

12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu, und melden Sie sich als Mitglied der Gruppe "Domänen-Admins" an.

13. Überprüfen Sie auf dem Computer, auf dem die Lync Server-Systemsteuerung ausgeführt wird, ob auf der Seite **Topologie** der Lync Server-Systemsteuerung für den Dienststatus des Vermittlungsservers ein grünes Häkchen angezeigt wird. Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus. Klicken Sie im Menü **Aktion** auf **Alle Dienste starten** .

Wenn Sie dem Vermittlungsserverpool mehr als einen Computer hinzugefügt haben, führen Sie die hier beschriebenen Schritte für alle Computer in diesem Vermittlungsserverpool aus. Wenn Sie keine Vermittlungsserverdateien für weitere Computer installieren müssen, führen Sie die unter [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) beschriebenen Schritte aus, um Einstellungen für die Trunkverbindung zwischen diesem Vermittlungsserverpool (bzw. allen Vermittlungsservern an diesem Standort) und dem zugehörigen Peer zu konfigurieren.

## Siehe auch

#### Konzepte

[Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

