---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853b52c6f6a06d05f106114ab6b59ebc52129fc3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Nachdem Sie einen Microsoft lync Server 2010-Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1.  Öffnen Sie im lync Server 2013-Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.

2.  Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.

3.  Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Sie Benutzer-und Anwendungsdatenbanken aus dem SQL Server

1.  Um die Datenbanken auf dem SQL Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server Sysadmins für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen.

2.  Öffnen der lync Server-Verwaltungsshell

3.  Wenn Sie die Datenbank für den Pool Benutzerspeicher entfernen möchten, geben Sie Folgendes ein:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Hierbei \<handelt\> es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, \<FQDN\> ) des Datenbankservers, wobei es sich bei der Instanz um die benannte Datenbankinstanz handelt (also, wenn eine definiert wurde).

4.  Wenn Sie die Datenbank für den Pool-Anwendungsspeicher entfernen möchten, geben Sie Folgendes ein:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei \<ist\> FQDN der FQDN des Datenbankservers, und \<Instanz\> ist die benannte Datenbankinstanz (also, wenn eine definiert wurde).

5.  Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **Y** (oder drücken Sie die EINGABETASTE), um fortzufahren, oder drücken Sie **N** , und geben Sie dann ein, wenn Sie das Cmdlet beenden möchten (d. h., falls Fehler auftreten).

</div>

</div>

<span> </span>

</div>

</div>

</div>

