---
title: Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015
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
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten und Implementieren der Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen.'
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734293"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015

Der Zweck dieses Artikels besteht darin, die erforderlichen Anleitungen für die Vorbereitung und Implementierung der Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen bereitzustellen. Dieser Vorgang erfordert eine umfassende Planung und Vorbereitung. Lesen Sie sorgfältig alle Informationen in diesem Artikel, wenn Sie den Plan zum Deaktivieren von TLS 1,0 und 1,1 für Ihre Organisation erstellen. Beachten Sie, dass es viele externe Abhängigkeiten und Verbindungsbedingungen gibt, die durch Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden könnten, sodass umfangreiche Planung und Tests gewährleistet sind.

## <a name="in-this-article"></a>Inhalt dieses Artikels

- [Hintergrund und Bereich](#background)
- [Voraussetzungen und Prozess](#prerequisites-and-process)
- [Erweiterte Bereitstellungsszenarien](#advanced-deployment-scenarios)

## <a name="background"></a>Hintergrund

Die primären Treiber für die Bereitstellung von TLS 1,0 und 1,1 deaktivieren Unterstützung für Skype for Business Server lokal sind die Standards für die Informationsverarbeitung (Payment Card Industry, PCI) Security Standards Council und Federal Information Processing. Weitere Informationen zu PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft kann keine Anleitungen dazu geben, ob Ihre Organisation diese oder andere Anforderungen einhalten muss. Sie müssen feststellen, ob Sie TLS 1,0 und/oder 1,1 in ihren Umgebungen deaktivieren müssen.

Microsoft hat ein Whitepaper zu TLS erstellt, das [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)verfügbar ist, und wir empfehlen auch das in diesem [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbare Hintergrund Lesematerial.

## <a name="supportability-scope"></a>Unterstützungsbereich

Der *Bereich* bezieht sich auf Unterstützungsgrenzen. *Vollständig getestet und unterstützt* bedeutet, dass wir die Deaktivierung von TLS 1,0 und 1,1 für die aufgeführten Produktversionen vollständig unterstützen und getestet haben. *Derzeit untersucht wird* , bedeutet nur, dass; Wir untersuchen aktiv, diese Produkte in den Geltungsbereich der TLS-Deaktivierungs Unterstützung zu bringen. *Außerhalb des Bereichs* bedeutet, dass diese Produktversionen die Deaktivierung von TLS 1,0 oder 1,1 nicht unterstützen, und es kann nicht mit bekannten Ausnahmen funktionieren.

### <a name="fully-tested-and-supported-servers"></a>Vollständig getestete und unterstützte Server

- Skype for Business Server 2019 ku1 17.0.2046.123 (Juni 2019) oder höher
- Skype for Business Server 2015 ku9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder einem abgelösten Update), 2012 R2 oder 2016.
- In-Place-Upgrade Skype for Business Server 2015 mit ku9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder Ersetzen von Updates) oder 2012 R2.
- Exchange-Konnektivität und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 HF2 oder höher (bestätigen Sie mit Ihrem Anbieter, dass Sie die entsprechenden Updates gepackt und für Ihre Appliance zur Verfügung gestellt haben)
- Survivable Branch Server (SBS) mit Skype for Business Server 2015 CU6 HF2 oder höher
- Nur lync Server 2013- **Edge-Rolle**, dies liegt daran, dass die Edge-Rolle keine Abhängigkeit von Windows Fabric 1,0 hat.

### <a name="fully-tested-and-supported-clients"></a>Vollständig getestete und unterstützte Clients

- Lync 2013 (Skype for Business) Desktop Client, MSI und C2R, einschließlich grundlegender [15.0.5023.1000 oder höher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 oder höher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic
- Skype for Business 2016 klicken Sie auf Ausführen erfordern die Updates vom [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Monatlich und Semi-Annual Ziel, 16 \. 0 \. 9126 \. 2152 oder höher
    - Semi-Annual und verzögerter Kanal, 16 \. 0 \. 8431 \. 2242 oder höher
- Skype for Business auf Mac 16,15 oder höher
- Skype for Business für IOS und Android 6,19 oder höher
- Microsoft Teams-Räume (bisher als Skype Room System v2 SRS v2 bezeichnet) 4.0.64.0 (Dezember 2018) oder höher
- Surface Hub-Update für Team Edition basierend auf KB4499162 (Mai 2019, OS Build 15063,1835) oder höher
- Skype-Webanwendung 2015 CU6 HF2 oder höher (mit Server ausgeliefert)

### <a name="currently-being-investigated"></a>Derzeit untersucht

- Anruf Qualitäts Dashboard (neue Installation nach TLS 1,0, 1,1 wurden deaktiviert, siehe unten) *
 
### <a name="out-of-scope"></a>Nicht inbegriffen

Sofern nicht anders angegeben, sind die folgenden Produkte nicht im Bereich für TLS 1.0/1.1 Disable Support und funktionieren nicht in einer Umgebung, in der TLS 1,0 und 1,1 deaktiviert wurden. Was das bedeutet: Wenn Sie weiterhin out-of-Scope-Server oder-Clients verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 Anywhere in Ihrer Skype for Business Server lokalen Bereitstellung deaktivieren müssen.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 oder niedriger
- Lync für Mac 2011
- Lync 2013 für Mobile-IOS, iPad, Android oder Windows Phone
- Lync "MX" Windows Store-Client
- Lync Room System (aka SRSv1). LRS hat am 9. Oktober 2018 das Ende der Unterstützung erreicht und wird nicht zur Unterstützung von TLS 1,2 aktualisiert.
- Alle lync 2010 Clients
- Lync Phone Edition-Anleitung [hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)aktualisiert.
- 2013 basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Skype for Business für Windows Phone

### <a name="exceptions"></a>Ausnahmen

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 übernimmt eine Abhängigkeit von Windows Fabric, Version 1,0.  In der Entwurfsphase für lync Server 2013 wurde Windows Fabric 1,0 für die überzeugende und neue verteilte Architektur ausgewählt, um Replikation, hohe Verfügbarkeit und Fehlertoleranz bereitzustellen.  Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur mit erheblichem Re-Design in den nachfolgenden Versionen erheblich verbessert.  Der aktuelle Skype for Business 2015 Server verwendet beispielsweise Windows Fabric 3,0.

Leider unterstützt Windows Fabric 1,0 **TLS 1,2 nicht.  Wir werden jedoch lync Server 2013 aktualisieren, um mit TLS 1,2 zu arbeiten**. Dieser wird im nächsten kumulativen Update für lync Server 2013 bereit stehen.  Wir bieten TLS 1,2-Unterstützung, um Koexistenz-, Migrations-, Verbund-und Hybrid Szenarien zu ermöglichen.

Wenn Ihre Organisation TLS 1,0 und 1,1 deaktivieren muss und Sie derzeit lync Server 2013 verwenden, empfehlen wir Ihnen, den Planungsprozess mit der Möglichkeit zu beginnen, dass Sie möglicherweise ein direktes Upgrade oder eine parallele Migration (neue Pools, Benutzer verschieben) auf Skype for Business Server 2015 oder höher durchführen müssen.  Möglicherweise möchten Sie die Migration zu Skype for Business Online beschleunigen.

#### <a name="call-quality-dashboard"></a>Dashboard für Anrufqualität

Das lokale Anruf Qualitäts Dashboard verfügt derzeit über eine Abhängigkeit von TLS 1,0 bei der Neuinstallation (erstmalige Installation in Ihrer lokalen Umgebung).  Wir untersuchen derzeit dieses Problem und planen, eine Korrektur in naher Zukunft freizugeben.  Wenn Sie planen, CQD zu installieren und außerdem TLS 1,0 zu deaktivieren, wird empfohlen, zuerst die CQD-Installation abzuschließen und dann mit der Deaktivierung von TLS 1,0 fortzufahren.

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business Sdn Manager

Skype for Business Sdn Manager mit SQL-eine Datenbank verfügt über eine Abhängigkeit von TLS 1,0 während der neuen Installation. Wenn Sie planen, Skype for Business Sdn Manager mit einer SQL-Datenbank zu installieren und außerdem TLS 1,0 zu deaktivieren, empfehlen wir, zunächst Skype for Business Sdn Manager abzuschließen und dann mit der Deaktivierung von TLS 1,0 fortzufahren. Falls TLS 1,0 vor der Installation deaktiviert wurde, sollten Sie TLS 1,0 in SQL Server Back-End-Server, der zum Hosten Skype for Business Sdn Manager SQL-Datenbank verwendet wird, vorübergehend aktivieren.

#### <a name="third-party-devices"></a>Geräte von Drittanbietern

Auf Drittanbietergeräten wie 3PIP-Telefonen, Video Konferenzen, Reverse-Proxies und Lastenausgleichs stellen müssen Sie die TLS 1,2-Unterstützung validieren, sorgfältig testen und bei Bedarf den Anbieter kontaktieren.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Überlegungen zum Verbund beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern

Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihren Edge-Servern sorgfältig planen und berücksichtigen.  Wenn TLS 1,0 und 1,1 deaktiviert sind, können Sie feststellen, dass andere Organisationen nicht mehr in der Lage sind, mit Ihrer Organisation zu verbünden.

Sie können sich dafür entscheiden, TLS 1.0/1.1 auf Ihren Edge-Servern aktiviert zu halten, um die Abwärtskompatibilität mit externen Systemen ohne Patches (SFB 2015, lync 2013) oder älteren (2010) beizubehalten.

Microsoft kann keine Ratschläge oder Empfehlungen dazu abgeben, ob Ihr Edge-Netzwerk (oder ein beliebiges Netzwerk) unter den PCI-Standard fällt oder nicht. Dies muss durch das jeweilige Unternehmen bestimmt werden.

Skype for Business Online ist in der Lage, TLS 1,2 heute, so dass keine Auswirkungen auf Hybrid-/Verbund mit Online erwartet wird.

PIC (Public Chat Connectivity) an Skype Consumer Service: Es wird nicht erwartet, dass die Deaktivierung von TLS 1.0/1.1 die [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md)beeinträchtigt; Microsoft PIC-Gateways sind bereits TLS 1,2-fähig.

## <a name="prerequisites-and-process"></a>Voraussetzungen und Prozess

Wenn TLS 1,0 und 1,1 außerhalb des Bereichs Server deaktiviert sind, funktionieren Clients und Geräte auch länger ordnungsgemäß oder überhaupt nicht, sofern nicht weiter oben erwähnt. Dies kann bedeuten, dass Sie unterbrechen und auf aktualisierte Anleitungen von Microsoft warten müssen. Wenn Sie sicher sind, dass Sie alle Anforderungen erfüllen und einen Plan zum Beheben von Lücken haben, fahren Sie fort.

Auf einer hohen Ebene, während Skype for Business Server 2019 bei der Installation zur Verfügung steht, benötigen Skype for Business Server 2015 die Installation von ku9, das Anwenden von Voraussetzungen für .net und SQL, das Bereitstellen von erforderlichen Registrierungsschlüsseln und schließlich eine separate Runde von OS-Konfigurationsupdates (d. h. das Deaktivieren von TLS 1,0 und 1,1 über den Import von Registrierungsdateien). Es ist äußerst wichtig, dass Sie die Installation aller Voraussetzungen, einschließlich Skype for Business Server 2015 CU6 HF2, abschließen, bevor Sie TLS 1,0 und 1,1 auf einem beliebigen Server in Ihrer Umgebung deaktivieren. Jeder Skype for Business Server, einschließlich Edge-Rolle und SQL-Backends, erfordert die Updates. Stellen Sie außerdem sicher, dass alle unterstützten (in-Scope) Clients auf die erforderlichen minimal Versionen aktualisiert wurden. Vergessen Sie nicht, auch die Verwaltungsarbeitsstationen zu aktualisieren.

Wir möchten die übliche Reihenfolge der Vorgänge von "Inside Out" für das Upgrade von Skype for Business Servern befolgen. Behandeln Sie Director-Pools, beständigen Chat und verbundene Pools auf die gleiche Weise wie normalerweise. Die Reihenfolge und die Methoden für das Upgrade werden [hier](topology.md) und [hier](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)behandelt.

### <a name="high-level-process"></a>High-Level-Prozess

1. Testen Sie alle Schritte in der Übungseinheit vor dem Konfigurieren von Produktionsservern.
2. Sichern und bewahren Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll. Sie können keine Registrierungen zwischen Servern freigeben; Sie enthalten eindeutige computerbasierte Schlüssel.
3. Aktualisieren Sie alle Skype for Business 2015 Server auf ku9 oder höher. Für Skype for Business Server 2019 ein Upgrade auf ku1 oder höher durchführen.
4. Installieren Sie alle erforderlichen Komponenten auf allen Servern.
5. Bereitstellen von erforderlichen Registrierungsschlüsseln
6. Stellen Sie sicher, dass alle in-Scope-Clients aktualisiert werden.
7. Deaktivieren Sie TLS 1,0 und 1,1 über den Registrierungs Import.
8. Überprüfen, ob Arbeitsauslastungen wie erwartet funktionieren.
    - Wenn Probleme auftreten, beheben und beheben oder
    - Wiederherstellen der Registrierung aus Schritt 2 zur erneuten Aktivierung von TLS 1,0 und 1,1
9. Überprüfen Sie, dass nur TLS 1,2 verwendet wird.

### <a name="install-prerequisites-to-all-servers"></a>Installieren der erforderlichen Komponenten auf allen Servern

Bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen, ist eine umfassende Abhängigkeits Aktualisierung erforderlich. Im folgenden sind die Mindestversionen aufgeführt, die TLS 1,2 unterstützen können. Stellen Sie alle erforderlichen Updates auf allen Skype for Business Servern in Ihrer Umgebung bereit, bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 beginnen.

- Skype for Business Server 2015 ku9 6.0.9319.548 (Mai 2019) oder höher
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) oder höher mit aktivierter SchUseStrongCrypto in der Registrierung (unten bereitgestellt)
- SQL muss auf allen Skype for Business 2015 Servern und Backends aktualisiert werden. Aktualisieren Sie den Enterprise Edition-Pool SQL-Backends zuerst, dann ihre jeweiligen Fes. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)oder höher/SQL Server 2012 SP2 + ku16 oder höher/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)oder höher/SQL Server 2014 SP2
     - [SQL Server Native Client für SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 für SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)oder höher
     - [Gemeinsam genutzte Verwaltungsobjekte für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Grundlegende Schritte zur Installation von Voraussetzungen in der empfohlenen Reihenfolge von Vorgängen

1. Installieren Sie das Skype for Business Server ku9-Update auf allen Servern. 
    1. Installieren Sie das Update für Komponenten mit dem Updater.
    2. Aktualisieren von Datenbankennach dokumentierten Verfahren. Informationen zu Skype for Business Server 2015 finden Sie unter KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie mit anderen Änderungen fortfahren.
2. Laden Sie .NET 4,7 Offline Installer herunter. 
    1. Referenz [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden.
    3. Referenz [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Führen Sie das Installationspaket aus.
    7. Starten Sie den Server neu.
3. Aktualisieren Sie SQL Express 2014 auf allen Servern. 
    1. Referenz [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Herunterladen von SQL 2014 SP2 
        - Referenz [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Kopieren Sie das Installationsmedium in einen Ordner auf dem Server (z. b.: \ 01_2014SqlSp2).
    4. Sicherstellen, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Öffnen einer Administrator-Eingabeaufforderung und Aktualisieren aller installierten Komponenten und Instanzen 
        - Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS-Parameter/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Aktualisieren von SQL Native Client. 
    1. Referenz: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Herunterladen von [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten wurden. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Beenden der Ausführung von SQL-Instanzen 
        - Ex ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (nur Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installieren Sie das Update.
5. Aktualisieren Sie den ODBC-Treiber 11 für SQL Server, um die Unterstützung für TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) einzuschließen.
    1. Laden Sie [ODBC Driver 11 für SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)herunter.
    2. Stellen Sie sicher, dass Skype for Business Server 2015 Dienste auf dem Front-End-Server angehalten werden.
        - Beispiel (Standard Edition): ```Stop-CsWindowsService```
        - Beispiel (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Installieren Sie das Update.
6. Bereitstellen von erforderlichen Registrierungsschlüsseln

### <a name="pre-requisite-registry-keys"></a>Voraussetzungen für Registrierungsschlüssel

Kopieren/fügen Sie den folgenden Test in Notepad ein, und benennen Sie TLSPreReq. reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Für SQL-Back-Ends für Enterprise Edition-Pools sollten Voraussetzungen und TLS-Deaktivierung wie alle SQL-oder BS-Updates behandelt werden; Siehe: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Zwar können sowohl die erforderlichen Schritte für die erforderliche Anwendung als auch die TLS-Deaktivierung kombiniert werden, es wird jedoch dringend empfohlen, alle Voraussetzungen anzuwenden, bevor Sie mit dem Deaktivieren von TLS 1,0 und 1,1 auf Betriebssystemebene fortfahren. Die bewährte Methode besteht darin, die Umgebung vorzubereiten, indem Sie alle Voraussetzungen bereitstellen, überprüfen, ob die Arbeitslasten ordnungsgemäß und wie erwartet funktionieren, und dann zu einem späteren Zeitpunkt mit der TLS 1.0/1.1-Deaktivierung fortfahren.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deaktivieren von TLS 1,0 und 1,1 über den Registrierungs Import

Bevor Sie mit den nächsten Schritten fortfahren, *Stellen Sie sicher, dass Sie alle Voraussetzungen erfüllt und Skype for Business Server aktualisiert haben*.

Kopieren Sie den folgenden Text in eine Notepad-Datei, und benennen Sie Sie **TLSDisable. reg** um:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importieren Sie die reg-Datei auf jedem Server, auf dem TLS 1,0 und 1,1 deaktiviert werden sollen. Starten Sie den Server neu. Wenn die Dienste wieder online sind, navigieren Sie zum nächsten Server. Der Ansatz für Enterprise Edition-Pools ist die gleiche, die Sie für jedes Betriebssystemupdate ausführen würden.

Sie haben vielleicht bemerkt, dass wir mehr tun, als nur TLS 1,0 und 1,1 hier zu deaktivieren. Wir unterstützen die erneute Reihenfolge von Cipher Suite (siehe oben) und die Deaktivierung einiger älterer schwacher Chiffren. Dies ist das erste Mal, dass wir diese Änderungen an SChannel und der Crypto-API auf Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir unterstützen und zu diesem Zeitpunkt getestet haben. Wir können in Zukunft zusätzliche Konfigurationen in Frage stellen, aber jetzt sollten Sie die Registrierungs Importdatei nicht in ihrer Implementierung ändern.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Überprüfen, ob Arbeitsauslastungen wie erwartet funktionieren

Nachdem TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Ihre Haupt Arbeitslasten wie erwartet funktionieren, beispielsweise Chat & Anwesenheit, P2P-Anrufe, Enterprise-VoIP usw.

**Überprüfen, ob nur TLS 1,2 verwendet wird**

Lassen Sie Ihr Sicherheits Team eine neue Überprüfung Skype for Business Datenverkehrs durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1,0 und 1,1 nicht mehr verwendet werden.

Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen mit Webdiensten von Skype for Business Server 2015 zu testen, nachdem TLS 1,0 und TLS 1,1 deaktiviert wurden.

1. Starten Sie Internet Explorer.
2. Wählen Sie **Extras**  >  **Internet Optionen** aus.
3. Wählen Sie die Registerkarte **erweitert** aus.
4. Scrollen Sie unter **Einstellungen** nach unten.
5. Stellen Sie sicher, dass TLS 1,0, TLS 1,1 und TLS 1,2 aktiviert sind.
6. Durchsuchen Sie die interne Webdienst-URL Ihres SFB 2015-Pools (sollte erfolgreich eine Verbindung herstellen).
7. Wechseln Sie zurück in Internet Explorer, und deaktivieren Sie die Option nur **TLS 1,2 verwenden** .
8. Durchsuchen Sie die interne Webdienst-URL Ihres SFB 2015-Pools erneut (sollte keine Verbindung hergestellt werden).

![Internet Optionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Erweiterte Bereitstellungsszenarien

Da für die Unterstützung von TLS 1,2 in Skype for Business Server 2015 einige erforderliche Abhängigkeiten erforderlich sind, kann die Installation von RTM-Medien auf keinem System fehlschlagen, auf dem TLS 1,0 und 1,1 deaktiviert wurden.

**Bereitstellen neuer Standard Edition-Server oder Enterprise Edition-Pools, wenn TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden.**

**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL-Binärdateien in einer zukünftigen Cu aufzunehmen, und diesen Artikel in Zukunft aktualisieren werden.

**Option 2:** Lokale SQL-Instanzen vorab installieren (RTCLOCAL und LYNCLOCAL)

1. Laden Sie SQL Express 2014 SP2 (SQLEXPR_x64.exe) in den lokalen Ordner auf FE herunter, und kopieren Sie es. Angenommen, der Ordnerpfad <SQL_FOLDER_PATH>.
2. Starten Sie PowerShell oder Eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.
3. Erstellen Sie die RTCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie fortfahren:

    SQLEXPR_x64.exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "VORDEFINIERT\Administratoren"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati
1. Erstellen Sie die LYNCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie mit dem nächsten Schritt fortfahren:

    SQLEXPR_x64.exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "VORDEFINIERT\Administratoren"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Führen Sie Skype for Business Server 2015 RTM-Setup aus.
2. Befolgen Sie die restlichen Schritte im Abschnitt Voraussetzungen weiter oben.

**Option 3:** Sie können Binärdateien auch manuell in einem lokalen Installationsmedien Verzeichnis wie folgt ersetzen:

1. [Installieren der Voraussetzungen für Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installieren von .NET 4,7: 
      - **Hinweis:** Wir haben zunächst die Unterstützung für .NET 4,7 in Skype for Business Server 2015 CU5 (6.0.9319.281) eingeführt. In den nachfolgenden Schritten werden daher die wichtigsten Komponenten vor der Hauptinstallation aktualisiert.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referenz: [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Kopieren von ISO-Dateien/Ordnern: 
    - Wenn die Skype for Business Server 2015 ISO angefügt ist, öffnen Sie das Stammverzeichnis des Laufwerks, dem es angefügt ist (ex: D: \) im Datei-Explorer.
    - Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. b.: C:\SkypeForBusiness2015ISO).
    - **Hinweis:** Vor dem Installieren von Komponenten müssen einige Dateien für die Unterstützung von TLS 1,2 aktualisiert werden.
4. Ersetzen Sie MSI/exe-Pakete: 
    - Ersetzen Sie die vorhandenen MSI-und exe-Pakete im Ordner/Setup/amd64/des Installationsmediums auf dem lokalen Computer.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Benennen Sie den SQLEXPR_x64 auf dem lokalen Computer um, und ersetzen Sie die vorhandene Datei im Setup/amd64/Ordner des Installationsmediums.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Hinweis:** Benennen Sie diese gegebenenfalls in sqlncli.msi um, und ersetzen Sie dann die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.
    - SQL-Verwaltungsobjekte: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält eine Vielzahl von Elementen, die heruntergeladen werden können. Wählen Sie aus, um SharedManagementObjects.msi nur herunterzuladen.
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.
    - SQL CLR-Typen: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält eine Vielzahl von Elementen, die heruntergeladen werden können. Auswählen, um nur CQLSysClrTypes.msi herunterzuladen
        - **Hinweis**: Ersetzen Sie die vorhandene Datei, die im Setup/amd64/Ordner des Installationsmediums vorhanden ist.
5. Installieren von Hauptkomponenten: 
    - Führen Sie Setup.exe aus dem Setup/amd64/Ordner des Installationsmediums aus. Befolgen Sie die Anweisungen zum Installieren von Hauptkomponenten.
    - Schließen Sie die Kernkomponenten.
6. Aktualisieren der Kernkomponenten: 
    - Laden Sie das Installationsprogramm für Skype for Business Updates herunter.
    - Führen Sie das Installationsprogramm aus, um die Hauptkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.
    - **Hinweis:** Ab der Veröffentlichung von CU6HF2 wird die automatische Update Funktion derzeit nur bis zu CU6 installieren. Daher muss der Updater separat ausgeführt werden, um die Hauptkomponenten auf 6.0.9319.516 zu aktualisieren.
    - Referenz https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installieren von Verwaltungs Tools (optional): 
    - Auf diese Weise werden die Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) und Microsoft System CLR-Typen für SQL Server 2014 (x64) unter Verwendung der aktualisierten Dateien installiert. Darüber hinaus wird der Skype for Business Server 2015 Topologie-Generator und die Systemsteuerung auf dem lokalen Computer verfügbar sein.
8. Installieren des lokalen Konfigurationsspeichers (Schritt 1): 
     - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Sie Skype for Business Server System, und klicken Sie auf **Ausführen** unter Schritt 1: Installieren des lokalen Konfigurationsspeichers.
     - Klicken Sie im Dialogfeld **lokalen Konfigurationsspeicher installieren** auf **weiter** .
     ![Dialogfeld zum Installieren des lokalen Konfigurationsspeichers](../../media/local-configuration-store.png)
     - Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Aufgaben Status abgeschlossen ist. Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **Protokoll anzeigen** klicken.
     ![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)
     - Klicken Sie auf **Fertig stellen**.
9. Einrichten oder Entfernen von Skype for Business Server Komponenten (Schritt 2):
    - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **Skype for Business Server System installieren oder aktualisieren**, und klicken Sie dann auf **Ausführen** von Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen
    - Klicken Sie im Dialogfeld Skype for Business Server Komponenten einrichten auf **weiter** .
    ![Das Fenster Skype for Business Server Komponenten einrichten](../../media/set-up-skype-for-business-server-components-window.png)
    - Überprüfen Sie das Protokoll mit View Log, und überprüfen Sie, ob das Setup ohne Probleme abgeschlossen wurde. 
    - Klicken Sie auf **Fertig stellen**.
10. Fahren Sie bei Bedarf mit zusätzlicher Installation und Konfiguration fort (Sie können zu diesem Zeitpunkt die normalen Installationsverfahren fortsetzen).
