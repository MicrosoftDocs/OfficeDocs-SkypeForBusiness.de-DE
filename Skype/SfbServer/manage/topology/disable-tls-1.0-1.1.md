---
title: Deaktivieren Sie TLS 1.0/1.1 in Skype für Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Vorbereiten Sie und implementieren Sie in Ihren Umgebungen deaktivieren TLS 1.0 und 1.1.'
ms.openlocfilehash: dc835a68e47f9fac6036724d92ad336ead795e50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214773"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deaktivieren Sie TLS 1.0/1.1 in Skype für Business Server 2015

Der Zweck dieses Artikels ist der erforderlichen Richtlinien für die Sie zum Vorbereiten und implementieren Sie deaktivieren TLS 1.0 und 1.1 in Ihrer Umgebung bereitstellen. Dieser Prozess erfordert umfassende Planung und Vorbereitung. Lesen Sie bitte aufmerksam sämtliche Informationen in diesem Artikel, wie Sie Ihren Plan Deaktivieren von TLS 1.0 und 1.1 für Ihre Organisation vornehmen. Beachten Sie, dass es gibt viele externe Abhängigkeiten und Konnektivität Bedingungen, die durch das Deaktivieren von TLS 1.0/1.1 beeinträchtigt werden könnte, so stark planen und Testen garantiert ist.

## <a name="in-this-article"></a>In diesem Artikel

