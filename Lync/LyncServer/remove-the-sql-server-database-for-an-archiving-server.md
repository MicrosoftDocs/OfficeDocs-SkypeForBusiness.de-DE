---
title: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
TOCTitle: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49890786
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen der SQL Server-Datenbank für einen Archivierungsserver

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nach dem Entfernen eines Microsoft Lync Server 2010- Archivierungsservers, können Sie die SQL Server-Datenbanken entfernen, in denen die Pooldaten gehostet wurden. Mithilfe der folgenden Verfahren können Sie die Definitionen aus dem Topologie-Generator entfernen und anschließend die Datenbank und die Protokolldateien vom Datenbankserver entfernen.

## So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server den Topologie-Generator.

2.  Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und dann zu **SQL Server-Speicher** . Klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Löschen** .

3.  Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.

## So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server

1.  Zum Entfernen der Datenbanken auf dem SQL Server müssen Sie Mitglied der SQL Server-Gruppe "sysadmins" für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden.

2.  Öffnen Sie die Lync Server-Verwaltungsshell.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei ist *\<FQDN\>* der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und *\<instance\>* die benannte Datenbankinstanz (sofern eine definiert wurde).

4.  Wenn Sie vom Cmdlet **Uninstall-CsDataBase** aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **Y** (oder die EINGABETASTE), oder drücken Sie **N** und dann die EINGABETASTE, wenn Sie die Ausführung des Cmdlets beenden möchten (im Falle von Fehlern).

