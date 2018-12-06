---
title: 'Lync Server 2013: Ausführen der Gesamtstrukturvorbereitung'
TOCTitle: Ausführen der Gesamtstrukturvorbereitung
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412732(v=OCS.15)
ms:contentKeyID: 49294899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen der Gesamtstrukturvorbereitung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Für die Vorbereitung der Gesamtstruktur können Sie Setup oder Lync Server-Verwaltungsshell-Cmdlets nutzen. Das Cmdlet, das die Gesamtstruktur vorbereitet, ist **Enable-CsAdForest**.

Nach der Vorbereitung der Gesamtstruktur, müssen Sie vor der Domänenvorbereitung sicherstellen, dass die globalen Einstellungen repliziert wurden.

## So verwenden Sie Setup zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem an eine Domäne angeschlossenen Computer als Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur-Stammdomäne an.

2.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten** , und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie in **Schritt 3: Aktuelle Gesamtstruktur vorbereiten** auf **Ausführen** .

5.  Klicken Sie auf der Seite **Gesamtstruktur vorbereiten** auf **Weiter** .
    

    > [!NOTE]
    > Bei der Vorbereitung der Gesamtstruktur können Sie auswählen, wo die universellen Gruppen für Lync Server 2013 abgelegt werden sollen. Wählen Sie einen Speicherort entsprechend den Anforderungen Ihrer Organisation.



6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** , und klicken Sie dann auf **Protokoll anzeigen** .

7.  Erweitern Sie in der Spalte **Aktion** die Option **Gesamtstrukturvorbereitung** , und achten Sie am Ende jeder Aufgabe auf das Ausführungsergebnis **\<Erfolg\>** , um sicherzustellen, dass die Gesamtstrukturvorbereitung erfolgreich abgeschlossen wurde. Schließen Sie das Protokoll, und klicken Sie auf **Fertig stellen** .

8.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Gesamtstruktur-Stammdomäne aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen. Erzwingen Sie die Replikation zwischen den Domänencontrollern an allen Active Directory-Standorten, damit die Replikation an den Standorten innerhalb von Minuten durchgeführt werden kann.

## So verwenden Sie Cmdlets zum Vorbereiten der Gesamtstruktur

1.  Melden Sie sich bei einem Domänencomputer als Mitglied der Gruppe "Domänen-Admins" in der Stammdomäne der Gesamtstruktur an.

2.  Installieren Sie die Lync Server-Hauptkomponenten wie folgt:
    
    1.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Sie werden im Dialogfeld für das Lync Server 2013-Setup aufgefordert, einen Speicherort für die Installation der Lync Server-Dateien anzugeben. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren** .
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** , und klicken Sie dann auf **OK** . Das Installationsprogramm installiert die Hauptkomponenten von Lync Server 2013.

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Beispiel:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Wenn Sie den Parameter "GroupDomain" nicht angeben, wird standardmäßig die lokale Domäne verwendet. Wenn zuvor universelle Gruppen in einer Domäne erstellt wurden, bei der es sich nicht um die Standarddomäne handelt, muss der Parameter "GroupDomain" explizit angegeben werden.

5.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In **Active Directory-Standorte und -Dienste** für den Domänencontroller der Stammdomäne der Gesamtstruktur aufgelistet sind, bevor Sie die Domänenvorbereitung ausführen.

6.  Überprüfen Sie, ob die Vorbereitung der Gesamtstruktur erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdForest 
    
    Bei erfolgreicher Gesamtstrukturvorbereitung gibt dieses Cmdlet den Wert **LC\_FORESTSETTINGS\_STATE\_READY** zurück.

## Siehe auch

#### Aufgaben

[Verwenden von Cmdlets zum Rückgängigmachen der Gesamtstrukturvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  

#### Weitere Ressourcen

[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)