- [Hintergrund und des Umfangs](#background)
- [Erforderliche Komponenten und verarbeiten](#prerequisites-and-process)
- [Erweiterte Bereitstellungsszenarien](#advanced-deployment-scenarios)

## <a name="background"></a>Hintergrund

Die primäre Treiber für die Bereitstellung von TLS 1.0 und 1.1 Disable-Unterstützung für Skype für Business Server lokal sind Payment Card Industry (PCI) Security Standards Council und Federal Information Processing Standards (engl.). Weitere Informationen für PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft kann nicht Hilfestellung für unabhängig davon, ob Ihre Organisation erforderlich ist, diese oder anderen Vorschriften einhalten. Sie müssen ermitteln, ob es für TLS 1.0 und/oder 1.1 in Ihren Umgebungen deaktivieren erforderlich ist.

Microsoft hat ein Whitepaper über TLS verfügbaren [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)hergestellt und sollten auch im Hintergrund Lesen in diesen [Exchange-Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)verfügbar.

## <a name="supportability-scope"></a>Support-Bereich

*Bereich* bezieht sich auf unterstützt. Für Skype für Business Server lokal bedeutet, dass *im Bereich* wir vollständig unterstützen, und Deaktivieren der TLS 1.0 und 1.1 für die aufgeführten Produktversionen getestet. *Derzeit untersuchten* bedeutet, dass nur die; Wir sind aktiv untersuchen, verwenden Sie diese Produkte in den Bereich aus, für TLS-Unterstützung deaktivieren. *Außerhalb des Gültigkeitsbereichs* bedeutet, dass diese Produktversionen deaktivieren TLS 1.0 oder 1.1 nicht unterstützt und funktioniert nicht, mit Ausnahmefällen.

### <a name="fully-tested-and-supported-servers"></a>Vollständig getesteten und unterstützten Server

- Skype for Business Server 2019
- Skype für Business Server 2015 CU6 HF2 6.0.9319.516 ([update März 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) und höher auf: 
    - Windows Server 2012 (mit KB 3140245 oder vorrangiges Update), 2012 R2 oder 2016
- In-Place Upgrade Skype für Business Server 2015 mit CU6 HF2 und höher auf 
    - Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder vorrangiges Update) oder 2012 R2
- Exchange-Diensten und Outlook Web App mit RU19 von Exchange Server 2010 SP3 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) mit Skype für Business Server 2015 CU6 HF2 oder höher (Vergewissern Sie sich mit Ihrem Lieferanten, dass sie die geeignete Updates gepackt und für Ihre Anwendung zur Verfügung gestellt wurde haben)
- Survivable Branch Server (SBS) mit Skype für Business Server 2015 CU6 HF2 oder höher
- Dies ist Lync Server 2013 **Edge Rolle nur**, da edgerolle eine Abhängigkeit nicht auf Windows Fabric 1.0 verfügt.


### <a name="fully-tested-and-supported-clients"></a>Vollständig getestete und unterstützte clients

- Lync 2013 (Skype für Unternehmen) Desktopclient, MSI und C2R, einschließlich Basic [15.0.5023.1000 und höher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype für Business 2016 Desktop Client MSI [16.0.4678.1000 und höher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic
- Skype für Business 2016 klicken Sie auf Ausführen, sind die [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) -Updates erforderlich: 
    - Monatliche und Semikolons pro Jahr als Ziel, 16\.0\.9126\.2152 und höher
    - Semikolons jährlichen und zurückgestellt Kanal, 16\.0\.8431\.2242 und höher
- Skype für Unternehmen auf Mac 16.15 und höher
- Skype für geschäftliche für iOS und Android 6.19 und höher
- Skype Web App 2015 CU6 HF2 und höher (im Lieferumfang von Server)

### <a name="currently-being-investigated"></a>Derzeit untersuchten

#### <a name="devices"></a>Geräte

- Lync-Chatroom-System (auch bekannt als SRSv1)
- Microsoft Teams-Räume
- Surface Hub
- 2015 basieren Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)

#### <a name="other"></a>Andere

- Rufen Sie Quality Dashboard (neue Installation nach TLS 1.0, 1.1 deaktiviert wurden, finden Sie weiter unten) *
 
### <a name="out-of-scope"></a>Außerhalb des Gültigkeitsbereichs

Wenn nicht anders angegeben die folgenden Produkte sind nicht im Gültigkeitsbereich für die Unterstützung für TLS 1.0/1.1 deaktivieren und funktioniert nicht in einer Umgebung, in dem TLS 1.0 und 1.1 deaktiviert wurden.  Dies bedeutet: Wenn Sie dennoch außerhalb des Bereichs Servern oder Clients nutzen, müssen Sie aktualisieren oder entfernen Sie diese Option, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrem Skype für Business Server-Bereitstellung lokal nicht deaktiviert werden müssen.

- Lync Server 2013
- Lync Server 2010
- WindowsServer 2008 als auch eine untere
- Lync für Mac 2011
- Lync 2013 für Mobile - iOS, iPad, Android oder Windows Phone
- Lync "MX" Windows Store-client
- Alle Lync 2010-clients
- Lync Phone Edition - aktualisierter Leitfaden [hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)
- Cloud-Connector-Edition (CCE)
- Microsoft Skype for Business für Windows Phone

### <a name="exceptions"></a>Ausnahmen

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 übernimmt eine Abhängigkeit Windows Fabric Version 1.0.  In der Phase Design für Lync Server 2013 wurde gewählt, Windows Fabric 1.0 für die überzeugender und neue verteilte Architektur Replikation, hohe Verfügbarkeit und Fehlertoleranz bereitstellen.  Im Laufe der Zeit beide Skype für Business Server und Windows Fabric haben erheblich verbessert diese gemeinsame Architektur mit erhebliche überarbeiten in späteren Versionen.  Aktuelle Skype für Business 2015 Server wird Windows Fabric 3.0, beispielsweise verwendet.

Windows Fabric 1.0 **unterstützt TLS 1.2 leider nicht.  Jedoch empfohlen wird werden Aktualisieren von Lync Server 2013 TLS 1.2 entwickelt**. Dadurch wird das nächste kumulative Update für Lync Server 2013 stammen.  Wir bieten immer noch die Unterstützung für TLS 1.2 Koexistenz, Migration, Verbund- und hybridkonfiguration Szenarien zu ermöglichen.

Wenn Ihre Organisation Deaktivieren von TLS 1.0 und 1.1 erforderlich ist und Sie zurzeit Lync Server 2013 verwenden, empfehlen wir Sie beim Planen beginnen, mit der Möglichkeit möglicherweise müssen Sie bei direkten Upgrades oder Side-by-Side migrieren (neuen Pools, Benutzer verschieben) zu Skype für Business Server 2015 oder höher.  Oder Sie möchten die Beschleunigung der Migration auf Skype für Business Online.

#### <a name="call-quality-dashboard"></a>Anrufqualitäts-Dashboard

Lokale aufrufen Qualitätsdashboard ist derzeit abhängig von TLS 1.0 während der Neuinstallation (erstmalig in Ihrer lokalen Umgebung installieren).  Wir sind zurzeit untersucht dieses Problem und ein Update in naher Zukunft freigeben möchten.  Wenn Sie beabsichtigen, installieren CQD und TLS 1.0 auch deaktivieren, wird empfohlen, dass Sie zuerst CQD-Installation abgeschlossen, und fahren mit TLS 1.0 zu deaktivieren.

#### <a name="third-party-devices"></a>Drittanbieter-Geräte

Auf Geräten von Drittanbietern wie 3PIP Telefone unbedingt-Video-Konferenzen Reverseproxys und zum Lastenausgleich, TLS 1.2 Supportability überprüfen und sorgfältig getestet und Kontaktaufnahme mit dem Hersteller bei Bedarf.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Verbund-Überlegungen beim Deaktivieren von TLS 1.0/1.1 auf Edge-Servern

Sie müssen sorgfältig planen und berücksichtigen die Auswirkungen der TLS 1.0/1.1 auf Edge-Servern deaktivieren.  Sobald TLS 1.0 und 1.1 deaktiviert sind, können Sie feststellen, dass anderen Organisationen sind nicht mehr in der Lage, Verbund mit Ihrer Organisation.

Sie können entscheiden, wenn Sie TLS 1.0/1.1 auf Edge-Servern zum Aufrechterhalten der Abwärtskompatibilität mit nicht gepatcht (SfB 2015, Lync 2013) aktiviert oder externen Systemen mit älteren (2010).

Microsoft kann nicht Rat oder Recommendations angeben, auf unabhängig davon, ob Ihr Netzwerk Edge (oder jedes Netzwerk) unter PCI-Standards liegt. muss von der einzelnen Unternehmen bestimmt werden.

Skype für Business Online kann TLS 1.2 heute, sodass keine Auswirkung auf Hybrid/Verbund mit Online erwartet wird.

PIC (Public IM Connectivity) mit Skype Consumer-Dienst: wir davon ausgehen, dass TLS 1.0/1.1 um [Skype-Konnektivität](../../deploy/deploy-skype-connectivity.md); beeinträchtigen deaktivieren Microsoft PIC-Gateways sind bereits TLS 1.2 werden können.

## <a name="prerequisites-and-process"></a>Erforderliche Komponenten und verarbeiten

Außer oben nicht anders angegeben, einmal TLS 1.0 und 1.1 deaktivierte außerhalb des Bereichs Server sind, funktionieren Clients und Geräten ordnungsgemäß oder überhaupt mehr. Dies kann bedeuten, dass müssen Sie unterbrechen, und warten Sie aktualisierter Leitfaden von Microsoft. Nachdem Sie sind davon überzeugt, dass Anforderungen entsprechen und ein Plans zum Adresse Lücken haben, fahren Sie fort.

Auf allgemeiner Ebene während Skype für Business Server 2019 für Verfahren bei der Installation bereit ist erforderlich Skype für Business Server 2015, dass Sie CU6 HF2, Anwenden von Updates für vorausgesetzte .NET und SQL, Bereitstellung von erforderlichen Registrierungsschlüssel und schließlich eine Separate installieren Roundrobin der OS-Konfiguration (d. h. deaktivieren TLS 1.0 und 1.1 über den Registrierungs-Dateiimport) aktualisiert. Es ist von entscheidender Bedeutung, dass Sie alle erforderlichen Komponenten, einschließlich Skype für Business Server 2015 CU6 HF2 deaktivieren TLS 1.0 und 1.1 auf allen Servern in Ihrer Umgebung vor der Installation abgeschlossen. Jeder Skype für Business Server, einschließlich Edge-Rolle und SQL-Back-Ends, erfordert die Updates. Außerdem sicherstellen Sie, dass alle unterstützten (im Gültigkeitsbereich)-Clients, die mindestens erforderlichen Versionen aktualisiert wurden. Vergessen Sie nicht, Verwaltungscomputer sowie zu aktualisieren.

Wir möchten die übliche Reihenfolge der Vorgänge von "innen nach außen" führen für das Upgrade von Skype für Unternehmensserver. Behandeln von Director-Pools, Persistent Chat und gepaart Pools in die gleiche Weise wie gewohnt verwenden. Reihenfolge und Methoden für das Upgrade fallen [hier](topology.md) und [hier](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Allgemeine Prozess

1. Testen Sie alle Schritte im Lab vor dem Konfigurieren von Produktionsservern.
2. Sichern Sie und bewahren Sie eine Kopie der exportierten Registrierung auf jedem einzelnen Server aktualisiert werden. Registrierung zwischen Servern kann nicht freigegeben werden. Sie enthalten eindeutige computerbasierte Schlüssel.
3. Aktualisieren Sie alle Skype für 2015 Business Server, auf CU6 HF2 oder höher. (Für Skype für Business Server 2019, ist keine CU erforderlich)
4. Installieren Sie alle erforderlichen Komponenten auf allen Servern.
5. Bereitstellen von erforderlichen Registrierungsschlüssel.
6. Stellen Sie sicher, dass alle im Gültigkeitsbereich Clients aktualisiert werden.
7. Deaktivieren Sie TLS 1.0 und 1.1 über Registrierung importieren.
8. Überprüfen Sie, dass Arbeitslasten wie erwartet funktionieren.
    - Wenn Probleme auftreten, zu beheben, oder
    - Wiederherstellen der Registrierung aus Schritt 2 zum erneuten Aktivieren von TLS 1.0 und 1.1
9. Überprüfen Sie, dass nur TLS 1.2 verwendet wird.

### <a name="install-prerequisites-to-all-servers"></a>Installieren der erforderlichen Komponenten auf allen Servern

Umfassende Abhängigkeit aktualisieren ist erforderlich, bevor Sie beginnen, TLS 1.0 und 1.1 auf Betriebssystemebene in Ihrer Skype für Business Server 2015 Bereitstellungen zu deaktivieren. Im folgenden werden die minimalen Versionen, die TLS 1.2 unterstützen können. Stellen Sie alle erforderlichen Updates über jede Skype für Business Server in Ihrer Umgebung bereit, bevor Sie beginnen, deaktivieren TLS 1.0 und 1.1.

- Skype für Business Server 2015 CU6 HF2 6.0.9319.516 ([update März 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) oder höher
- [.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) oder höher mit SchUseStrongCrypto aktiviert in der Registrierung (siehe unten)
- SQL muss auf allen Skype für Business 2015-Server und -Back-Ends aktualisiert werden. Aktualisieren Sie Enterprise Edition-Pool SQL-Back-Ends zuerst, klicken Sie dann ihre jeweiligen FEs. 
    - SQL Server 2014 SP1 + CU5 ([Link](https://support.microsoft.com/help/3130926)) oder höher / SQL Server 2012 SP2 + CU16 oder höher / RTM-Version von SQL Server 2014 + CU12 ([Link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) oder höher / SQL Server 2014 SP2
    - SQL Server Native Client für SQL Server 2012 ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Microsoft ODBC-Treiber 11 für SQL Server ([Link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) oder höher
    - Gemeinsame Management Objects für SQL Server 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes für SQLServer 2014 SP2 ([Link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Grundlegende Schritte zum Installieren der erforderlichen Komponenten in empfohlene Reihenfolge der Vorgänge

1. Installieren Sie die Skype für Business Server CU6HF2 (6.0.9319.516) auf allen Servern zu aktualisieren. 
    1. Installieren des Updates und den Updater-Komponenten.
    2. Aktualisieren von Datenbanken entsprechend dokumentierte Verfahren. Anweisungen sind unter dokumentiert [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Produktfunktionen in der Bereitstellung, bevor Sie mit anderen Änderungen zu überprüfen.
2. Laden Sie .NET 4.7 Offline Installer. 
    1. Referenz:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Stellen Sie sicher, dass Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden.
    3. Referenz:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): Stop – CsWindowsServices
    5. Ex (Enterprise Edition): Aufruf-CsComputerFailover
    6. Führen Sie das Installer-Paket.
    7. Starten Sie den Server neu.
3. Aktualisieren Sie SQL Express 2014 auf allen Servern. 
    1. Referenz:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2 herunterladen 
        - Referenz:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Kopieren Sie die Installationsmedien in einen Ordner auf dem Server (Ex: C:\01_2014SqlSp2)
    4. Sicherstellen von Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Aufruf-CsComputerFailove
    5. Öffnen Sie ein Eingabeaufforderungsfenster Admin, und aktualisieren Sie alle installierten Komponenten und Instanzen 
        - Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch allinstances
4. Aktualisieren Sie SQL Native Client. 
    1. Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Laden Sie aus[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Stellen Sie sicher Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden. 
        - Ex (Standard Edition): Stop – CsWindowsServices
        - Ex (Enterprise Edition): Aufruf-CsComputerFailove
    4. Beenden Sie die Ausführung von installierten SQL-Instanzen 
        - Beispiel: Get-Service "MSSQL$ RTCLOCAL" | STOP-Dienst
        - Beispiel: Get-Service 'MSSQL$ LYNCLOCAL' | STOP-Dienst
        - Ex (nur Standard Edition): Get-Service "MSSQL$ RTC" | STOP-Dienst
    5. Installieren Sie das Update.
5. ODBC-Treiber 11 für SQLServer zu aktualisieren. 
    1. Referenz: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Laden Sie aus[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Stellen Sie sicher, dass Skype für Business Server 2015 Dienste auf dem Front-End-Server beendet werden 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Aufruf-CsComputerFailove
    4. Installieren Sie das Update.
6. Bereitstellen von erforderlichen Registrierungsschlüssel.

### <a name="pre-requisite-registry-keys"></a>Vorausgesetzte Registrierungsschlüssel

Kopieren und Einfügen den folgenden Test in Notepad ein umbenennen Sie TLSPreReq.reg oder einen Namen Ihrer Wahl, und importieren:

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

Für SQL sollten Back zu deaktivierende enden für Enterprise Edition-Pools, erforderliche Komponenten und TLS wie SQL oder OS Updates behandelt werden. finden Sie unter:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Während der erforderlichen Anwendung und die Schritte deaktivieren TLS kombiniert werden können, empfehlen wir dringend, alle erforderlichen Komponenten vor dem Fortfahren mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene angewendet werden. Der beste Practice Ansatz wäre die Umgebung vorbereiten, indem Sie alle erforderlichen Komponenten, überprüfen, dass alle Arbeitslasten ordnungsgemäß und wie erwartet funktionieren und Fortfahren mit TLS 1.0/1.1 deaktivieren Sie dann zu einem späteren Zeitpunkt bereitstellen.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deaktivieren von TLS 1.0 und 1.1 über Registrierung importieren

Vor dem Fortfahren Sie mit den nächsten Schritten, *Stellen Sie sicher, dass Sie alle erforderlichen Komponenten abgeschlossen und Skype für Unternehmensserver aktualisiert haben*.

Kopieren Sie den folgenden Text in eine Editor-Datei, und benennen Sie sie **TLSDisable.reg**:

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

Importieren Sie die REG-Datei auf jedem Server, die Sie TLS 1.0 deaktivieren möchten und 1.1. Starten Sie den Server neu. Sobald die Dienste wieder online geschaltet haben, fahren Sie mit den nächsten Server. Die Vorgehensweise für Enterprise Edition-Pools ist identisch, die Sie für jedes Update OS ausführen würden.

Sie haben möglicherweise bemerkt, dass wir mehr als einfach zu deaktivieren, TLS 1.0 und 1.1 hier machen. Wir sind Chiffre-Suite neu anordnen (siehe oben) und das Deaktivieren der einige ältere schwache Chiffre unterstützen. Hierbei handelt es sich beim ersten wir diese Änderungen SCHANNEL und Kryptografie-API auf Skype offiziell für Business Server unterstützt haben, und es ist wichtig, beachten Sie, dass diese Änderungen nur sind, die wir unterstützen und zu diesem Zeitpunkt getestet. Wir sollten weitere Konfigurationen in der Zukunft, aber jetzt darf nicht geändert werden in der Implementierung die Registrierung-Importdatei.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Überprüfen Sie, dass Arbeitslasten wie erwartet funktionieren

Nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert haben, stellen Sie sicher, dass alle Ihre wichtigsten Arbeitslasten wie erwartet funktionieren, beispielsweise Sofortnachrichten & Anwesenheit, P2P-Aufrufe, Enterprise-VoIP, usw..

**Überprüfen Sie nur TLS 1.2 verwendet wird**

Haben Sie Ihre Security Team führen Sie eine neue Überwachung Skype für Business-Datenverkehr, um sicherzustellen, dass das ältere TLS 1.0 Protokolle und 1.1 nicht mehr verwendet werden.

Alternativ können Sie Internet Explorer verwenden, TLS-Verbindungen an Webdienste von Skype für Business Server 2015 nach getestet TLS 1.0 und TLS 1.1 deaktiviert wurden.

1. Starten Sie Internet Explorer.
2. Wählen Sie **Extras** > **Internetoptionen**.
3. Wählen Sie die Registerkarte **Erweitert** .
4. Klicken Sie unter **Einstellungen**führen Sie einen Bildlauf nach unten.
5. Stellen Sie sicher, dass TLS 1.0, TLS 1.1 und TLS 1.2 aktiviert sind.
6. Durchsuchen Sie den internen Webdienst-URL des Pools SfB 2015 (sollte erfolgreich eine Verbindung herstellen).
7. Wechseln Sie wieder in den Internet Explorer, und deaktivieren Sie nur die Option zur **Verwendung von TLS 1.2** .
8. Durchsuchen Sie den internen Webdienst-URL des SfB 2015 Pools erneut (sollte fehlschlagen Verbindung).

![Internetoptionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Erweiterte Bereitstellungsszenarien

Da einige Abhängigkeit erforderliche Komponenten zur Unterstützung von TLS 1.2 in Skype für Business Server 2015 erforderlich sind, fehl aus der RTM-Medien installieren auf einem beliebigen System, auf dem TLS 1.0 und 1.1 deaktiviert wurden.

**Bereitstellen von neuen Standard Edition-Server oder Enterprise Edition-Pools, sobald TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert sind.**

**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Beachten Sie, dass wir die aktualisierten SQL-Binärdateien in einer zukünftigen CU zur Erfüllung SmartSetup aktualisieren, und in diesem Artikel werden in der Zukunft aktualisiert.

**Option 2:** Vor der Installation lokalen SQL Server-Instanzen (RTCLOCAL und LYNCLOCAL)

1. Laden und SQL Express 2014 SP2 (SQLEXPR_x64.exe) in lokalen Ordner auf FE kopieren. Nehmen wir an Ordner Pfad <SQL_FOLDER_PATH>.
2. Starten Sie PowerShell oder im Eingabeaufforderungsfenster, und navigieren Sie zu <SQL_FOLDER_PATH>.
3. Erstellen Sie durch Ausführen des folgenden Befehls die RTCLOCAL-SQL-Instanz. Warten, bis SQLEXPR_x64.exe beendet, bevor Sie fortfahren ist:

    SQLEXPR_x64.exe/q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Installation/Funktionen = SQLEngine, Tools/InstanceName = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT-Autorität\Netzwerkdienst" /SQLSYSADMINACCOUNTS = "Builtin\ Administrators"/BROWSERSVCSTARTUPTYPE ="Automatisch"/AGTSVCACCOUNT ="NT-AUTORITÄT\NetworkService"/SQLSVCSTARTUPTYPE = Automatis
1. Erstellen Sie durch Ausführen des folgenden Befehls die LYNCLOCAL SQL-Instanz. Warten, bis SQLEXPR_x64.exe beendet, bevor Sie mit dem nächsten Schritt fortfahren ist:

    SQLEXPR_x64.exe/q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Installation/Funktionen = SQLEngine, Tools/InstanceName = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT-Autorität\Netzwerkdienst" /SQLSYSADMINACCOUNTS = "Builtin\ Administrators"/BROWSERSVCSTARTUPTYPE ="Automatisch"/AGTSVCACCOUNT ="NT-AUTORITÄT\NetworkService"/SQLSVCSTARTUPTYPE = automatische
1. Skype für Business Server 2015 RTM Setup ausführen.
2. Führen Sie die restlichen Schritte vom Abschnitt erforderlichen Komponenten.

**Option 3:** Sie können auch manuell Binärdateien in einer lokalen Installationsverzeichnis Medien wie folgt ersetzen:

1. [Installieren der erforderlichen Komponenten für Skype für Business Server](../../deploy/install/install-prerequisites.md)  
2. 2. Installieren von .NET 4.7: 
      - **Hinweis:** Wir zunächst wird die Unterstützung für .NET 4.7 in Skype für Business Server 2015 CU5 oder höher (6.0.9319.281) eingeführt. Aus diesem Grund wird in den späteren Schritten unten wir Hauptkomponenten vor der Installation Hauptfenster aktualisieren.
      - Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Referenz: [Software, die vor einem Skype für Business Server 2015 Bereitstellung installiert werden muss](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Kopieren Sie die ISO-Dateien/Ordner: 
    - Mit der Skype für Business Server 2015 ISO zugeordnet ist, öffnen Sie das Stammverzeichnis des Laufwerks, wird es als angefügt (Ex: D:\) im Datei-Explorer.
    - Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (Ex: C:\SkypeForBusiness2015ISO).
    - **Hinweis:** Einige Dateien müssen vor dem Installieren von Komponenten aus, für die Unterstützung von TLS 1.2 aktualisiert werden.
4. Ersetzen Sie die MSI-EXE-Pakete: 
    - Ersetzen Sie die vorhandenen Pakete MSI und EXE-Datei im Ordner "/ Setup/amd64 /" des Installationsmediums auf dem lokalen Computer.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Benennen Sie auf dem lokalen Computer SQLEXPR_x64, und Ersetzen Sie die vorhandene Datei in das Setup/amd64/Ordner der-Installationsmedien.
    - SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Hinweis:** Benennen Sie dies bei Bedarf sqlncli.msi, und klicken Sie dann ersetzen die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.
    - SQL Management Objects:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack müssen viele Elemente, die heruntergeladen werden können. Wählen Sie nur SharedManagementObjects.msi herunterladen.
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.
    - SQL-CLR-Typen:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack müssen viele Elemente, die heruntergeladen werden können. Wählen Sie nur CQLSysClrTypes.msi herunterladen
        - **Hinweis**: Ersetzen Sie die vorhandene Datei, die in der Setup/amd64 vorhanden ist/Ordner der-Installationsmedien.
5. Installieren Sie die Hauptkomponenten: 
    - Führen Sie Setup.exe von der Setup/amd64/Ordner der-Installationsmedien. Führen Sie die Anweisungen, um die Hauptkomponenten installieren
    - Hauptkomponenten zu schließen.
6. Aktualisieren Sie die Hauptkomponenten: 
    - Laden Sie die Skype für Business Update-Installationsprogramm.
    - Führen Sie das Installationsprogramm, um die Hauptkomponenten zu aktualisieren, und installieren die Leistungsindikatoren.
    - **Hinweis:** Die Version von CU6HF2 wird das Feature für automatische Updates derzeit nur bis CU6 zu installieren. Aus diesem Grund muss der Updater separat ausgeführt werden, um Hauptkomponenten auf 6.0.9319.516 zu aktualisieren.
    - Referenz:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Installieren der Verwaltungstools (Optional): 
    - Hiermit wird die Microsoft SQL Server 2012 Native Client sowie SQL Server 2014 Management Objects (x64) und Microsoft System CLR-Typen für SQL Server 2014 (x64) verwenden die aktualisierten Dateien installiert. Darüber hinaus wird der Skype für Business Server 2015 Topologie-Generator und der Systemsteuerung auf dem lokalen Computer verfügbar sein.
8. Lokalen Konfigurationsspeicher installieren (Schritt 1): 
     - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Installieren oder aktualisieren Skype für Business Server-System und klicken Sie auf **Ausführen** , in Schritt 1: lokalen Konfigurationsspeicher installieren.
     - Klicken Sie auf **Weiter** im Dialogfeld **Lokalen Konfigurationsspeicher installieren** .
     ![Dialogfeld lokalen Konfigurationsspeicher installieren](../../media/local-configuration-store.png)
     - Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Status der Aufgabe abgeschlossen ist. Überprüfen Sie die daraus resultierende Protokolldatei durch Klicken auf **Protokoll anzeigen**.
     ![Aufgabenstatus wird als abgeschlossen](../../media/local-configuration-task-completed.png)
     - Klicken Sie auf **Fertig stellen**.
9. Einrichten oder Entfernen von Skype für Business Server-Komponenten (Schritt2):
    - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**und klicken Sie auf **Ausführen** , um Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten
    - Klicken Sie auf **nächste** in das Festlegen von Skype für Business Server-Komponenten (Dialogfeld).
    ![Das Festlegen von Skype für Fenster Business Server-Komponenten](../../media/set-up-skype-for-business-server-components-window.png)
    - Überprüfen Sie die melden Sie sich mit Protokoll anzeigen, und Überprüfen von Setup ohne Probleme abgeschlossen. 
    - Klicken Sie auf **Fertig stellen**.
10. Zusätzliche Installation und Konfiguration nach Bedarf fort (Sie können fortsetzen normalen Installationsverfahren zu diesem Zeitpunkt).
