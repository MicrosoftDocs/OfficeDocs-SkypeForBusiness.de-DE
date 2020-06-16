---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d46868b63236327825f2fe4134330fd055ead2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Nachdem Sie ein Microsoft lync Server 2010 entfernt Front-End-Pool oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators

1.  Öffnen Sie im lync Server 2013 Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.

2.  Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.

3.  Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Sie Benutzer- und Anwendungsdatenbanken aus dem SQL Server-basierten Server

1.  Zum Entfernen der Datenbanken vom SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe sysadmins für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden.

2.  Lync Server-Verwaltungsshell öffnen

3.  Geben Sie Folgendes ein, um die Datenbank für den Poolbenutzerspeicher zu entfernen:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei \<FQDN\> ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und \<instance\> die benannte Datenbankinstanz (sofern eine definiert wurde).

4.  Geben Sie Folgendes ein, um die Datenbank für den Poolanwendungsspeicher zu entfernen:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Dabei \<FQDN\> ist der FQDN des Datenbankservers und \<instance\> die benannte Datenbankinstanz (sofern eine definiert wurde).

5.  Wenn Sie vom **Uninstall-CsDataBase**-Cmdlet aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **J** (oder die EINGABETASTE), oder drücken Sie **N** und dann die EINGABETASTE, wenn Sie die Ausführung des Cmdlets beenden möchten (im Falle von Fehlern).

</div>

</div>

<span> </span>

</div>

</div>

</div>

