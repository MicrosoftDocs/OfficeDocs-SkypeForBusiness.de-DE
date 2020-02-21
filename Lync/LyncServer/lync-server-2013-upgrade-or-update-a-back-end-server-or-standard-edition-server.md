---
title: Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Aktualisieren oder Aktualisieren eines Back-End-Servers oder Standard Edition-Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In diesem Thema wird erläutert, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.

Wenn ein Back-End-Server während des Upgrades mindestens 30 Minuten lang ausfällt, können Benutzer in den Ausfall Sicherheitsmodus wechseln. Wenn das Upgrade abgeschlossen ist und die Back-End-Server erneut mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer an die vollständige Funktionalität zurückgegeben. Wenn das Upgrade weniger als 30 Minuten dauern kann, sind die Benutzer nicht betroffen.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>So aktualisieren Sie einen Back-End-Server oder Standard Edition-Server

1.  Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle "CsAdministrator" an.

2.  Laden Sie das Update herunter, und extrahieren Sie es auf die lokale Festplatte.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Beenden Sie lync Server Dienste. Geben Sie in die Befehlszeile Folgendes ein:
    
        Stop-CsWindowsService

5.  Beenden Sie den WWW-Dienst (World Wide Web). Geben Sie in die Befehlszeile Folgendes ein:
    
        net stop w3svc

6.  Schließen Sie alle lync Server-Verwaltungsshell Fenster.

7.  Installieren Sie das Update.

8.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

9.  Beenden Sie lync Server Dienste erneut, um den globalen Assemblycache (GAC) – d-Assemblys zu erfassen. Geben Sie an der Eingabeaufforderung Folgendes ein:
    
        Stop-CsWindowsService

10. Starten Sie den WWW-Dienst neu. Geben Sie an der Befehlszeile Folgendes ein:
    
        net start w3svc

11. Übernehmen Sie die mit "LyncServerUpdateInstaller.exe" vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:
    
      - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und keine zusammengefassten Datenbanken auf diesem Server vorhanden sind, wie etwa Archivierungs-oder Überwachungsdatenbanken, geben Sie Folgendes an einer Befehlszeile ein:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server zusammengefasste Datenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Wenn es sich um eine Standard Edition-Server handelt, geben Sie Folgendes an einer Befehlszeile ein:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

