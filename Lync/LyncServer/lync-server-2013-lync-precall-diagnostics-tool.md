---
title: Lync PreCall-Diagnosetool
TOCTitle: Lync PreCall-Diagnosetool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn451255(v=OCS.15)
ms:contentKeyID: 59373610
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync PreCall-Diagnosetool

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Das Lync PreCall-Diagnosetool (PCD) ist eine clientbasierte Anwendung, die es Ihnen ermöglicht zu sehen, welchen Einfluss der aktuelle Zustand Ihres Netzwerks bei einem anstehende Enterprise-VoIP-Anruf ggf. auf die Audioqualität hat.

PCD ist insbesondere in Szenarien nützlich, in denen der letzte Hop eines Netzwerks wahrscheinlich das schwächste Glied ist (beispielsweise Laptops in einem öffentlichen Wi-Fi-Netzwerk oder Privatbenutzer). PCD erstellt einen kleinen Paketstream, der diesen letzten Abschnitt des Netzwerks durchquert. Anschließend analysiert das Tool den Paketstream, um die voraussichtlichen Auswirkungen von Jitter und Verlust in diesem Abschnitt auf die Anrufqualität zu ermitteln und einen entsprechenden Bericht bereitzustellen. PCD kann kontinuierlich auf dem Client ausgeführt werden, sogar wenn Anrufe getätigt werden. Der Paketstream hat keine wesentlichen Auswirkungen auf die Bandbreite.

**Die neueste Version des PCD, Version 1.1, umfasst die folgenden Verbesserungen:**

  - Unterstützung für längere Kennwörter, die jetzt bis zu 127 Zeichen lang sein können

  - Zusätzliche Diagnose für Anmeldeprobleme bei der Authentifizierung

  - Bessere Unterstützung für Lync-Hybridbereitstellungen

  - Updates für die Auswahl von Anmeldeinformationen

  - Stabilitätsverbesserungen

Wir freuen uns über jede Art von Feedback. Bitte senden Sie alle Supportanfragen oder Probleme an den Alias [PCD Feedback](mailto:pcdfb@microsoft.com) an <pcdfb@microsoft.com>.

Dieses Thema enthält die folgenden Abschnitte:

  - Versionen von Lync PCD

  - Systemanforderungen von Lync PCD

  - Features von Lync PCD

  - Ausführen von Lync PCD

  - Deinstallieren von Lync PCD

## Versionen von Lync PCD

