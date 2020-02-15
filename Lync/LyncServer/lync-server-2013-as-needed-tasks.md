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
ms.openlocfilehash: 67a0355d32e5e704d6609335c82f8cfe1fe7aa86
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Erforderliche Aufgaben in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Führen Sie bei Bedarf die folgenden Aufgaben aus. Sie werden häufig auch von Standardverfahren abgedeckt:

  - **Vollständige Sicherheitsüberwachung   ** Sie können diese Überprüfung regelmäßig als Reaktion auf ein Upgrade oder ein Neuentwurf des Messagingsystems oder als Reaktion auf eine versuchte (oder erfolgreiche) Sicherheitsverletzung durchführen. Das Verfahren kann Portscans auf Servern und Firewalls, Überwachung der Sicherheitsfixes und Tests hinsichtlich Zugriffsverletzungen durch Dritte beinhalten.

  - **Ersetzen von Zertifikaten über das ablaufen**   der Überprüfung lync Server Zertifikate ist eine der regelmäßigen wöchentlichen Aufgaben, und als Teil des Verfahrens sollte ein Administrator einen Datensatz mit Ablaufdatum aller Zertifikate aufweisen. Dieser Datensatz ermöglicht es einem Administrator, eine Benachrichtigung zu erstellen, wenn ein bestimmtes Zertifikat abgelaufen ist und bei Bedarf ersetzt wird.

  - **Beim Aktualisieren**   der Leistungsbasislinien werden Leistungsbasis Pläne nach einem Upgrade oder einer Konfigurationsänderung aktualisiert. Ihre Organisation kann Basispläne verwenden, um Leistungsänderungen zu messen und Probleme zu erkennen, die sich auf die Systemleistung auswirken.

  - **Managing Enterprise-Pool**   die Erstkonfiguration von Enterprise-Pools, Standard Edition-Servern und anderen Servern in der Umgebung Ihrer Organisation wurde während der Bereitstellung der einzelnen Server durchgeführt. Die Verwaltung nach der Bereitstellung von Servern und Pools für Standard Edition-Server und Enterprise-Pools umfasst die folgenden Aufgaben:
    
      - Verwalten von Front-End-Servern
    
      - Verwalten von Webkonferenzen
    
      - Verwalten von Konferenzen
    
      - Ändern von Dienstkontoanmeldeinformationen
    
      - Verwalten von Datenbanken
    
      - Starten und Beenden von Diensten und Deaktivieren von Server Rollen
    
      - Entfernen von Servern und Serverrollen, Entfernen von Pools und Außerbetriebnahme von Servern und Pools

  - **Verwalten der Verwendung**   Sie können lync Server 2013 konfigurieren, um die Features und Funktionen bereitzustellen, die für Ihre Organisation am besten geeignet sind. Dazu gehört Folgendes:
    
      - Verwalten der Unterstützung für lokale Webkonferenzbesprechungen
    
      - Verwalten der Verwendung von Verteilergruppen zum Senden von Chatnachrichten
    
      - Verwalten von Kontakten, Anwesenheit und Abfragen
    
      - Konfigurieren der Client Versions Filterung
    
      - Konfigurieren der intelligenten Sofortnachrichtenfilterung
    
      - Konfigurieren der Archivierung, Aufzeichnung von Kommunikationsdatensätzen und erfüllen der Compliance

  - **Managing Edgeserver Connectivity**   die laufende Verwaltung der Server und Einstellungen, die für die Bereitstellung externer Konnektivität erforderlich sind, umfasst Folgendes:
    
      - Verwalten der Konnektivität zwischen internen Servern und Edge-Servern
    
      - Konfigurieren interner und externer Schnittstellen und Zertifikate für Edgeserver
    
      - Verwalten des Zugriffs durch Verbund Partner

  - **Das Verwalten**   von Adressbuch Servern für das Adressbuch umfasst Folgendes:
    
      - Konfigurieren der Adressbuch Server-Telefon Normalisierung
    
      - Verwalten des Adressbuchservers über die Befehlszeile

  - **Das Verwalten der Benutzerkonten**   Verwaltung von Benutzerkonten umfasst Folgendes:
    
      - Aktivieren von Benutzerkonten für lync Server
    
      - Konfigurieren von lync Server Benutzern mithilfe des Assistenten
    
      - Konfigurieren einzelner lync Server Benutzerkontoeigenschaften
    
      - Suchen nach lync Server Benutzern
    
      - Verschieben von lync Server Benutzern
    
      - Löschen von lync Server Benutzern

  - **Analysieren von lync Server 2013 Protokolldateien**   ein sehr hilfreiches Tool, das in der Regel für die Problembehandlung verwendet wird, ist das lync Server 2013 Protokollierungstool, das ausführlich unter [using lync Server 2013 Logging Tool](http://technet.microsoft.com/library/gg558599.aspx)beschrieben wird.

Da das Protokollierungstool Protokolldateien (auf Serverebene) generiert, können diese Protokolldateien mithilfe des Tools Snooper angezeigt und analysiert werden, wenn die Microsoft Office Server 12 Resource Kit-Tools auf dem Computer installiert sind. Andernfalls können Protokolle auch mithilfe eines Text-Editors analysiert werden, was weitaus weniger transparent und komplexer ist als die Verwendung des Snooper-Dienstprogramms.

So zeigen Sie Protokollnachrichten an und analysieren Sie

Wenn Sie im Protokollierungstool die Debugsitzung beendet haben, klicken Sie auf Protokolldateien analysieren, um die Protokolldateien mithilfe des Tools Snooper anzuzeigen. Sie können Protokoll Protokolle für die folgenden Komponenten analysieren:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server Konferenz Signalisierungs Datenverkehr (C3P), einschließlich MCU Infra C3P und Focus C3P

  - Lync Server-Webkonferenz Datenverkehr (PSOM)

  - Lync Server Unified Communications Clientplattform-Client (uccp)

  - Fehlerberichte aus der Archivierungsdatenbank

Informationen zur Organisation der Leistung von nach Bedarf ausgeführten Aufgaben finden Sie unter Checkliste der erforderlichen Vorgänge.

<div>


> [!IMPORTANT]  
> Ausführliche Verwaltungs-und Verwaltungsverfahren finden Sie im Microsoft lync Server 2013 Administration Guide.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Sicherungs-(und Wiederherstellungs-) Richtlinien oder Konfigurationseinstellungen

Lync Server 2013 können Sie das gesamte System sichern und wiederherstellen. IIf Sie möchten eine einzelne Richtlinie oder eine einzelne Auflistung von Konfigurationseinstellungen sichern (und dann möglicherweise eines Tages wiederherstellen), die entsprechende Richtlinie abrufen und das Objekt dann an das Export-CliXML-Cmdlet weiterleiten, wodurch die Richtlinieninformationen als XML-Datei gespeichert werden:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Sie können jetzt mit RedmondClientPolicy experimentieren und viele Einstellungen ändern. Wenn Sie stattdessen die alte Richtlinie wiederherstellen möchten, geben Sie Folgendes ein:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Beachten Sie, dass dieser Ansatz für die meisten Richtlinien und Einstellungen funktioniert, aber nicht mit einigen der komplexeren Elemente – Elemente, die mehrere unter Objekte enthalten (wie Routing Konfigurationseinstellungen, die viele getrennte VoIP-Routen enthalten).

</div>

</div>

<span> </span>

</div>

</div>

</div>

