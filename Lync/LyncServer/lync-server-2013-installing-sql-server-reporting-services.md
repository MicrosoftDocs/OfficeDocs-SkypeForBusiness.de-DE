---
title: 'Lync Server 2013: Installieren von SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3527e3abca5bb9d6fa953db59be902c0ee340721
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Installieren von SQL Server Reporting Services in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-20_

Wenn Sie Microsoft lync Server 2013-Überwachungsberichte verwenden möchten (Weitere Informationen finden Sie im nächsten Abschnitt dieser Dokumentation), müssen Sie zuerst SQL Server Reporting Services installieren; Reporting Services kann gleichzeitig installiert werden, wenn Sie Microsoft SQL Server oder nach der Installation von SQL Server zu einem beliebigen Zeitpunkt installieren. Wenn Sie SQL Server nicht installiert haben, befolgen Sie die weiter oben in dieser Dokumentation beschriebenen Anweisungen. Achten Sie beim Installieren von SQL Server darauf, dass Sie auf der Seite Featureauswahl die Option Reporting Services auswählen. Damit wird SQL Server Reporting Services installiert.

Wenn Sie SQL Server ohne SQL Server Reporting Services installiert haben, können Sie dieses Feature gemäß der entsprechenden Vorgehensweise für SQL Server 2008 R2 bzw. SQL Server 2012 installieren.

Wenn Sie überprüfen möchten, ob die Reporting Services ordnungsgemäß installiert sind, gehen Sie wie folgt vor:

1.  Wenn bei Ihnen Microsoft SQL Server 2008 R2 ausgeführt wird, klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2008 R2**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.
    
    Bei Microsoft SQL Server 2012 klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2012**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.

2.  Überprüfen Sie im Dialogfeld **Konfigurationsverbindung für Reporting Services**, ob im Feld **Servername** der Name Ihres Servers und im Feld **Berichtsserverinstanz** der Name der SQL Server-Instanz, die Ihre Überwachungsdaten speichert, angezeigt werden. Klicken Sie auf **Verbinden**.

Im Konfigurations-Manager für den Berichtsdienst sollte im Bereich Berichtsserverstatus angezeigt werden, dass SQL Server Reporting Services installiert wurde und dass die Reporting Services derzeit ausgeführt werden: der Status des Berichtsservers sollte als **gestartet** angezeigt werden, und die Schaltfläche **Start** sollte abgeblendet sein und nicht verfügbar sein. Wenn der Berichterstellungsdienst nicht ausgeführt wird, klicken Sie auf **Start**, um den Dienst zu starten.

Wenn neben "Berichtsserver-Datenbankname" keine Datenbank aufgeführt ist, führen Sie Folgendes durch:

1.  Klicken Sie im Konfigurations-Manager für Reporting Services auf **Datenbank**.

2.  Klicken Sie im Bereich "Berichtsserver-Datenbank" auf **Datenbank ändern**.

3.  Aktivieren Sie im Assistenten zum Konfigurieren der Berichtsserver-Datenbank im Bereich "Aktion" den Punkt **Neue Berichtsserver-Datenbank erstellen**, und klicken Sie dann auf **Weiter**.

4.  Überprüfen Sie im Bereich "Datenbankserver", ob die Angaben in den Feldern **Servername**, **Authentifizierungstyp** und **Benutzername** korrekt sind. Klicken Sie auf **Verbindung testen**, um zu überprüfen, ob eine Verbindung zu dem Datenbankserver hergestellt werden kann, und klicken Sie dann auf **Weiter**.

5.  Akzeptieren Sie im Bereich "Datenbank" die Standardwerte für **Datenbankname**, **Sprache** und **Berichtsservermodus**, und klicken Sie dann auf **Weiter**.

6.  Überprüfen Sie, ob im Bereich "Anmeldeinformationen" in der Dropdownliste **Authentifizierungstyp** und in den Feldern **Benutzername** und **Kennwort** die korrekten Informationen aufgeführt sind, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie im Bereich "Zusammenfassung" auf **Weiter**.

8.  Klicken Sie im Bereich "Fortsetzen und Fertigstellen" auf **Fertigstellen**.

Klicken Sie auf **Webdienst-URL**, um zu überprüfen, ob die Berichtsdienst-URLs konfiguriert sind. Unter **URLs für Berichtsserver-Webdienst** sollte mindestens eine URL aufgeführt sein. Klicken Sie auf die einzelnen URLs, um zu überprüfen, ob Sie damit die Startseite für die lokale Installation von SQL Server Reporting Services erreichen.

</div>

<span> </span>

</div>

</div>

</div>

