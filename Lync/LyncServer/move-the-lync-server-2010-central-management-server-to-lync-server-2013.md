---
title: Verschieben des zentralen Lync Server 2010-Verwaltungsservers zu Lync Server 2013
TOCTitle: Verschieben des zentralen Lync Server 2010-Verwaltungsservers zu Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49890690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben des zentralen Lync Server 2010-Verwaltungsservers zu Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-25_

Nach der Migration von Lync Server 2010 zu Lync Server 2013 müssen Sie den zentraler Verwaltungsserver aus Lync Server 2010 zum Front-End-Server oder zum Pool in Lync Server 2013 verschieben, bevor Sie den Lync Server 2010-Legacyserver entfernen können.

Der zentrale Verwaltungsserver ist ein Einzelmaster/Mehrfachreplikat-System, bei dem die Datenbankkopie mit Lese-/Schreibberechtigung vom Front-End-Server verwaltet wird, der den zentralen Verwaltungsserver enthält. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver umfasst, verfügt über eine schreibgeschützte Kopie der Daten für den zentralen Verwaltungsspeicher in der SQL Server-Datenbank (heißt standardmäßig RTCLOCAL), die während des Setups und der Bereitstellung auf dem Computer installiert wird. Die lokale Datenbank empfängt Replikataktualisierungen über den Replikat-Replikations-Agent von Lync Server, der auf allen Computern als Dienst ausgeführt wird. Der Name der eigentlichen Datenbank auf dem zentralen Verwaltungsserver und des lokalen Replikats lautet XDS und besteht aus den Dateien xds.mdf und xds.ldf. Auf den Speicherort der Masterdatenbank wird mit einem Dienstverbindungspunkt (Service Control Point, SCP) in Active Directory-Domänendienste verwiesen. Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Lync Server verwenden, nutzen den Dienstverbindungspunkt, um den zentralen Verwaltungsspeicher aufzufinden.

Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken für den zentralen Verwaltungsserver vom ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen von Datenbanken für den zentralen Verwaltungsserver finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).

Sie können das Windows PowerShell-Cmdlet **Move-CsManagementServer** in der Lync Server-Verwaltungsshell verwenden, um die Datenbank aus der SQL Server-Datenbank in Lync Server 2010 zur SQL Server-Datenbank in Lync Server 2013 zu verschieben, und anschließend den Dienstverbindungspunkt aktualisieren, sodass er auf den Speicherort des zentralen Verwaltungsservers in Lync Server 2013 verweist.

## Vorbereiten der Lync Server 2013Front-End-Server vor dem Verschieben des zentralen Verwaltungsservers

Gehen Sie wie in diesem Abschnitt beschrieben vor, um die Lync Server 2013- Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungsserver aus Lync Server 2010 verschieben.

## So bereiten Sie einen Enterprise Edition- Front-End-Pool vor

1.  Gehen Sie im Lync Server 2013 Enterprise Edition- Front-End-Pool, zu dem Sie den zentralen Verwaltungsserver verschieben möchten, wie folgt vor: Melden Sie sich an dem Computer an, auf dem die Lync Server-Verwaltungsshell als Mitglied der Rolle **RTCUniversalServerAdmins** installiert ist. Darüber hinaus benötigen Sie Systemadministratorrechte und -berechtigungen für die SQL Server-Datenbank, in der Sie den zentralen Verwaltungsspeicher installieren möchten.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein, um den neuen zentralen Verwaltungsspeicher in der SQL Server-Datenbank in Lync Server 2013 zu erstellen:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.

## So bereiten Sie einen Standard Edition- Front-End-Server vor

1.  Gehen Sie auf dem Lync Server 2013 Standard Edition- Front-End-Server, zu dem Sie den zentralen Verwaltungsserver verschieben möchten, wie folgt vor: Melden Sie sich an dem Computer an, auf dem Lync Server-Verwaltungsshell als Mitglied der Rolle **RTCUniversalServerAdmins** installiert ist.

2.  Öffnen Sie die Lync Server-Bereitstellungs-Assistent.

3.  Klicken Sie im Lync Server-Bereitstellungs-Assistenten auf **Vorbereiten des ersten Standard Edition-Servers** .

