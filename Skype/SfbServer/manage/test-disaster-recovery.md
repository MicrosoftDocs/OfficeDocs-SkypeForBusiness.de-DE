---
title: Disaster Recovery-Tests in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Durchführen einer Systemwiederherstellung für einen Skype for Business Server-Pool Server zum Testen des dokumentierten Disaster Recovery-Prozesses
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817301"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Disaster Recovery-Tests in Skype for Business Server

Führen Sie eine Systemwiederherstellung für einen Skype for Business Server-Pool Server aus, um Ihren dokumentierten Disaster Recovery-Prozess zu testen. Mit diesem Test wird ein vollständiger Hardwarefehler für einen Server simuliert, und es wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind. Versuchen Sie, den Fokus des Tests monatlich zu drehen, damit Ihre Organisation den Fehler eines anderen Servers oder eines anderen Geräts jedes Mal testet. 

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder vernachlässigt werden. 

Exportieren Sie Ihre Skype for Business Server-Topologie,-Richtlinien und-Konfigurationseinstellungen in eine Datei. Unter anderem kann diese Datei nach einem Upgrade, einem Hardwareausfall oder einem anderen Problem, das zu Datenverlust geführt hat, zum Wiederherstellen dieser Informationen im zentralen Verwaltungsspeicher verwendet werden.

Importieren Sie Ihre Skype for Business Server-Topologie,-Richtlinien und-Konfigurationseinstellungen entweder in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen gezeigt: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

So sichern Sie Produktionsdaten:

- Sichern Sie die RTC-und LCSLog-Datenbanken mithilfe des standardmäßigen SQL Server-Sicherungsprozesses, um die Datenbank auf ein Datei-oder Bandspeicher Abbildgerät zu übernehmen.
- Verwenden Sie eine Sicherungsanwendung von einem Drittanbieter, um die Daten in einer Datei oder auf einem Band zu sichern.
- Verwenden Sie das Cmdlet „Export-CsUserData“, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.
- Verwenden Sie das Dateisystem-Backup oder Drittanbieter-Backup, um Besprechungsinhalte und Kompatibilitäts Protokolle zu sichern.
- Verwenden Sie das Befehlszeilentool "Exportieren-CsConfiguration", um die Einstellungen für Skype for Business Server zu sichern.

Der erste Schritt in der Failoverprozedur besteht in einer erzwungenen Verschiebung von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool. Es handelt sich dabei um eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerumsetzung zu akzeptieren.

Der Skype for Business Server-Prozess "Move User" ist eine Änderung an einem Attribut für das Benutzerkontoobjekt sowie eine Datensatzaktualisierung in der RTC SQL-Datenbank. Diese Daten können vom ursprünglichen Backup-Dump-Gerät aus dem Produktions-SQL-Server mithilfe des standardmäßigen SQL Server-Wiederherstellungsprozesses oder mithilfe eines Sicherungs-/Wiederherstellungstools eines Drittanbieters wiederhergestellt werden.

Nach der Wiederherstellung dieser Daten können Benutzer eine Verbindung mit dem Disaster Recovery-Pool herstellen und wie gewohnt funktionieren. Damit Benutzer eine Verbindung mit dem Disaster Recovery-Pool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.

Der Produktions-Skype for Business-Pool wird von Clients, die die automatischen Konfigurations-und DNS-SRV-Einträge verwenden, referenziert:

- SRV: _sip. _tls. \<Domain>/CNAME: SIP. \<Domänen>
- CNAME: SIP. \<Domänen>/CVC-Pool-1. \<Domänen>

Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den DROCSPool-FQDN verweist:

- CNAME: SIP.<domain> /DROCSPool. \<Domänen>
- SIP. \<Domänen>
- AV.\<Domain>
- webconf. \<Domänen>
