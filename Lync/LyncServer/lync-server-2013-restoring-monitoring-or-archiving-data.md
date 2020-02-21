---
title: 'Lync Server 2013: Wiederherstellen von Überwachungs-oder Archivierungsdaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Das Wiederherstellen von Überwachungs-und Archivierungsdaten ist nicht erforderlich, um nach einem Ausfall lync Server aufzunehmen und auszuführen. Wenn Überwachungs-und Archivierungsdaten jedoch für Ihre Organisation wichtig sind, sollten Sie die Daten wiederherstellen, nachdem Sie die Datenbanken neu erstellt haben.

Im folgenden Verfahren wird die Verwendung von SQL Server Management Studio zum Wiederherstellen von Archivierungs-oder Überwachungsdaten beschrieben.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>So stellen Sie Überwachungs-oder Archivierungsdaten aus einer Sicherungsdatei wieder her

1.  Melden Sie sich bei dem Server an, den Sie als Mitglied der Gruppe Administratoren auf dem lokalen Computer oder einer Gruppe mit gleichwertigen Benutzerrechten wiederherstellen.

2.  Öffnen Sie SQL Server Management Studio: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012** oder **Microsoft SQL Server 2008 R2**, und klicken Sie dann auf **SQL Server Management Studio**.

3.  Stellen Sie unter **Verbindung mit Server herstellen**eine Verbindung mit der SQL Server Instanz her, indem Sie mindestens den Namen des Servers und die Authentifizierungsinformationen angeben.

4.  Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Datenbank wiederherstellen**.

5.  Klicken Sie unter **Seite auswählen**auf **Allgemein**, und wählen Sie dann in **Datenbank** den Datenbanknamen wie folgt aus:
    
      - Wählen Sie für ein Archivierungsdatenbank die Option **LcsLog**aus.
    
      - Wählen Sie für eine KDS-Datenbank (Call Detail Recording) die Option **LcsCDR**aus.
    
      - Wählen Sie für eine QoE-Datenbank (Quality of Experience) die Option **QoEMetrics**aus.

6.  Klicken Sie auf **von Gerät**.

7.  Klicken Sie unter **Wählen Sie die wiederherzustellenden Sicherungssätze aus**auf die Sicherungsdatei, und klicken Sie dann auf **Wiederherstellen**.

8.  Klicken Sie unter **Seite auswählen**auf **Optionen**, stellen Sie sicher, dass sich der Pfad und der Protokollpfad der Datendatei im richtigen Ordner befinden, und klicken Sie dann auf **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>So stellen Sie sicher, dass Zugriffssteuerungslisten (Access Control Lists, ACLs) korrekt sind

1.  Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank Archivierung oder Überwachung, erweitern Sie **Sicherheit**, und erweitern Sie dann **Benutzer**.

2.  Stellen Sie sicher, dass die Domänengruppe RTCComponentUniversalServices als Benutzer vorhanden ist.

3.  Wenn RTCComponentUniversalServices unter **Benutzer**nicht vorhanden ist, gehen Sie wie folgt vor:
    
    1.  Klicken Sie mit der rechten Maustaste auf **Benutzer**, und klicken Sie anschließend auf **Neuer Benutzer**.
    
    2.  Geben Sie unter **Anmeldename**den fehlenden Gruppennamen RTCComponentUniversalServices.
    
    3.  Wählen Sie unter **Mitgliedschaft in Datenbankrollen**die Berechtigung **serverRole** aus, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Sie müssen den Archivierungs-oder Überwachungsdienst nicht neu starten.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