4.  Auf der Seite **Befehle ausführen** installieren Sie SQL Server Express als zentralen Verwaltungsserver. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen** , wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    

    > [!NOTE]
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies hängt mit der Installation der SQL Server Express zusammen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen.



5.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein, um den neuen zentralen Verwaltungsspeicher auf dem Lync Server 2013 Standard Edition- Front-End-Server zu erstellen:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Bestätigen Sie, dass der Dienst **Lync Server-Front-End** den Status **Gestartet** aufweist.

## So verschieben Sie den zentralen Verwaltungsserver aus Lync Server 2010 zu Lync Server 2013

1.  Gehen Sie auf dem Lync Server 2013-Server, der als zentraler Verwaltungsserver dienen soll, wie folgt vor: Melden Sie sich an dem Computer an, auf dem die Lync Server-Verwaltungsshell als Mitglied der Gruppe **RTCUniversalServerAdmins** installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein:
    
        Enable-CsTopology
    

    > [!WARNING]
    > Sollte <CODE>Enable-CsTopology</CODE> nicht erfolgreich sein, beheben Sie dieses Problem, bevor Sie den Vorgang fortsetzen. Wenn <STRONG>Enable-CsTopology</STRONG> nicht erfolgreich ausgeführt wird, tritt beim Verschieben ein Fehler auf, und die Topologie weist möglicherweise einen Status auf, in dem kein zentralen Verwaltungsspeicher vorhanden ist.



4.  Geben Sie auf dem Lync Server 2013- Front-End-Server oder im Front-End-Pool Folgendes in die Lync Server-Verwaltungsshell ein:
    
        Move-CsManagementServer

5.  Die Lync Server-Verwaltungsshell zeigt die Server, Dateispeicher, Datenbankspeicher und Dienstverbindungspunkte für **Aktueller Zustand** und **Vorgeschlagener Zustand** an. Lesen Sie die Informationen sorgfältig durch, und bestätigen Sie, dass es sich um die gewünschte Quelle und das gewünschte Ziel handelt. Geben Sie **J** ein, um das Verschieben fortzusetzen, oder geben Sie **N** ein, um das Verschieben zu beenden.

6.  Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese.

7.  Öffnen Sie auf dem Lync Server 2013-Server den Lync Server-Bereitstellungs-Assistenten.

8.  Klicken Sie im Lync Server-Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren** , klicken Sie auf **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** , klicken Sie auf **Weiter** , überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen** .

9.  Öffnen Sie auf dem Lync Server 2010-Server den Lync Server-Bereitstellungs-Assistenten.

10. Klicken Sie im Lync Server-Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren** , klicken Sie auf **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** , klicken Sie auf **Weiter** , überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen** .

11. Starten Sie den Lync Server 2013-Server neu. Dies ist wegen einer Gruppenmitgliedschaftsänderung für den Zugriff auf die zentraler Verwaltungsserver-Datenbank erforderlich.

12. Geben Sie in der Lync Server-Verwaltungsshell Folgendes ein, um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher ausgeführt wird:
    
        Get-CsManagementStoreReplicationStatus
    

    > [!NOTE]
    > Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden.



## So entfernen Sie Dateien des zentralen Verwaltungsspeichers nach dem Verschieben aus Lync Server 2010

1.  Führen Sie auf dem Lync Server 2010-Server die folgenden Schritte aus: Melden Sie sich an dem Computer an, auf dem die Lync Server-Verwaltungsshell als Mitglied der Gruppe **RTCUniversalServerAdmins** installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.
    

    > [!WARNING]
    > Fahren Sie mit dem Entfernen der vorherigen Datenbankdateien erst fort, wenn die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor Abschluss der Replikation entfernen, unterbrechen Sie den Replikationsprozess, weshalb der neu verschobene zentrale Verwaltungsserver einen unbekannten Status aufweist. Bestätigen Sie den Replikationsstatus mithilfe des Cmdlets <STRONG>Get-CsManagementStoreReplicationStatus</STRONG>.



3.  Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers vom zentralen Verwaltungsserver in Lync Server 2010 zu entfernen:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Beispiel:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Dabei ist *\<FQDN of SQL Server\>* entweder der Lync Server 2010 Back-End-Server in einer Enterprise Edition-Bereitstellung oder der FQDN des Standard Edition-Servers.

