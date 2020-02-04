---
title: Entfernen der SQL Server-Datenbank für einen Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Entfernen der SQL Server-Datenbank für einen Monitoring Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nachdem Sie einen Microsoft lync Server 2010-Überwachungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server Daten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1.  Öffnen Sie auf dem lync Server 2013-Front-End-Server den Topologie-Generator.

2.  Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Überwachungs Server zugeordnet ist, und klicken Sie dann auf **Löschen**.

3.  Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien aus dem SQL Server

1.  Um die Datenbanken auf dem SQL Server-basierten Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-Server sein, auf dem Sie die Datenbankdateien entfernen.

2.  Öffnen Sie die lync Server-Verwaltungsshell.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Hierbei \<handelt\> es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, \<FQDN\> ) des Datenbankservers, und Instanz ist die optionale benannte Datenbankinstanz.

4.  Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **Y** (oder drücken Sie die EINGABETASTE), um fortzufahren, oder drücken Sie **N** , und geben Sie dann ein, wenn Sie das Cmdlet beenden möchten (d. h., falls Fehler auftreten).

</div>

</div>

<span> </span>

</div>

</div>

</div>

