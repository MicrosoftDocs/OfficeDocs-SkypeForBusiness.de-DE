---
title: Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung anhand von Anmeldeinformationen
TOCTitle: Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung anhand von Anmeldeinformationen
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204632(v=OCS.15)
ms:contentKeyID: 49293008
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung anhand von Anmeldeinformationen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Wenn Ihr Monitorknotencomputer außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie ein etwas anderes Verfahren anwenden, um diesen Monitorknoten für die Ausführung synthetischer Transaktionen zu konfigurieren. Beachten Sie, dass Sie keinen Pool mit vertrauenswürdigen Anwendungen und keine vertrauenswürdige Anwendung erstellen sollten und ein Zertifikat installieren müssen, über das der Monitorknoten Benachrichtigungen an einen Computer im Umkreisnetzwerk senden kann. Dies bedeutet, dass Sie zwei separate Schritte ausführen müssen:

  - Aktualisieren der Mitgliedschaft für die Gruppe "RTC Local Read-only Administrators Group" des Computers

  - Installieren der Konfigurationsdateien des Monitorknotens

## Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-only Administrators"

Wenn der Monitorknoten außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie das Netzwerkdienstkonto auf dem Computer mit dem Monitorknoten der Gruppe "RTC Local Read-only Administrators" hinzufügen. Führen Sie dazu für den Monitorknoten die folgenden Schritte aus:

1.  Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Verwalten**.

2.  Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Doppelklicken Sie im Bereich "Gruppen" mit der rechten Maustaste auf **RTC Local Read-only Administrators**.

4.  Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **Hinzufügen**.

5.  Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen auf **Standorte**.

6.  Wählen Sie im Dialogfeld **Standorte** den Namen des Monitorknotencomputers aus, und klicken Sie dann auf **OK**.

7.  Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** den Text **Netzwerkdienst** ein, und klicken Sie auf **OK**.

8.  Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **OK**, und schließen Sie den **Server-Manager**.

Starten Sie den Monitorknotencomputer neu.

## Installieren der Konfigurationsdateien des Monitorknotens

Nachdem der Monitorknotencomputer neu gestartet wurde, ist der nächste Schritt das Ausführen der Datei "Watchernode.msi". Öffnen Sie zum Ausführen dieser Datei die Verwaltungsshell für Lync Server 2013, indem Sie nacheinander auf **Start**, **Alle Programme**, **Lync Server 2013** und **Lync Server-Verwaltungsshell** klicken. Geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie die EINGABETASTE (geben Sie den richtigen Pfad zu Ihrer Kopie der Datei "Watchernode.msi" an):

    C:\Tools\Watchernode.msi Authentication=Negotiate


> [!NOTE]
> Wie bereits erwähnt, kann die Datei "Watchernode.msi" auch über ein Befehlsfenster mit Eingabeaufforderung ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>. Geben Sie den bereits gezeigten Befehl ein, nachdem das Befehlsfenster geöffnet wurde.



Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.

