---
title: Disaster Recovery-Tests in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Führen Sie eine Wiederherstellung für eine Skype für Business Server-Pool zum Testen Ihrer dokumentierte Disaster Recovery-Prozess
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884964"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Disaster Recovery-Tests in Skype für Business Server

Führen Sie eine Wiederherstellung für eine Skype für Business Server-Pool zum Testen Ihrer dokumentierte notfallwiederherstellungsprozess. Bei diesem Test simuliert einen vollständige Hardwarefehler für einen Server, und wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind. Versuchen Sie, den Fokus des Tests jeden Monat drehen, sodass Ihrer Organisation den Ausfall einen anderen Server oder eine sonstige Codekomponente Geräte bei jedem überprüft. 

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden. 

Exportieren Sie Ihre Skype für Business Server-Topologie, Richtlinien und-Konfigurationseinstellungen in eine Datei. Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.

Importieren Sie Ihre Skype für Business Server-Topologie, Richtlinien und Konfigurationseinstellungen auf dem zentralen Verwaltungsspeicher oder auf dem lokalen Computer wie in den folgenden Befehlen gezeigt: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

So sichern Sie Produktionsdaten

- Sichern Sie die Datenbanken RTC und LCSLog mithilfe der standardmäßigen SQL Server backup-Vorgang, um die Datenbank auf eine Datei oder auf Band Sicherungsmedium dump.
- Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.
- Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.
- Verwenden Sie die Datei System oder Drittanbieter-Sicherung um zu sichernden Daten meeting Inhalte und Kompatibilitätsdaten von Protokollen.
- Verwenden Sie das Export-CsConfiguration-Befehlszeilentool zum Sichern von Skype für Business Server-Einstellungen.

Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool. Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.

Die Skype für Business Server Verschiebens Benutzer ist praktisch eine Änderung für ein Attribut für das Konto Benutzerobjekt zusätzlich zu einem Datensatz Update auf der RTC-SQL-Datenbank. Diese Daten können wiederhergestellt werden aus der ursprünglichen backup Dump-Gerät aus der Produktion SQL Server mithilfe der standardmäßigen SQL Server Wiederherstellungsvorgang oder mithilfe eines Drittanbieters-Sicherung/Wiederherstellung Dienstprogramm.

Nach der Wiederherstellung dieser Daten können wie gewohnt Benutzer effektiv Verbinden mit den Disaster Recovery-Pool, und betreiben. Um Benutzern die Verbindung zu dem Pool Disaster Recovery zu aktivieren, wird eine DNS-Datensatz Änderung erforderlich sein.

Clients verwenden die automatische Konfiguration und der DNS-SRV-Einträge werden die Produktion Skype für Business Pool verweist:

- SRV: _sip. \<Domain> /CNAME: SIP. \<Domain>
- CNAME: SIP. \<Domain> /cvc-pool-1. \<Domain>

Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:

- CNAME: SIP.<domain> / DROCSPool. \<Domain>
- SIP. \<Domain>
- AV.\<Domain>
- Webconf. \<Domain>