In diesem Thema werden die folgenden Versionen des Tools beschrieben, die zum kostenlosen Download bereitstehen:

  - Windows Desktop-App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

  - Windows 8 Modern-App ([http://go.microsoft.com/fwlink/?LinkId=322110](http://go.microsoft.com/fwlink/p/?linkid=322110))


> [!NOTE]
> Benutzer von Lync für Office 365 können beide Versionen des PCD verwenden.



Wenn Sie eine ältere Version von PCD verwenden möchten, gilt Folgendes:

  - Die 32-Bit-Version von PCD steht als kostenloser Download im Microsoft Download Center unter [Office Communications Server 2007 R2, PreCallDiagnostic Resource Kit Tool (32 Bit)](http://go.microsoft.com/fwlink/p/?linkid=164769) zur Verfügung.

  - Die 64-Bit-Version von PCD ist in den Office Communications Server 2007 R2 Resource Kit-Tools enthalten, die als kostenloser Download im Microsoft Download Center unter [Office Communications Server 2007 R2 Resource Kit Tools](http://go.microsoft.com/fwlink/p/?linkid=145159) verfügbar sind.

## Systemanforderungen von Lync PCD


> [!NOTE]
> PCD setzt voraus, dass die Unified Communications-Web API (UCWA) installiert und so konfiguriert ist, dass mobile Clients in der Lync Server-Bereitstellung unterstützt werden. UCWA wird zusammen mit Lync Server installiert.



## Voraussetzungen für die Windows Desktop-App

  - Eine beliebige Edition des Betriebssystems Windows 7 oder Windows 8

  - Microsoft .NET Framework 4.5, verfügbar unter [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Anforderungen von Windows 8 Modern App

  - Eine beliebige Edition des Betriebssystems Windows 8

  - Microsoft .NET Framework 4.5, verfügbar unter [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Features von Lync PCD

Lync PCD bietet die folgenden Features:

  - Im Standardmodus bei Bedarf ausführen (2-Minuten-Bursts)

  - Im Modus "Immer aktiv" ausführen (bis zu 24 Stunden in der angedockten Ansicht)

  - Verlaufsansicht Ihrer Testläufe

  - Anmeldefehler diagnostizieren (nur Lync PCD für Windows 8)

![Lync PCD zeigt laufende Anmeldung (Screenshot)](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD zeigt laufende Anmeldung (Screenshot)")

  - Grafische Ansicht von Netzwerkmetriken – Netzwerk-MOS, Paketverlust und Jitter der Zwischenankunftszeit in der Vollbildansicht und der angedockten Ansicht

**Vollbildansicht**

![Ergebnisse des PreCall-Diagnosetools (Diagramme)](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Ergebnisse des PreCall-Diagnosetools (Diagramme)")

**Angedockte Ansicht**

![PreCall-Diagnosetool: Testergebnisse](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall-Diagnosetool: Testergebnisse")

## Ausführen von Lync PCD

## Ausführen der Windows Desktop-App

1.  Zum Starten von PCD auf einem Windows 7-System wählen Sie im Menü **Start** den Eintrag **PreCall Diagnostics** aus.
    
    Zum Starten von PCD auf einem Windows 8-System wählen Sie das Symbol im Startbildschirm aus, oder suchen Sie nach "PreCall Diagnostics".
    
    ![Symbol für PreCall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für PreCall-Diagnosetool")

2.  Wählen Sie beim Start des Tools Ihre bevorzugte Methode für die Bereitstellung von Anmeldeinformationen aus, und wählen Sie im Dialogfeld **PreCall Diagnostics Tool Options** den Netzwerkbetriebsmodus as. Klicken Sie dann auf **OK**.

3.  Klicken Sie auf die Schaltfläche **Start Test**, um mit der Ausführung der Diagnose zu beginnen.
    
    Wenn Sie sich für die Option **Use network credentials** entschieden haben, wird der Test sofort gestartet.
    
    Wenn Sie die Option **Let me enter my credentials** ausgewählt haben wird das Dialogfeld **Windows Security** geöffnet. Der Test wird gestartet, nachdem Sie Ihre Anmeldeinformationen eingegeben haben.

## Ausführen der Windows 8 Modern App


1.  Zum Starten von PCD wählen Sie das Symbol im Startbildschirm aus, oder suchen Sie nach "PreCall Diagnostics".
    
    ![Symbol für PreCall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für PreCall-Diagnosetool")

2.  Geben Sie beim Start des Tools Ihre Lync-Anmeldeinformationen ein, und wählen Sie **OK** aus.
    
    ![Anmelden beim Lync PreCall-Diagnosetool](images/Dn451255.88039914-4c68-48f6-a9fa-58cb4e3f3488(OCS.15).jpg "Anmelden beim Lync PreCall-Diagnosetool")

3.  Klicken Sie auf die Schaltfläche **Start Test**, um mit der Ausführung der Diagnose zu beginnen.

## Deinstallieren von Lync PCD

Gehen Sie zum Deinstallieren von Lync PCD je nach Betriebssystem wie folgt vor:

  - Öffnen Sie auf einem Windows 7-System die Systemsteuerung,wählen Sie **Programme und Funktionen** aus, und doppelklicken sie auf **Lync 2013 PreCall Diagnostics**.

  - Klicken Sie auf einem Windows 8-System mit der rechten Maustaste auf die PCD-Kachel, und klicken Sie dann in der App-Leiste am Fuß des Startbildschirms auf **Deinstallieren**.

