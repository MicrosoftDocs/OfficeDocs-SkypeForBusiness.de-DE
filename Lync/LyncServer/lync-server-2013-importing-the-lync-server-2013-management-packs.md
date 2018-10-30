---
title: Importieren der Lync Server 2013 Management Packs
TOCTitle: Importieren der Lync Server 2013 Management Packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205052(v=OCS.15)
ms:contentKeyID: 49294619
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importieren der Lync Server 2013 Management Packs

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie die Management Packs installieren – Software, die bestimmt, welche Elemente von System Center Operations Manager überwacht werden können und wie diese Elemente überwacht werden sollen, wie Benachrichtigungen ausgelöst und gemeldet werden sollen. Lync Server 2013 enthält zwei System Center Operations Manager Management Packs, die folgende Funktionen bieten:

  - Mit dem Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) werden Lync Server-Probleme nachverfolgt, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in Kommunikationsdatensatz- (KDS) und QoE-Datenbanken protokolliert sind. Für schwerwiegende Probleme kann der System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per E-Mail, Sofortnachricht oder SMS benachrichtigt werden. Mit der SMS-Technologie werden Textnachrichten von einem mobilen Gerät zu einem anderen gesendet.)
    

    > [!NOTE]
    > Ausführliche Informationen zur Konfiguration von Operations Manager-Benachrichtigungen finden Sie im Artikel "Benachrichtigungen konfigurieren" in der TechNet-Bibliothek unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x407</A>.



  - Das Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) testet proaktiv wichtige Lync Server-Komponenten, wie beispielsweise das Anmelden beim System, das Austauschen von Sofortnachrichten oder das Tätigen von Anrufen im Telefonfestnetz (Public Switched Telephone Network, PSTN). Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen von Lync Server durchgeführt. Beispielsweise können Sie das Cmdlet **Test-CsIM** verwenden, um eine Konversation mit Sofortnachrichten zwischen einem Testbenutzerpaar zu simulieren. Wenn bei dieser simulierten Konversation mit Sofortnachrichten ein Fehler auftritt, wird eine Warnung generiert.

Sie müssen die Management Packs importieren. Wenn Sie die Management Packs nicht importieren, können Sie Operations Manager nicht zur Überwachung von Lync Server-Ereignissen verwenden oder synthetische Transaktionen für Lync Server ausführen.

Das Component and User Management Pack wird nur verwendet, um Lync Server 2013 zu überwachen. Wenn Sie sich in einem Koexistenzszenario befinden, wo sowohl Lync Server 2013 als auch Lync Server 2010 installiert sind, sollten Sie weiterhin die Management Packs von Lync Server 2010 für Ihre Lync Server 2010-Computer verwenden.


> [!NOTE]
> Management Packs für Lync Server 2010 enthalten das Monitoring Management Pack von Lync Server 2010 sowie das Group Chat Monitoring Management Pack von Lync Server 2010.



Zum Importieren der Management Packs können folgende Tools verwendet werden:

  - **System Center Operations Manager**   Mit dieser Methode wird Operations Manager verwendet, um die Überwachungsfunktion für Lync Server hinzuzufügen.

  - **Operations Manager-Shell**   Die Operations Manager-Shell kann zum direkten Importieren verwendet werden oder um alle Probleme zu behandeln, die beim Importieren der Management Packs mit der System Center Operations Manager-Konsole auftreten.

## Importieren der Verwaltungspakete mit dem System Center Operations Manager

1.  Laden Sie die Dateien "Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp" und "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" herunter.

2.  Klicken Sie im System Center Operations Manager auf **Verwaltung**.

3.  Klicken Sie auf der Verwaltungsseite mit der rechten Maustaste auf **Management Packs**, und klicken Sie anschließend auf **Management Packs importieren**.

4.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5.  Klicken Sie im Dialogfeld **Verbindung mit dem Onlinekatalog** auf **Abbrechen**, damit verhindert wird, dass für Operations Manager eine Onlineverbindung hergestellt wird, um zu überprüfen, ob Abhängigkeiten mit den Management Packs von Lync Server bestehen. Wenn Sie System Center Operations Manager 2012 verwenden, klicken Sie auf **Nein**.

6.  Suchen Sie im Dialogfeld **Zu importierende Management Packs auswählen** die Dateien **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** und **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, und wählen Sie sie aus, und klicken Sie anschließend auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie dann die STRG-TASTE gedrückt, und klicken Sie dann auf die zweite Datei.

7.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner, und starten Sie den Import- und Installationsvorgang erneut.

8.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Beachten Sie, dass der Import- und Installationsvorgang mehrere Minuten dauern kann.

## Importieren der Management Packs mit Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mit Operations Manager zu importieren. Wenn jedoch ein Fehler auftritt und bei der Installation Fehler auftreten, stellt die Konsole nicht immer ausreichende Fehlerberichte bereit. Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Fehler auftreten, importieren Sie das Management Pack mit der Operations Manager-Shell. Die Operations Manager-Shell kann weitere hilfreiche Informationen bieten, um festzustellen, warum beim Import Fehler aufgetreten sind.

Führen Sie die folgenden Schritte aus, wenn Sie System Center Operations Manager 2007 R2 verwenden:

1.  Klicken Sie auf **Start**, dann auf **Alle Programme**, anschließend auf **System Center Operations Manager 2007 R2** und dann auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, und drücken Sie die EINGABETASTE. Verwenden Sie dabei den tatsächlichen Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp":
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" verwenden:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Schließen Sie die Operations Manager-Shell.

Sollten Sie System Center Operations Manager 2012 verwenden, führen Sie stattdessen folgendes Verfahren durch:

1.  Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, und drücken Sie die EINGABETASTE. Verwenden Sie dabei den tatsächlichen Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp":
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" verwenden:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

