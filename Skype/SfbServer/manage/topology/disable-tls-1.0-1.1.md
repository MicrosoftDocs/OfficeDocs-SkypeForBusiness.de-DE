---
title: Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten und Implementieren der Deaktivierung von TLS 1,0 und 1,1 in Ihrer Umgebung.'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275241"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015

In diesem Artikel werden die erforderlichen Anleitungen bereitgestellt, mit denen Sie die Deaktivierung von TLS 1,0 und 1,1 in ihren Umgebungen vorbereiten und implementieren können. Dieser Vorgang erfordert eine umfassende Planung und Vorbereitung. Bitte überprüfen Sie sorgfältig alle Informationen in diesem Artikel, während Sie Ihren Plan zur Deaktivierung von TLS 1,0 und 1,1 für Ihre Organisation festlegen. Beachten Sie, dass es viele externe Abhängigkeiten und Verbindungsbedingungen gibt, die durch das Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden können, daher ist eine umfassende Planung und Prüfung gewährleistet.

## <a name="in-this-article"></a>In diesem Artikel

- [Hintergrund und Bereich](#background)
- [Voraussetzungen und Prozesse](#prerequisites-and-process)
- [Erweiterte Bereitstellungsszenarien](#advanced-deployment-scenarios)

## <a name="background"></a>Hintergrund

Die primären Treiber für die Bereitstellung von TLS 1,0 und 1,1 für die Unterstützung von Skype for Business Server lokal sind die Standards für die Datenverarbeitung in der Zahlungskartenbranche (PCI) Security Standards Council und Federal Information Processing Standards. Weitere Informationen zu PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft kann keine Anleitungen dazu liefern, ob Ihre Organisation diese oder andere Anforderungen erfüllen muss. Sie müssen feststellen, ob es für Sie erforderlich ist, TLS 1,0 und/oder 1,1 in ihren Umgebungen zu deaktivieren.

Microsoft hat [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)ein Whitepaper zu TLS erstellt, und wir empfehlen auch die Hintergrund Lektüre, die in diesem [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbar ist.

## <a name="supportability-scope"></a>Unterstützungsbereich

Der *Bereich* bezieht sich auf Unterstützungs Begrenzungen. Für Skype for Business Server lokal *im Bereich* bedeutet, dass wir die Deaktivierung von TLS 1,0 und 1,1 für die aufgelisteten Produktversionen vollständig unterstützen und getestet haben. *Derzeit untersucht wird* , bedeutet genau dies; Wir untersuchen aktiv, wie diese Produkte in den Anwendungsbereich der TLS-Deaktivierung gebracht werden. *Außerhalb des gültigen Bereichs* bedeutet, dass diese Produktversionen die Deaktivierung von TLS 1,0 oder 1,1 nicht unterstützen und mit bekannten Ausnahmen nicht funktionieren.

### <a name="fully-tested-and-supported-servers"></a>Vollständig getestete und unterstützte Server

- Skype for Business Server 2019
- Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([März 2018 Update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) und höher: 
    - Windows Server 2012 (mit KB 3140245 oder Ersetzen von Update), 2012 R2 oder 2016
- In-Place-Upgrade von Skype for Business Server 2015, mit CU6 HF2 und höher 
    - Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder Ersetzen von Update) oder 2012 R2
- Exchange-Konnektivität und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Überlebensfähige Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 HF2 oder höher (bestätigen Sie bei Ihrem Anbieter, dass Sie die entsprechenden Updates verpackt haben und für Ihre Appliance zur Verfügung gestellt wurden)
- Survivor Branch Server (SBS) mit Skype for Business Server 2015 CU6 HF2 oder höher
- Nur lync Server 2013- **Edge-Rolle**, das liegt daran, dass die Edge-Rolle keine Abhängigkeit von Windows Fabric 1,0 aufweist.


### <a name="fully-tested-and-supported-clients"></a>Vollständig getestete und unterstützte Clients

- Lync 2013 (Skype for Business)-Desktop Client, MSI und C2R, einschließlich grundlegender [15.0.5023.1000 und höher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016-Desktop Client, MSI [16.0.4678.1000 und höher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic
- Für Skype for Business 2016-Click-to-Run sind die Updates vom [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) erforderlich: 
    - Monatlich und halbjährlich ausgerichtet, 16\.0\.9126\.2152 und höher
    - Halbjährlicher und verzögerter Kanal, 16\.0\.8431\.2242 und höher
- Skype for Business für Mac 16,15 und höher
- Skype for Business für IOS und Android 6,19 und höher
- Skype Web App 2015 CU6 HF2 und höher (ausgeliefert mit Server)

### <a name="currently-being-investigated"></a>Derzeit untersucht

#### <a name="devices"></a>Geräte

- Lync Room System (aka SRSv1)
- Microsoft Teams-Räume
- Surface Hub
- 2015-basierte, überlebensfähige Branch Appliance (SBA) oder Survivable Branch Server (SBS)

#### <a name="other"></a>Andere

- Dashboard für die Anrufqualität (neue Installation nach TLS 1,0, 1,1 wurden deaktiviert, siehe unten) *
 
### <a name="out-of-scope"></a>Außerhalb des Bereichs

Sofern nicht anders angegeben, sind die folgenden Produkte nicht im Bereich für die TLS 1.0/1.1-Unterstützung deaktiviert und funktionieren in einer Umgebung, in der TLS 1,0 und 1,1 deaktiviert wurden.  Was dies bedeutet: Wenn Sie weiterhin Server oder Clients außerhalb des Geltungsbereichs verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrer lokalen Skype for Business Server-Bereitstellung deaktivieren müssen.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 und niedriger
- Lync für Mac 2011
- Lync 2013 für Handys – IOS, iPad, Android oder Windows Phone
- Lync "MX" Windows Store-Client
- Alle lync 2010-Clients
- Lync Phone Edition – aktualisierte Anleitungen [finden Sie hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013-basierte, überlebensfähige Branch Appliance (SBA) oder Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Microsoft Skype for Business für Windows Phone

### <a name="exceptions"></a>Ausnahmen

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 übernimmt eine Abhängigkeit von Windows Fabric, Version 1,0.  In der Entwurfsphase von lync Server 2013 wurde Windows Fabric 1,0 für seine überzeugende und neue verteilte Architektur ausgewählt, um Replikation, höchste Verfügbarkeit und Fehlertoleranz bereitzustellen.  Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur erheblich verbessert, wobei in späteren Versionen ein erhebliches Re-Design zu finden ist.  Der aktuelle Skype for Business 2015-Server verwendet beispielsweise Windows Fabric 3,0.

Leider unterstützt Windows Fabric 1,0 **TLS 1,2 nicht.  Wir werden jedoch lync Server 2013 aktualisieren, um mit TLS 1,2 zu arbeiten**. Dies wird im nächsten kumulativen Update für lync Server 2013 erfolgen.  Wir bieten TLS 1,2-Unterstützung, um Koexistenz-, Migrations-, Föderations-und Hybrid Szenarien zu ermöglichen.

Wenn Ihre Organisation TLS 1,0 und 1,1 deaktivieren muss und Sie zurzeit lync Server 2013 verwenden, empfehlen wir, dass Sie den Planungsprozess beginnen, mit der Möglichkeit, dass Sie möglicherweise ein direktes Upgrade oder eine parallele Migration (neue Pools, Verschieben von Benutzern) zu Skype für Business Server 2015 oder höher  Oder Sie möchten vielleicht die Migration zu Skype for Business Online beschleunigen.

#### <a name="call-quality-dashboard"></a>Anrufqualitäts-Dashboard

Das lokale Anruf Qualitäts Dashboard hat derzeit eine Abhängigkeit von TLS 1,0 bei der Neuinstallation (erstmalige Installation in Ihrer lokalen Umgebung).  Wir untersuchen derzeit dieses Problem und planen, in naher Zukunft eine Lösung zu veröffentlichen.  Wenn Sie beabsichtigen, CQD zu installieren und auch TLS 1,0 zu deaktivieren, empfehlen wir, zuerst die CQD-Installation abzuschließen und dann mit der Deaktivierung von TLS 1,0 fortzufahren.

#### <a name="third-party-devices"></a>Geräte von Drittanbietern

Achten Sie bei Geräten von Drittanbietern wie 3PIP-Telefonen, Video Konferenzen, Reverse-Proxys und Last-Balancern darauf, dass Sie die TLS 1,2-Unterstützung überprüfen, sorgfältig testen und bei Bedarf mit dem Anbieter in Verbindung treten.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Überlegungen zur Föderation beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern

Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihren Edge-Servern sorgfältig planen und berücksichtigen.  Wenn TLS 1,0 und 1,1 deaktiviert sind, stellen Sie möglicherweise fest, dass andere Organisationen nicht mehr mit Ihrer Organisation zusammenarbeiten können.

Sie können festlegen, dass TLS 1.0/1.1 auf Ihren Edge-Servern aktiviert bleibt, damit die Abwärtskompatibilität mit nicht gepatchten (SFB 2015, lync 2013) oder älteren (2010) externen Systemen gewährleistet ist.

Microsoft kann keine Ratschläge oder Empfehlungen liefern, ob Ihr Edge-Netzwerk (oder irgendein Netzwerk) unter den PCI-Standard fällt. Dies muss vom jeweiligen Unternehmen festgelegt werden.

Skype for Business Online ist heute in der Lage, TLS 1,2 zu nutzen, sodass keine Auswirkungen auf Hybrid/Federation mit Online erwartet werden.

PIC (Public-Chat-Konnektivität) zum Skype-Verbraucher Dienst: Wir erwarten nicht, dass die Deaktivierung von TLS 1.0/1.1 Auswirkungen auf die [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md)hat. Microsoft PIC-Gateways sind bereits TLS 1,2-fähig.

## <a name="prerequisites-and-process"></a>Voraussetzungen und Prozesse

Sofern oben nicht erwähnt, funktionieren Clients und Geräte nach der Deaktivierung von TLS 1,0 und 1,1 außerhalb des Bereichs nicht mehr ordnungsgemäß. Dies bedeutet möglicherweise, dass Sie die Aktualisierung unterbrechen und auf aktualisierte Anleitungen von Microsoft warten müssen. Wenn Sie davon überzeugt sind, dass Sie alle Anforderungen erfüllen und einen Plan zur Behebung von Lücken haben, fahren Sie fort.

Auf einem hohen Niveau, während Skype for Business Server 2019 bei der Installation einsatzbereit ist, erfordert Skype for Business Server 2015, dass Sie CU6 HF2 installieren, Voraussetzungen für .net und SQL installieren, erforderliche Registrierungsschlüssel bereitstellen und schließlich eine separate Runde der Betriebssystem-Konfigurationsupdates (d. h. das Deaktivieren von TLS 1,0 und 1,1 über den Import von Registrierungsdateien). Es ist äußerst wichtig, dass Sie die Installation aller Voraussetzungen, einschließlich Skype for Business Server 2015 CU6 HF2, abschließen, bevor Sie TLS 1,0 und 1,1 auf einem beliebigen Server in Ihrer Umgebung deaktivieren. Für jeden Skype for Business-Server, einschließlich Edge-Rolle und SQL-Backends, sind die Updates erforderlich. Stellen Sie außerdem sicher, dass alle unterstützten (in-Scope-) Clients auf die erforderlichen Mindestversionen aktualisiert wurden. Vergessen Sie nicht, Management-Workstations auch zu aktualisieren.

Wir möchten die übliche Reihenfolge der Vorgänge von "Inside Out" für das Upgrade von Skype for Business-Servern befolgen. Behandeln Sie Director-Pools, beständigen Chat und gekoppelte Pools auf die gleiche Weise wie normalerweise. Reihenfolge und Methoden für das Upgrade werden [hier](topology.md) und [hier](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)behandelt.

### <a name="high-level-process"></a>Prozess auf höherer Ebene

1. Testen Sie alle Schritte in Ihrer Testumgebung, bevor Sie Produktionsserver konfigurieren.
2. Sichern Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll, und bewahren Sie Sie auf. Sie können keine Registrierungen zwischen Servern freigeben. Sie enthalten eindeutige, auf Computern basierende Schlüssel.
3. Aktualisieren Sie alle Skype for Business 2015-Server auf CU6 HF2 oder höher. (Für Skype for Business Server 2019 ist keine Cu erforderlich)
4. Installieren Sie alle Voraussetzungen für alle Server.
5. Bereitstellen von erforderlichen Registrierungsschlüsseln
6. Stellen Sie sicher, dass alle in-Scope-Clients aktualisiert werden.
7. Deaktivieren Sie TLS 1,0 und 1,1 mithilfe des Registrierungs Imports.
8. Überprüfen Sie, ob Arbeitslasten wie erwartet funktionieren.
    - Wenn Probleme aufgetreten sind, beheben und beheben oder
    - Wiederherstellen der Registrierung aus Schritt 2 zum erneuten Aktivieren von TLS 1,0 und 1,1
9. Überprüfen Sie, ob nur TLS 1,2 verwendet wird.

### <a name="install-prerequisites-to-all-servers"></a>Installieren von Voraussetzungen für alle Server

Umfassende Abhängigkeits Updates sind erforderlich, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen. Im folgenden sind die Mindestversionen aufgeführt, die TLS 1,2 unterstützen können. Stellen Sie alle erforderlichen Updates für alle Skype for Business-Server in Ihrer Umgebung bereit, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 beginnen.

- Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([März 2018 Update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) oder höher
- [.NET Framework 4,7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) oder höher mit aktiviertem SchUseStrongCrypto in der Registrierung (siehe unten)
- SQL muss auf allen Skype for Business 2015-Servern und-Backends aktualisiert werden. Aktualisieren Sie den Enterprise Edition-Pool SQL-Backends zuerst und dann den jeweiligen Fes. 
    - SQL Server 2014 SP1 + CU5 ([Link](https://support.microsoft.com/help/3130926)) oder höher/SQL Server 2012 SP2 + CU16 oder höher/SQL Server 2014 RTM + CU12 ([Link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) oder höher/SQL Server 2014 SP2
    - SQL Server Native Client für SQL Server 2012 ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Microsoft ODBC-Treiber 11 für SQL Server ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) oder höher
    - Freigegebene Verwaltungsobjekte für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Grundlegende Schritte zum Installieren von Voraussetzungen in der empfohlenen Reihenfolge von Vorgängen

1. Installieren Sie das Skype for Business Server CU6HF2 (6.0.9319.516)-Update auf allen Servern. 
    1. Installieren Sie das Update auf Komponenten mithilfe des Updates.
    2. Aktualisieren Sie Datenbankennach dokumentierten Verfahren. Anweisungen sind unter [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)dokumentiert.
    3. Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie weitere Änderungen vornehmen.
2. .NET 4,7 Offline-Installationsprogramm herunterladen. 
    1. Referenz[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server angehalten werden.
    3. Referenz[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): Stop-CsWindowsServices
    5. Ex (Enterprise Edition): Invoke-CsComputerFailover
    6. Führen Sie das Installationspaket aus.
    7. Starten Sie den Server neu.
3. Aktualisieren Sie SQL Express 2014 auf allen Servern. 
    1. Referenz[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Herunterladen von SQL 2014 SP2 
        - Referenz[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Kopieren Sie das Installationsmedium in einen Ordner auf dem Server (z. b.: C:\01_2014SqlSp2).
    4. Sicherstellen, dass die Dienste von Skype for Business Server 2015 auf dem Front-End-Server angehalten werden 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    5. Öffnen Sie eine Administratoreingabeaufforderung, und aktualisieren Sie alle installierten Komponenten und Instanzen. 
        - Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS-Parameter/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Aktualisieren Sie SQL Native Client. 
    1. Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Herunterladen von[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server angehalten werden. 
        - Ex (Standard Edition): Stop-CsWindowsServices
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Beenden der ausgeführten SQL-Instanzen 
        - Ex: Get-Service "MSSQL $ RTCLOCAL" | Stop-Service
        - Ex: Get-Service "MSSQL $ LYNCLOCAL" | Stop-Service
        - Ex (nur Standard Edition): Get-Service "MSSQL $ RTC" | Stop-Service
    5. Installieren Sie das Update.
5. Aktualisieren Sie den ODBC-Treiber 11 für SQL Server. 
    1. Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Herunterladen von[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Sicherstellen, dass die Dienste von Skype for Business Server 2015 auf dem Front-End-Server angehalten werden 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Installieren Sie das Update.
6. Bereitstellen von erforderlichen Registrierungsschlüsseln

### <a name="pre-requisite-registry-keys"></a>Voraussetzungen für Registrierungsschlüssel

Kopieren/fügen Sie den folgenden Test in den Editor ein, und benennen Sie TLSPreReq. reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:

```
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

Für SQL-Back-Ends für Enterprise Edition-Pools sollten Voraussetzungen und TLS-Deaktivierung als SQL-oder Betriebssystemupdates behandelt werden. Weitere Informationen finden Sie unter:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Während die Schritte für die Voraussetzungen für die Anwendungs-und TLS-Deaktivierung kombiniert werden können, empfehlen wir dringend, alle Voraussetzungen anzuwenden, bevor Sie mit der Deaktivierung von TLS 1,0 und 1,1 auf Betriebssystemebene fortfahren. Der bewährte Methodenansatz besteht darin, die Umgebung vorzubereiten, indem alle Voraussetzungen bereitgestellt werden, die Überprüfung, ob Arbeitsauslastungen ordnungsgemäß und wie erwartet funktionieren, und dann zu einem späteren Zeitpunkt die Deaktivierung von TLS 1.0/1.1 fortgesetzt wird.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deaktivieren von TLS 1,0 und 1,1 über den Registrierungs Import

Bevor Sie mit den nächsten Schritten fortfahren, *Stellen Sie sicher, dass Sie alle Voraussetzungen und aktualisierten Skype for Business-Server abgeschlossen haben*.

Kopieren Sie den folgenden Text in eine Notepad-Datei, und benennen Sie ihn **TLSDisable. reg**um:

```
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

Importieren Sie die reg-Datei auf jedem Server, auf dem Sie TLS 1,0 und 1,1 deaktivieren möchten. Starten Sie den Server neu. Wenn die Dienste wieder online sind, wechseln Sie zum nächsten Server. Der Ansatz für Enterprise Edition-Pools ist für jedes Betriebssystemupdate identisch.

Sie haben vielleicht bemerkt, dass wir hier mehr tun, als nur TLS 1,0 und 1,1 zu deaktivieren. Wir unterstützen die erneute Reihenfolge der Verschlüsselungs Suite (wie oben dargestellt) und die Deaktivierung einiger älterer schwacher Chiffren. Dies ist das erste Mal, dass wir diese Änderungen an der Schannel-und Krypto-API in Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir zurzeit unterstützen und getestet haben. Wir können in Zukunft zusätzliche Konfigurationen in Erwägung gezogen, aber im Moment sollten Sie die Registrierungs Importdatei in ihrer Implementierung nicht ändern.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Überprüfen, ob Arbeitslasten wie erwartet funktionieren

Nachdem TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Ihre wichtigsten Arbeitslasten wie erwartet funktionieren, wie etwa im &-Anwesenheitsstatus, P2P-anrufen, Enterprise-VoIP usw.

**Nur überprüfen, ob TLS 1,2 verwendet wird**

Lassen Sie Ihr Sicherheits Team eine neue Prüfung des Skype for Business-Datenverkehrs durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1,0 und 1,1 nicht mehr verwendet werden.

Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen mit Webdiensten von Skype for Business Server 2015 zu testen, nachdem TLS 1,0 und TLS 1,1 deaktiviert wurden.

1. Starten Sie Internet Explorer.
2. Wählen Sie **Extras** > **Internet Optionen**aus.
3. Wählen Sie die Registerkarte **erweitert** aus.
4. Scrollen Sie unter **Einstellungen**nach unten.
5. Überprüfen Sie, ob TLS 1,0, TLS 1,1 und TLS 1,2 aktiviert sind.
6. Durchsuchen Sie die interne Web Service-URL Ihres SFB 2015-Pools (sollte eine Verbindung erfolgreich hergestellt werden).
7. Wechseln Sie zurück in Internet Explorer, und deaktivieren Sie die Option nur für **TLS 1,2** .
8. Durchsuchen Sie die interne Web Service-URL Ihres SFB 2015-Pools erneut (Verbindungsfehler).

![Internet Optionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Erweiterte Bereitstellungsszenarien

Da einige Abhängigkeits Voraussetzungen zur Unterstützung von TLS 1,2 in Skype for Business ser 2015 erforderlich sind, schlägt die Installation von RTM-Medien auf jedem System fehl, auf dem TLS 1,0 und 1,1 deaktiviert wurden.

**Bereitstellen von neuen Standard Edition-Servern oder Enterprise Edition-Pools, sobald TLS 1,0 und 1,1 in Ihrer Umgebung deaktiviert wurden.**

**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL-Binärdateien in einem zukünftigen Cu-Daten Satz aufnehmen zu können, und diesen Artikel in Zukunft aktualisieren werden.

**Option 2:** Lokale SQL-Instanzen (RTCLOCAL und LYNCLOCAL) vor der Installation

1. Laden Sie SQL Express 2014 SP2 (SQLEXPR_x64. exe) in den lokalen Ordner auf FE herunter, und kopieren Sie Sie. Sagen wir Ordnerpfad <SQL_FOLDER_PATH>.
2. Starten Sie PowerShell oder Eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.
3. Erstellen Sie die RTCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis "SQLEXPR_x64. exe" abgeschlossen ist, bevor Sie fortfahren:

    SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administratoren "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = automati
1. Erstellen Sie die LYNCLOCAL-SQL-Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64. exe beendet ist, bevor Sie mit dem nächsten Schritt fortfahren:

    SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/instanceName = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Administratoren "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = Automatic
1. Führen Sie das Setup von Skype for Business Server 2015 RTM aus.
2. Führen Sie die restlichen Schritte aus dem Abschnitt Voraussetzungen oben aus.

**Option 3:** Sie können Binärdateien in einem lokalen Installationsmedien Verzeichnis auch manuell wie folgt ersetzen:

1. [Installieren von Voraussetzungen für Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. 2. Installieren Sie .NET 4,7: 
      - **Hinweis:** Wir haben zunächst die Unterstützung für .NET 4,7 in Skype for Business Server 2015 CU5 + (6.0.9319.281) eingeführt. Aus diesem Grund werden wir in den nachfolgenden Schritten die wichtigsten Komponenten vor der Hauptinstallation aktualisieren.
      - Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Referenz: [Software, die vor der Bereitstellung von Skype for Business Server 2015 installiert werden soll](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Kopieren von ISO-Dateien/-Ordnern: 
    - Wenn der Skype for Business Server 2015 ISO angeschlossen ist, öffnen Sie das Stammverzeichnis des Laufwerks, dem es angefügt ist (ex\) : D: im Datei-Explorer.
    - Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. b.: C:\SkypeForBusiness2015ISO).
    - **Hinweis:** Vor der Installation von Komponenten müssen einige Dateien für die Unterstützung von TLS 1,2 aktualisiert werden.
4. Ersetzen Sie MSI/exe-Pakete: 
    - Ersetzen Sie die vorhandenen MSI-und exe-Pakete im Ordner/Setup/amd64/des Installationsmediums auf dem lokalen Computer.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Benennen Sie SQLEXPR_x64 auf dem lokalen Computer um, und ersetzen Sie die vorhandene Datei im Setup/amd64/-Ordner des Installationsmediums.
    - SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Hinweis:** Benennen Sie diese bei Bedarf in sqlncli. msi um, und ersetzen Sie dann die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.
    - SQL-Verwaltungsobjekte:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können. Wählen Sie diese Option aus, um nur SharedManagementObjects. msi herunterzuladen.
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.
    - SQL CLR-Typen:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können. Zum Herunterladen von CQLSysClrTypes. msi auswählen
        - **Hinweis**: Ersetzen Sie die vorhandene Datei, die im Setup/amd64/-Ordner des Installationsmediums vorhanden ist.
5. Installieren von Kernkomponenten: 
    - Führen Sie Setup. exe aus dem Setup/amd64/Ordner des Installationsmediums aus. Befolgen Sie die Anweisungen zum Installieren der Kernkomponenten.
    - Schließen Sie Kernkomponenten.
6. Aktualisieren von Kernkomponenten: 
    - Laden Sie das Skype for Business Update-Installationsprogramm herunter.
    - Führen Sie das Installationsprogramm aus, um die Kernkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.
    - **Hinweis:** Ab der Veröffentlichung von CU6HF2 wird das Feature für die automatische Aktualisierung zurzeit nur bis zu CU6 installiert. Daher muss der Updater separat ausgeführt werden, um Kernkomponenten auf 6.0.9319.516 zu aktualisieren.
    - Referenzhttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Installieren von Verwaltungs Tools (optional): 
    - Damit werden die Microsoft SQL Server 2012 Native Client-, SQL Server 2014 Management Objects (x64)-und Microsoft System CLR-Typen für SQL Server 2014 (x64) unter Verwendung der aktualisierten Dateien installiert. Darüber hinaus steht der Skype for Business Server 2015-Topologie-Generator und die Systemsteuerung auf dem lokalen Computer zur Verfügung.
8. Installieren des lokalen Konfigurationsspeichers (Schritt 1): 
     - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Sie das Skype for Business Server-System, und klicken Sie auf **Ausführen** unter Schritt 1: Installieren des lokalen Konfigurationsspeichers.
     - Klicken Sie im Dialogfeld **lokalen Konfigurationsspeicher installieren** auf **weiter** .
     ![Dialogfeld ' lokalen Konfigurationsspeicher installieren '](../../media/local-configuration-store.png)
     - Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Vorgangs Status abgeschlossen ist. Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **Protokoll anzeigen**klicken.
     ![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)
     - Klicken Sie auf **Fertig stellen**.
9. Einrichten oder Entfernen von Skype for Business Server-Komponenten (Schritt 2):
    - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Sie das Skype for Business Server-System**, und klicken Sie auf **Ausführen** bei Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten
    - Klicken Sie im Dialogfeld Skype for Business Server-Komponenten einrichten auf **weiter** .
    ![Das Fenster "Skype for Business Server-Komponenten einrichten"](../../media/set-up-skype-for-business-server-components-window.png)
    - Überprüfen Sie das Protokoll mithilfe von View Log, und überprüfen Sie, ob Setup ohne Probleme abgeschlossen wurde. 
    - Klicken Sie auf **Fertig stellen**.
10. Fahren Sie nach Bedarf mit zusätzlicher Installation und Konfiguration fort (Sie können an dieser Stelle die normalen Installationsverfahren fortsetzen).
