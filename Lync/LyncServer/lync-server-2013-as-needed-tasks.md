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
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529542"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a>Erforderliche Aufgaben in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Führen Sie bei Bedarf die folgenden Aufgaben aus. Sie werden häufig auch von Standardverfahren abgedeckt:

  - **Vollständige Sicherheitsüberwachung   ** Sie können diese Überprüfung regelmäßig als Reaktion auf ein Upgrade oder ein Neuentwurf des Messagingsystems oder als Reaktion auf eine versuchte (oder erfolgreiche) Sicherheitsverletzung durchführen. Das Verfahren kann Portscans auf Servern und Firewalls, Überwachung der Sicherheitsfixes und Tests hinsichtlich Zugriffsverletzungen durch Dritte beinhalten.

  - **Ersetzen von Zertifikaten zum Ablaufdatum**     Das Überprüfen lync Server Zertifikate ist eine der regelmäßigen wöchentlichen Aufgaben, und im Rahmen des Verfahrens sollte ein Administrator einen Datensatz mit Ablaufdatum aller Zertifikate aufweisen. Dieser Datensatz ermöglicht es einem Administrator, eine Benachrichtigung zu erstellen, wenn ein bestimmtes Zertifikat abgelaufen ist und bei Bedarf ersetzt wird.

  - **Aktualisieren von Leistungsbasislinien**     Aktualisieren der Leistungsbasislinien nach einem Upgrade oder einer Konfigurationsänderung. Ihre Organisation kann Basispläne verwenden, um Leistungsänderungen zu messen und Probleme zu erkennen, die sich auf die Systemleistung auswirken.

  - **Verwalten von Enterprise-Pool**     Die anfängliche Konfiguration von Enterprise-Pools, Standard Edition-Servern und anderen Servern in der Umgebung Ihres Unternehmens erfolgte während der Bereitstellung der einzelnen Server. Die Verwaltung nach der Bereitstellung von Servern und Pools für Standard Edition-Server und Enterprise-Pools umfasst die folgenden Aufgaben:
    
      - Verwalten von Front-End-Servern
    
      - Verwalten von Webkonferenzen
    
      - Verwalten von Konferenzen
    
      - Ändern von Dienstkontoanmeldeinformationen
    
      - Verwalten von Datenbanken
    
      - Starten und Beenden von Diensten und Deaktivieren von Server Rollen
    
      - Entfernen von Servern und Serverrollen, Entfernen von Pools und Außerbetriebnahme von Servern und Pools

  - **Verwalten der Verwendung**     Sie können lync Server 2013 so konfigurieren, dass die Features und Funktionen bereitgestellt werden, die für Ihre Organisation am besten geeignet sind. Dazu gehört Folgendes:
    
      - Verwalten der Unterstützung für lokale Webkonferenzbesprechungen
    
      - Verwalten der Verwendung von Verteilergruppen zum Senden von Chatnachrichten
    
      - Verwalten von Kontakten, Anwesenheit und Abfragen
    
      - Konfigurieren der Client Versions Filterung
    
      - Konfigurieren der intelligenten Sofortnachrichtenfilterung
    
      - Konfigurieren der Archivierung, Aufzeichnung von Kommunikationsdatensätzen und erfüllen der Compliance

  - **Verwalten von Edgeserver Konnektivität**     Die laufende Verwaltung der Server und Einstellungen, die für die Bereitstellung externer Konnektivität erforderlich sind, umfasst Folgendes:
    
      - Verwalten der Konnektivität zwischen internen Servern und Edge-Servern
    
      - Konfigurieren interner und externer Schnittstellen und Zertifikate für Edgeserver
    
      - Verwalten des Zugriffs durch Verbund Partner

  - **Verwalten des Adressbuchs**     Das Verwalten von Adressbuch Servern umfasst Folgendes:
    
      - Konfigurieren der Adressbuch Server-Telefon Normalisierung
    
      - Verwalten des Adressbuchservers über die Befehlszeile

  - **Verwalten von Benutzerkonten**     Die Verwaltung von Benutzerkonten umfasst Folgendes:
    
      - Aktivieren von Benutzerkonten für lync Server
    
      - Konfigurieren von lync Server Benutzern mithilfe des Assistenten
    
      - Konfigurieren einzelner lync Server Benutzerkontoeigenschaften
    
      - Suchen nach lync Server Benutzern
    
      - Verschieben von lync Server Benutzern
    
      - Löschen von lync Server Benutzern

  - **Analysieren von lync Server 2013 Protokolldateien**     Ein sehr hilfreiches Tool, das in der Regel für die Problembehandlung verwendet wird, ist das lync Server 2013 Protokollierungstool, das ausführlich unter [using lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx)beschrieben wird.

Da das Protokollierungstool Protokolldateien (auf Serverebene) generiert, können diese Protokolldateien mithilfe des Tools Snooper angezeigt und analysiert werden, wenn die Microsoft Office Server 12 Resource Kit-Tools auf dem Computer installiert sind. Andernfalls können Protokolle auch mithilfe eines Text-Editors analysiert werden, was weitaus weniger transparent und komplexer ist als die Verwendung des Snooper-Dienstprogramms.

So zeigen Sie Protokollnachrichten an und analysieren Sie

Wenn Sie im Protokollierungstool die Debugsitzung beendet haben, klicken Sie auf Protokolldateien analysieren, um die Protokolldateien mithilfe des Tools Snooper anzuzeigen. Sie können Protokoll Protokolle für die folgenden Komponenten analysieren:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server Konferenz Signalisierungs Datenverkehr (C3P), einschließlich MCU Infra C3P und Focus C3P

  - Lync Server-Webkonferenz Datenverkehr (PSOM)

  - Lync Server Unified Communications Clientplattform-Client (uccp)

  - Fehlerberichte aus der Archivierungsdatenbank

Informationen zum Organisieren der Leistung von nach Bedarf ausgeführten Aufgaben finden Sie unter Checkliste für As-Needed Vorgänge.

<div>


> [!IMPORTANT]  
> Ausführliche Verwaltungs-und Verwaltungsverfahren finden Sie im Microsoft lync Server 2013 Administration Guide.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Sicherungs-(und Wiederherstellungs-) Richtlinien oder Konfigurationseinstellungen

Lync Server 2013 können Sie das gesamte System sichern und wiederherstellen. IIf Sie möchten eine einzelne Richtlinie oder eine einzelne Auflistung von Konfigurationseinstellungen sichern (und dann möglicherweise eines Tages wiederherstellen), die entsprechende Richtlinie abrufen und das Objekt dann an das Export-Clixml-Cmdlet weiterleiten, wodurch die Richtlinieninformationen als XML-Datei gespeichert werden:

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

