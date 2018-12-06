---
title: 'Lync Server 2013: Ausführen der Schemavorbereitung'
TOCTitle: Ausführen der Schemavorbereitung
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412729(v=OCS.15)
ms:contentKeyID: 49294897
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für die Vorbereitung des Active Directory-Schemas können Sie Setup oder Lync Server-Verwaltungsshell-Cmdlets nutzen. Das Cmdlet für die Erweiterung des Active Directory-Schemas ist **Install-CsAdServerSchema**.


> [!NOTE]
> Das Cmdlet für die Schemavorbereitung ( <STRONG>Install-CsAdServerSchema</STRONG>) muss auf den Schemamaster zugreifen. Dazu muss der Remoteregistrierungsdienst ausgeführt werden und der Remoteregistrierungsschlüssel aktiviert sein. Falls der Remoteregistrierungsdienst nicht auf dem Schemamaster aktiviert werden kann, können Sie das Cmdlet lokal auf dem Schemamaster ausführen. Ausführliche Informationen über den Remotezugriff auf die Registrierung finden Sie im Microsoft Knowledge Base-Artikel 314837 "Steuerung des Remotezugriffs auf die Registrierung" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.



Stellen Sie nach Abschluss der Schemavorbereitung manuell sicher, dass die Schemapartition repliziert wurde, bevor Sie mit der Vorbereitung der Gesamtstruktur fortfahren. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Setup vor

1.  Melden Sie sich bei einem Server in der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten auf dem Schemamaster an.

2.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.

4.  Sie werden im Dialogfeld für das Lync Server 2013-Setup aufgefordert, einen Speicherort für die Installation der Lync Server-Dateien anzugeben. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren** .

5.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** , und klicken Sie dann auf **OK** .

6.  Das Installationsprogramm installiert die Hauptkomponenten von Lync Server.

7.  Wenn der Bereitstellungs-Assistent bereit ist, klicken Sie auf **Active Directory vorbereiten** , und warten Sie das Bestimmen des Bereitstellungsstatus ab.

8.  Klicken Sie unter **Schritt 1: Schema vorbereiten** auf **Ausführen** .

9.  Klicken Sie auf der Seite **Schema vorbereiten** auf **Weiter** .

10. Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** , und klicken Sie dann auf **Protokoll anzeigen** .

11. Erweitern Sie in der Spalte **Aktion** die Option **Schemavorbereitung** , und achten Sie am Ende jeder Aufgabe auf das Ausführungsergebnis **\<Erfolg\>** , um sicherzustellen, dass die Schemavorbereitung erfolgreich abgeschlossen wurde. Schließen Sie das Protokoll, und klicken Sie auf **Fertig stellen** .

12. Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

13. Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## So bereiten Sie das Schema der aktuellen Gesamtstruktur mithilfe von Cmdlets vor

1.  Melden Sie sich bei einem Computer der Gesamtstruktur als Mitglied der Gruppe "Schema-Admins" und mit Administratorrechten für den Schemamaster an.

2.  Installieren Sie die Lync Server-Hauptkomponenten wie folgt:
    
    1.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Sie werden im Dialogfeld für das Lync Server 2013-Setup aufgefordert, einen Speicherort für die Installation der Lync Server-Dateien anzugeben. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren** .
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** , und klicken Sie dann auf **OK** . Das Installationsprogramm installiert die Hauptkomponenten von Lync Server 2013.

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Wenn Sie den Parameter "Ldf" nicht angeben, ist der Standardwert der Lync Server 2013-Installationspfad, der aus der Registrierung gelesen wird.
    
    Beispiel:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Überprüfen Sie mit dem folgenden Cmdlet, ob die Schemavorbereitung erfolgreich abgeschlossen wurde.
    
        Get-CsAdServerSchema 
    
    Bei erfolgreicher Schemavorbereitung gibt dieses Cmdlet den Wert **SCHEMA\_VERSION\_STATE\_CURRENT** zurück.

6.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation.

7.  Stellen Sie anhand des folgenden Verfahrens manuell sicher, dass die Schemaänderungen auf alle übrigen Domänencontroller repliziert wurden. Ausführliche Informationen finden Sie unter [Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## Siehe auch

#### Aufgaben

[Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  

#### Konzepte

[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

