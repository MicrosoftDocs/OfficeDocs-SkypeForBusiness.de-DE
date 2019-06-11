---
title: 'Lync Server 2013: Installieren von SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Installieren von SQL Server Reporting Services in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Wenn Sie beabsichtigen, Microsoft lync Server 2013-Überwachungsberichte zu verwenden (Weitere Informationen finden Sie im nächsten Abschnitt dieser Dokumentation), müssen Sie zuerst SQL Server Reporting Services installieren. Reporting Services kann zur gleichen Zeit installiert werden, wenn Sie Microsoft SQL Server oder nach der Installation von SQL Server installieren. Wenn Sie SQL Server nicht installiert haben, befolgen Sie die Anweisungen weiter oben in dieser Dokumentation. Stellen Sie bei der Installation von SQL Server sicher, dass Sie auf der Seite Featureauswahl die Option Reporting Services auswählen. , In dem SQL Server Reporting Services installiert wird.

Wenn Sie bereits SQL Server installiert haben, aber SQL Server Reporting Services nicht installiert haben, können Sie dieses Feature hinzufügen, indem Sie die entsprechenden Anweisungen für SQL Server 2008 R2 oder SQL Server 2012 entsprechend befolgen.

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Reporting Services erfolgreich installiert wurden:

1.  Wenn Sie Microsoft SQL Server 2008 R2 ausführen, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2008 R2**, klicken Sie auf **Konfigurations Tools**, und klicken Sie dann auf **Reporting Services-Konfigurations-Manager**.
    
    Wenn Sie Microsoft SQL Server 2012 ausführen, klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012**, klicken Sie auf **Konfigurations Tools**, und klicken Sie dann auf **Reporting Services-Konfigurations-Manager**.

2.  Überprüfen Sie im Dialogfeld **Reporting Services-Konfigurationsverbindung** , ob der Name Ihres Servers im Feld **Servername** angezeigt wird und dass der Name der SQL Server-Instanz, die ihre Überwachungsdaten speichert, auf dem **Berichtsserver angezeigt wird. Feld Instanz** . Klicken Sie auf **verbinden**.

Im Reporting Service-Konfigurations-Manager sollte der Bereich Berichtsserverstatus anzeigen, dass SQL Server Reporting Services installiert wurde und dass die Reporting Services aktuell ausgeführt werden: der Status des Berichtsservers sollte als **gestartet** angezeigt werden und die Schaltfläche " **Start** " sollte abgeblendet und nicht verfügbar sein. Wenn der Berichterstattungsdienst nicht ausgeführt wird, klicken Sie auf **Start** , um den Dienst zu starten.

Wenn neben der Bezeichnung des Berichts Server-Datenbanknamens keine Datenbank aufgeführt ist, gehen Sie folgendermaßen vor:

1.  Klicken Sie im Reporting Services-Konfigurations-Manager auf **Datenbank**.

2.  Klicken Sie im Bereich Berichts Server-Datenbank auf **Datenbank ändern**.

3.  Wählen Sie im Konfigurations-Assistenten für Berichtsserver-Datenbank im Bereich "Aktion" die Option **neue Berichtsserver-Datenbank erstellen** aus, und klicken Sie dann auf **weiter**.

4.  Überprüfen Sie im Konfigurations-Assistenten für die Berichts Server-Datenbank im Bereich Daten Bank Server, ob die in den Feldern **Server Name**, **Authentifizierungstyp**und **Benutzername** aufgeführten Informationen richtig sind. Klicken Sie auf **Verbindung testen** , um zu überprüfen, ob eine Verbindung mit dem Datenbankserver hergestellt werden kann, und klicken Sie dann auf **weiter**.

5.  Übernehmen Sie im Konfigurations-Assistenten für die Berichtsserver-Datenbank im Datenbankbereich die Standardwerte für **Datenbankname**, **Sprache**und **Berichtsservermodus** , und klicken Sie dann auf **weiter**.

6.  Überprüfen Sie im Assistenten für die Berichts Server-Datenbankkonfiguration im Bereich Anmeldeinformationen, ob die richtigen Informationen in der Dropdownliste **Authentifizierungstyp** und den Feldern **Benutzername** und **Kennwort** aufgeführt sind, und klicken Sie dann auf **weiter**.

7.  Klicken Sie im Konfigurations-Assistenten für Berichts Server-Datenbank im Zusammenfassungsbereich auf **weiter**.

8.  Klicken Sie im Konfigurations-Assistenten für Berichts Server-Datenbank im Bereich Status und fertig stellen auf **Fertig stellen**.

Wenn Sie überprüfen möchten, ob die Reporting Services-URLs konfiguriert wurden, klicken Sie auf **Webdienst-URL**. Es sollte eine oder mehrere URLs angezeigt werden, die unter der Überschrift **Berichts Server-Webdienst-URLs**aufgeführt sind. Klicken Sie auf jede dieser URLs, um zu überprüfen, ob Sie die Startseite für die lokale Installation von SQL Server Reporting Services erreichen können.

</div>

<span> </span>

</div>

</div>

</div>

