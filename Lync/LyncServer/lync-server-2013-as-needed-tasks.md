---
title: 'Lync Server 2013: erforderliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Erforderliche Aufgaben in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_

Führen Sie die folgenden Aufgaben nach Bedarf aus. Sie werden häufig auch durch Standardverfahren abgedeckt:

  - **Vollständige Sicherheitsüberwachung   ** Sie können diese Überprüfung regelmäßig als Reaktion auf ein Upgrade oder eine Neugestaltung des Messagingsystems oder als Antwort auf eine versuchte (oder erfolgreiche) Sicherheitsverletzung durchführen. Das Verfahren kann Port-Scans auf Servern und Firewalls, Audits von Sicherheitsfixes und Penetrationstests von Drittanbietern beinhalten.

  - **Ersetzen von Zertifikaten über das ablaufen**   der Überprüfung von lync Server-Zertifikaten ist eine regelmäßige wöchentliche Aufgabe, und als Teil des Verfahrens sollte ein Administrator eine Aufzeichnung aller Ablaufdaten aller Zertifikate aufweisen. Dieser Eintrag ermöglicht es einem Administrator, eine Benachrichtigung zu erstellen, wenn ein bestimmtes Zertifikat demnächst abgelaufen und nach Bedarf ersetzt werden soll.

  - ****   Aktualisieren von Leistungsbasis Plänen aktualisieren Sie die Leistungsbasis Pläne nach einem Upgrade oder einer Konfigurationsänderung. Ihre Organisation kann Basispläne verwenden, um Leistungsänderungen zu messen und Probleme zu erkennen, die sich auf die Systemleistung auswirken.

  - **Die Verwaltung der Unternehmens Pool**   -Erstkonfiguration von Enterprise-Pools, Standard Edition-Servern und anderen Servern in der Umgebung Ihrer Organisation erfolgte während der Bereitstellung der einzelnen Server. Die Verwaltung nach der Bereitstellung von Servern und Pools für Standard Edition-Server und Enterprise-Pools umfasst die folgenden Aufgaben:
    
      - Verwalten von Front-End-Servern
    
      - Verwalten von Webkonferenzen
    
      - Verwalten von Konferenzen
    
      - Ändern der Anmeldeinformationen für das Dienstkonto
    
      - Verwalten von Datenbanken
    
      - Starten und Beenden von Diensten und Deaktivieren von Server Rollen
    
      - Entfernen von Servern und Serverrollen, Entfernen von Pools und Außerbetriebnahme von Servern und Pools

  - **Verwalten der Verwendung**   Sie können lync Server 2013 so konfigurieren, dass die Features und Funktionen bereitgestellt werden, die für Ihre Organisation am besten geeignet sind. Dazu gehört Folgendes:
    
      - Verwalten der Unterstützung für lokale Webkonferenzbesprechungen
    
      - Verwalten der Verwendung von Verteilergruppen zum Senden von Sofortnachrichten
    
      - Verwalten von Kontakten, Anwesenheitsinformationen und Abfragen
    
      - Konfigurieren der Client Versions Filterung
    
      - Konfigurieren intelligenter Chat Filterung
    
      - Konfigurieren von Archivierungs-, Anruf Detail Aufzeichnung und Besprechungs Konformität

  - **Verwalten der Edge-Server-Konnektivität**   die laufende Verwaltung der Server und Einstellungen, die für die Bereitstellung externer Konnektivität erforderlich sind, umfasst Folgendes:
    
      - Verwalten der Konnektivität zwischen internen Servern und Edgeserver
    
      - Konfigurieren interner und externer Schnittstellen und Zertifikate für Edgeserver
    
      - Verwalten des Zugriffs von Verbundpartnern

  - **Das Verwalten des Adressbuchs**   mit Adressbuch Servern umfasst Folgendes:
    
      - Konfigurieren der Adressbuch Server-Telefon Normalisierung
    
      - Verwalten des Adressbuchservers über die Befehlszeile

  - **Die Verwaltung von**Benutzerkonten für Benutzerkonten umfasst Folgendes:   
    
      - Aktivieren von Benutzerkonten für lync Server
    
      - Konfigurieren von lync Server-Benutzern mit dem Assistenten
    
      - Konfigurieren der Eigenschaften einzelner lync Server-Benutzerkonten
    
      - Suchen nach lync Server-Benutzern
    
      - Verschieben von lync Server-Benutzern
    
      - Löschen von lync Server-Benutzern

  - **Analysieren von lync Server 2013-Protokolldateien**   ein sehr hilfreiches Tool, das in der Regel für die Problembehandlung verwendet wird, ist das lync Server 2013-Protokollierungstool, das ausführlich unter [Verwenden des lync Server 2013-Protokollierungstools](http://technet.microsoft.com/en-us/library/gg558599.aspx)beschrieben wird.

Da das Protokollierungstool Protokolldateien (pro Server) generiert, können diese Protokolldateien mithilfe des Snooper-Tools angezeigt und analysiert werden, wenn die Microsoft Office Server 12 Resource Kit-Tools auf dem Computer installiert sind. Andernfalls können Protokolle auch mithilfe eines Text-Editors analysiert werden, der weitaus weniger transparent und komplexer als die Verwendung des Snooper-Dienstprogramms ist.

So zeigen Sie Protokollnachrichten an und analysieren Sie

Wenn Sie im Protokollierungstool die Debugsitzung beendet haben, klicken Sie auf Protokolldateien analysieren, um die Protokolldateien mit dem Snooper-Tool anzuzeigen. Sie können Protokoll Protokolle für die folgenden Komponenten analysieren:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server Conferencing Signalisierungs Datenverkehr (C3P), einschließlich MCU Infra C3P und Fokus C3P

  - Lync Server Web Conferencing Traffic (PSOM)

  - Lync Server Unified Communications Client Platform-Client (uccp)

  - Fehlerberichte aus der Archivierungsdatenbank

Informationen dazu, wie Sie die Leistung der erforderlichen Aufgaben organisieren können, finden Sie unter Checkliste für erforderliche Vorgänge.

<div>


> [!IMPORTANT]  
> Detaillierte Verwaltungs-und Verwaltungsverfahren finden Sie im Microsoft lync Server 2013-Administratorhandbuch.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Sicherungs-und Wiederherstellungsrichtlinien oder Konfigurationseinstellungen

Mit lync Server 2013 können Sie das gesamte System sichern und wiederherstellen. Wenn Sie eine einzelne Richtlinie oder eine einzelne Sammlung von Konfigurationseinstellungen sichern (und dann möglicherweise irgendwann wiederherstellen) möchten, rufen Sie die entsprechende Richtlinie ab, und leiten Sie dieses Objekt dann an das Cmdlet Export-CliXML weiter, wodurch die Richtlinieninformationen als XML-Datei gespeichert werden:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Sie können jetzt mit RedmondClientPolicy experimentieren und viele Einstellungen ändern. Wenn Sie stattdessen die alte Richtlinie wiederherstellen möchten, geben Sie Folgendes ein:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Beachten Sie, dass diese Vorgehensweise für die meisten Richtlinien und Einstellungen geeignet ist, aber nicht mit einigen der komplexeren Elemente (Elemente, die mehrere untergeordnete Objekte enthalten (wie Routing Konfigurationseinstellungen, die viele getrennte VoIP-Routen enthalten) funktionieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

