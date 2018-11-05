---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
TOCTitle: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49890782
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen der SQL Server-Datenbank für einen Front-End-Pool

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nachdem Sie einen Microsoft Lync Server 2010  Front-End-Pool entfernt oder zur Verwendung einer anderen Datenbank umkonfiguriert haben, können Sie die SQL Server-Datenbanken entfernen, in denen die Pooldaten gehostet wurden. Mithilfe der folgenden Vorgehensweisen können Sie die Definitionen aus dem Topologie-Generator und dann die Datenbank und die Protokolleinträge auf dem Datenbankserver entfernen.

## So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.

2.  Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und dann zu **SQL Server-Speicher** . Klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen** .

3.  Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.

## So entfernen Sie Benutzer- und Anwendungsdatenbanken aus dem SQL Server-basierten Server

1.  Zum Entfernen der Datenbanken auf dem SQL Server müssen Sie Mitglied der SQL Server-Gruppe "sysadmins" für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie Folgendes ein, um die Datenbank für den Poolbenutzerspeicher zu entfernen:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei ist *\<FQDN\>* der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und *\<instance\>* die benannte Datenbankinstanz (sofern eine definiert wurde).

4.  Geben Sie Folgendes ein, um die Datenbank für den Poolanwendungsspeicher zu entfernen:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei ist *\<FQDN\>* der vollqualifizierte Domänenname des Datenbankservers und *\<instance\>* die benannte Datenbankinstanz (sofern eine definiert wurde).

5.  Wenn Sie vom Cmdlet **Uninstall-CsDataBase** aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **Y** (oder die EINGABETASTE), oder drücken Sie **N** und dann die EINGABETASTE, wenn Sie die Ausführung des Cmdlets beenden möchten (im Falle von Fehlern).

