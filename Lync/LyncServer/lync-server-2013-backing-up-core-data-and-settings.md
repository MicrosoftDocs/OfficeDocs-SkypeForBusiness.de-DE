---
title: Sichern von Hauptdaten und -einstellungen
TOCTitle: Sichern von Hauptdaten und -einstellungen
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202170(v=OCS.15)
ms:contentKeyID: 52056309
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sichern von Hauptdaten und -einstellungen

 

_**Letztes Änderungsdatum des Themas:** 2014-04-23_

Bei den folgenden Verfahren werden Lync Server-Verwaltungsshell-Cmdlets verwendet, um Sicherungsdateien für Einstellungen und Daten für wichtige Dienste zu erstellen. Ausführliche Informationen zu den in diesem Abschnitt eingesetzten Tools und Angaben dazu, wo Sie diese finden, erhalten Sie unter [Anforderungen für die Sicherung und Wiederherstellung: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Einzelheiten zum Sichern von Archivierungs- und Überwachungsdaten finden Sie unter [Sichern von Archivierungs- und Überwachungsdatenbanken](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).


> [!NOTE]
> Der Schritt zum Sichern des zentralen Verwaltungsspeichers umfasst die Einstellungen und die Konfiguration für die Archivierung und das Monitoring.



Sie können die in diesem Abschnitt beschriebenen Cmdlets lokale oder remote ausführen.

## So sichern Sie wichtige Daten und Einstellungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe **RTCUniversalServerAdmins** ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Zum Speichern der Sicherungen, die Sie in den folgenden Schritten erstellen, legen Sie einen neuen freigegebenen Ordner an und aktualisieren Sie den Pfad, der von **$Backup** referenziert wid, auf den neuen freigegebenen Ordner.

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Sichern Sie die Konfigurationsdatei des zentralen Verwaltungsspeichers. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Beispiel:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    

    > [!NOTE]
    > Mit diesem Schritt werden die Topologie, die Richtlinien und die Konfigurationseinstellungen für Lync Server in eine Datei exportiert. Weitere Schritte sind zum Sichern der Topologiedaten nicht erforderlich.



5.  Kopieren Sie die gesicherte Konfigurationsdatei des zentralen Verwaltungsspeichers in "$Backup\\".

6.  Sichern Sie die Standortinformationsdienst-Daten. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Beispiel:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Kopieren Sie die gesicherte Konfigurationsdatei des Standortinformationsdiensts in "$Backup\\".

8.  Sichern Sie die Benutzerdaten in jeder Back-End-Datenbank eines Front-End-Pools und auf jedem Standard Edition-Server. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Beispiel:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Kopieren Sie die gesicherte Benutzerdatei in **$Backup\\**.

10. Sichern Sie in jedem Pool, in dem die Reaktionsgruppenanwendung ausgeführt wird, die Konfigurationsdatei der Reaktionsgruppe. Gehen Sie folgendermaßen vor:
    
    1.  Geben Sie an der Befehlszeile Folgendes ein:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Beispiel:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Kopieren Sie die gesicherte Konfigurationsdatei für die Reaktionsgruppe in **$Backup\\**.

