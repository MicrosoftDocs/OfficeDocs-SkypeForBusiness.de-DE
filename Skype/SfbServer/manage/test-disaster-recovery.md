---
title: Notfallwiederherstellungstests in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Durchführen einer Systemwiederherstellung für einen Skype for Business Server-Poolserver zum Testen des dokumentierten Notfallwiederherstellungsprozesses
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832815"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Notfallwiederherstellungstests in Skype for Business Server

Führen Sie eine Systemwiederherstellung für einen Skype for Business Server-Poolserver aus, um ihren dokumentierten Notfallwiederherstellungsprozess zu testen. Dieser Test simuliert einen vollständigen Hardwarefehler für einen Server und gewährleistet, dass die Ressourcen, Pläne und Daten für die Wiederherstellung verfügbar sind. Versuchen Sie, den Fokus des Tests jeden Monat zu drehen, damit Ihre Organisation jedes Mal den Ausfall eines anderen Servers oder anderer Geräte testet. 

Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfallwiederherstellungstests durchführen, unterschiedlich ist. Es ist sehr wichtig, dass Notfallwiederherstellungstests nicht ignoriert oder ignoriert werden. 

Exportieren Sie Ihre Skype for Business Server-Topologie, -Richtlinien und -Konfigurationseinstellungen in eine Datei. Unter anderem kann diese Datei verwendet werden, um diese Informationen nach einem Upgrade, einem Hardwarefehler oder einem anderen Problem, das zu Datenverlust geführt hat, im zentralen Verwaltungsspeicher wiederherzustellen.

Importieren Sie Ihre Skype for Business Server-Topologie, -Richtlinien und -Konfigurationseinstellungen entweder in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen gezeigt: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

So sichern Sie Produktionsdaten:

- Sichern Sie die RTC- und LCSLog-Datenbanken mithilfe des standardmäßigen SQL Server, um die Datenbank auf einem Datei- oder Bandabbildgerät zu sichern.
- Verwenden Sie die Sicherungsanwendung eines Drittanbieters, um die Daten in einer Datei oder auf band zu sichern.
- Verwenden Sie Export-CsUserData Cmdlet, um einen XML-Export der gesamten RTC-Datenbank zu erstellen.
- Verwenden Sie die Dateisystem- oder Drittanbietersicherung, um Besprechungsinhalte und Kompatibilitätsprotokolle zu sichern.
- Verwenden Sie Export-CsConfiguration Befehlszeilentool, um Skype for Business Server-Einstellungen zu sichern.

Der erste Schritt des Failoververfahrens umfasst das erzwungene Verschieben von Benutzern aus dem Produktionspool in den Notfallwiederherstellungspool. Dies ist eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzerverlagerung zu akzeptieren.

Der Benutzerprozess zum Verschieben von Skype for Business Server ist eine Änderung an einem Attribut für das Benutzerkontoobjekt sowie eine Datensatzaktualisierung für die RTC-SQL Datenbank. Diese Daten können vom ursprünglichen Sicherungsabbildgerät aus der Produktionsumgebung SQL Server mithilfe des standardmäßigen SQL Server Wiederherstellungsprozesses oder mithilfe eines Sicherungs-/Wiederherstellungsprogramms eines Drittanbieters wiederhergestellt werden.

Nachdem diese Daten wiederhergestellt wurden, können Benutzer effektiv eine Verbindung mit dem Notfallwiederherstellungspool herstellen und wie gewohnt arbeiten. Damit Benutzer eine Verbindung mit dem Notfallwiederherstellungspool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.

Auf den Skype for Business-Produktionspool wird von Clients verwiesen, die die autokonfiguration und DNS-SRV-Einträge von:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Zur Erleichterung des Failovers muss dieser #A0 aktualisiert werden, um auf den FQDN des DROCSPools zu verweisen:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
