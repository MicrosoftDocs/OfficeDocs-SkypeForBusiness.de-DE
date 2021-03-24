---
title: Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015
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
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Vorbereiten und Implementieren der Deaktivierung von TLS 1.0 und 1.1 in Ihren Umgebungen.
ms.openlocfilehash: b07b9b5319b858a20a8073de8c6a37dd4d3299ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103211"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015

Dieser Artikel hilft Ihnen bei der Vorbereitung und Implementierung der Deaktivierung von TLS 1.0 und 1.1 in Ihren Umgebungen. Dieser Prozess erfordert eine umfassende Planung und Vorbereitung. Überprüfen Sie sorgfältig alle Informationen in diesem Artikel, während Sie Ihren Plan für die Deaktivierung von TLS 1.0 und 1.1 für Ihre Organisation erstellen. Es gibt viele externe Abhängigkeiten und Konnektivitätsbedingungen, die durch die Deaktivierung von TLS 1.0/1.1 betroffen sein könnten, sodass umfangreiche Planung und Tests gerechtfertigt sind.

- [Hintergrund und Bereich](#background-and-scope)
- [Voraussetzungen und Prozess](#prerequisites-and-process)
- [Erweiterte Bereitstellungsszenarien](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Hintergrund und Bereich

Die wichtigsten Treiber für die Bereitstellung von TLS 1.0 und 1.1 deaktivieren die Unterstützung für die lokale Skype for Business Server-Unterstützung: Payment Card Industry (PCI) Security Standards Council und Federal Information Processing Standards Requirements. Weitere Informationen zu PCI-Anforderungen finden Sie [hier](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft kann keine Anleitungen dazu bereitstellen, ob Ihre Organisation diese oder andere Anforderungen erfüllen muss. Sie müssen ermitteln, ob es erforderlich ist, TLS 1.0 und/oder 1.1 in Ihren Umgebungen zu deaktivieren.

Microsoft hat ein Whitepaper zu TLS [erstellt,](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)das hier verfügbar ist, und wir empfehlen auch die Hintergrundleseinformationen, die in diesem [Exchange-Blog verfügbar sind.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)

## <a name="supportability-scope"></a>Supportability Scope

*Bereich* bezieht sich auf Unterstützungsgrenzen. *Vollständig getestet und unterstützt* bedeutet, dass wir die Deaktivierung von TLS 1.0 und 1.1 für die aufgeführten Produktversionen vollständig unterstützen und getestet haben. *Derzeit wird genau* das untersucht. Wir untersuchen aktiv, diese Produkte in den Bereich der TLS-Deaktivierungsunterstützung zu bringen. *"Out of scope"* bedeutet, dass diese Produktversionen die Deaktivierung von TLS 1.0 oder 1.1 nicht unterstützen und mit den erwähnten Ausnahmen nicht funktionieren.

### <a name="fully-tested-and-supported-servers"></a>Vollständig getestete und unterstützte Server

- Skype for Business Server 2019 CU1 17.0.2046.123 (Juni 2019) oder höher
- Skype for Business Server 2015 CU9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder aktualisierungsergeding), 2012 R2 oder 2016.
- In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update) or 2012 R2.
- Exchange Connectivity und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder höher, Anleitung [hier](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 HF2 oder höher (vergewissern Sie sich bei Ihrem Anbieter, dass sie die entsprechenden Updates verpackt haben und für Ihre Appliance verfügbar gemacht wurden)
- Survivable Branch Server (SBS) mit Skype for Business Server 2015 CU6 HF2 oder höher
- Lync Server 2013 **Edge Role Only**, dies liegt daran, dass die Edgerolle keine Abhängigkeit von Windows Fabric 1.0 hat.

### <a name="fully-tested-and-supported-clients"></a>Vollständig getestete und unterstützte Clients

- Lync 2013 (Skype for Business) Desktop Client, MSI und C2R, einschließlich Basic [15.0.5023.1000 oder höher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 oder höher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), einschließlich Basic
- Skype for Business 2016 Klicken Sie zum Ausführen die [Updates vom April 2018](/officeupdates/release-notes-office365-proplus) erforderlich: 
    - Monatlich und Semi-Annual, 16 \. 0 \. 9126 \. 2152 oder höher
    - Semi-Annual und verzögerter Kanal, 16 \. 0 \. 8431 \. 2242 oder höher
- Skype for Business auf Mac 16.15 oder höher
- Skype for Business für iOS und Android 6.19 oder höher
- Microsoft Teams Rooms (früher als Skype Room System V2 SRS V2 bezeichnet) 4.0.64.0 (Dezember 2018) oder höher
- Surface Hub-Update für Team Edition basierend auf KB4499162 (Mai 2019, Os Build 15063.1835) oder höher
- Skype Web App 2015 CU6 HF2 oder höher (wird mit Server versendet)

### <a name="currently-being-investigated"></a>Derzeit untersucht

- Anrufqualitätsdashboard (neu installieren, nachdem TLS 1.0, 1.1 deaktiviert wurde, siehe unten)*
 
### <a name="out-of-scope"></a>Nicht inbegriffen

Sofern nicht erwähnt, sind die folgenden Produkte für TLS 1.0/1.1 nicht geeignet und funktionieren nicht in einer Umgebung, in der TLS 1.0 und 1.1 deaktiviert wurden. Was dies bedeutet: Wenn Sie weiterhin server- oder clientferne Server oder Clients verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrer lokalen Skype for Business Server-Bereitstellung deaktivieren müssen.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 oder niedriger
- Lync für Mac 2011
- Lync 2013 für Mobile – iOS, iPad, Android oder Windows Phone
- Lync "MX"-Windows Store-Client
- Lync Room System (a.k.a. SRSv1). LRS hat am 9. Oktober 2018 das Ende der Unterstützung erreicht und wird nicht auf TLS 1.2 aktualisiert.
- Alle Lync 2010-Clients
- Lync Phone Edition – aktualisierte Anleitung [hier](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013-basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Skype for Business for Windows Phone

### <a name="exceptions"></a>Ausnahmen

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 ist abhängig von Windows Fabric, Version 1.0.  In der Entwurfsphase für Lync Server 2013 wurde Windows Fabric 1.0 für seine überzeugende und neue verteilte Architektur ausgewählt, um Replikation, hohe Verfügbarkeit und Fehlertoleranz zu gewährleisten.  Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur mit einer erheblichen Neugestaltung in nachfolgenden Versionen erheblich verbessert.  Aktueller Skype for Business 2015 Server verwendet beispielsweise Windows Fabric 3.0.

Leider unterstützt Windows Fabric 1.0 **TLS 1.2 nicht.  Wir aktualisieren Lync Server 2013 jedoch so, dass es mit TLS 1.2 funktioniert.** Dies wird im nächsten kumulativen Update für Lync Server 2013 angezeigt.  Wir bieten TLS 1.2-Unterstützung, um Koexistenz-, Migrations-, Verbund- und Hybridszenarien zu ermöglichen.

Wenn Ihre Organisation TLS 1.0 und 1.1 deaktivieren muss und Sie derzeit Lync Server 2013 verwenden, wird empfohlen, mit dem Planungsprozess zu beginnen, mit der Möglichkeit, dass Sie möglicherweise ein In-Place-Upgrade oder eine side-by-Side-Migration (neue Pools, Verschieben von Benutzern) zu Skype for Business Server 2015 oder höher durchführen müssen.  Oder Sie möchten die Migration zu Skype for Business Online beschleunigen.

#### <a name="call-quality-dashboard"></a>Dashboard für Anrufqualität

Das Lokale Anrufqualitätsdashboard ist derzeit während der Neuinstallation von TLS 1.0 abhängig (bei der ersten Installation in Ihren lokalen Umgebungen).  Wir untersuchen derzeit dieses Problem und planen, in naher Zukunft eine Lösung zu veröffentlichen.  Wenn Sie planen, CQD zu installieren und auch TLS 1.0 zu deaktivieren, wird empfohlen, zuerst die CQD-Installation abzuschließen und dann mit der TLS 1.0-Deaktivierung fortzufahren.

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN Manager

Skype for Business SDN Manager, SQL eine Datenbank verwendet, ist während der neu installierten Installation von TLS 1.0 abhängig. Wenn Sie planen, Skype for Business SDN Manager mit SQL einer Datenbank zu installieren und auch TLS 1.0 zu deaktivieren, wird empfohlen, zuerst Skype for Business SDN Manager zu schließen und dann mit der TLS 1.0-Deaktivierung fortzufahren. Falls TLS 1.0 vor der Installation deaktiviert wurde, sollten Sie TLS 1.0 vorübergehend wieder im SQL Server-Back-End-Server aktivieren, der zum Hosten der Skype for Business SDN Manager-SQL-Datenbank verwendet wird.

#### <a name="third-party-devices"></a>Geräte von Drittanbietern

Überprüfen Sie auf Geräten von Drittanbietern wie 3PIP-Telefonen, Videokonferenzen, Reverseproxys und Lastenausgleichsgeräten die TLS 1.2-Unterstützung, testen Sie sorgfältig und wenden Sie sich bei Bedarf an den Anbieter.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Überlegungen zum Verbund beim Deaktivieren von TLS 1.0/1.1 auf Edgeservern

Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihren Edgeservern sorgfältig planen und berücksichtigen.  Sobald TLS 1.0 und 1.1 deaktiviert sind, stellen Sie möglicherweise fest, dass andere Organisationen nicht mehr in der Lage sind, einen Verbund mit Ihrer Organisation zu erstellen.

Sie können TLS 1.0/1.1 auf Ihren Edgeservern aktiviert lassen, um die Abwärtskompatibilität mit nicht gepatchten (SfB 2015, Lync 2013) oder älteren externen Systemen (2010) auf dem Server zu gewährleisten.

Microsoft kann keine Ratschläge oder Empfehlungen dazu geben, ob Ihr Edgenetzwerk (oder ein Netzwerk) unter den PCI-Standard fällt. das vom einzelnen Unternehmen bestimmt werden muss.

Skype for Business Online ist heute in der Lage, TLS 1.2 zu verwenden, sodass keine Auswirkungen auf Hybrid/Verbund mit Online erwartet werden.

PIC (Public IM Connectivity) zu Skype Consumer Service: Wir erwarten nicht, dass die Deaktivierung von TLS 1.0/1.1 Auswirkungen auf [die Skype-Konnektivität hat;](../../deploy/deploy-skype-connectivity.md) Microsoft PIC-Gateways sind bereits TLS 1.2-fähig.

## <a name="prerequisites-and-process"></a>Voraussetzungen und Prozess

Wenn TLS 1.0 und 1.1 außer den oben erwähnten Nicht-Bereichs-Servern deaktiviert sind, funktionieren Clients und Geräte länger oder gar nicht mehr ordnungsgemäß. Dies kann bedeuten, dass Sie anhalten und auf aktualisierte Anleitungen von Microsoft warten müssen. Sobald Sie sich sicher sind, dass Sie alle Anforderungen erfüllen und einen Plan zum Beseitigen von Lücken haben, fahren Sie fort.

Auf hoher Ebene erfordert Skype for Business Server 2015, dass Sie CU9 installieren, erforderliche Updates auf .NET und SQL anwenden, erforderliche Registrierungsschlüssel bereitstellen und schließlich eine separate Runde von Betriebssystemkonfigurationsupdates (d. h. Deaktivieren von TLS 1.0 und 1.1 über den Registrierungsdateiimport). Es ist von entscheidender Bedeutung, dass Sie die Installation aller erforderlichen Komponenten, einschließlich Skype for Business Server 2015 CU6 HF2, abschließen, bevor Sie TLS 1.0 und 1.1 auf einem Beliebigen Server in Ihrer Umgebung deaktivieren. Für jeden Skype for Business-Server, einschließlich edge role und SQL Back-Ends, sind die Updates erforderlich. Stellen Sie außerdem sicher, dass alle unterstützten (Bereichs-)Clients auf die erforderlichen Mindestversionen aktualisiert wurden. Vergessen Sie nicht, auch Verwaltungsarbeitsstationen zu aktualisieren.

Wir möchten die übliche Reihenfolge der Vorgänge "inside out" für das Upgrade von Skype for Business-Servern befolgen. Behandeln Sie Directorpools, beständigen Chat und Gekoppelte Pools auf die gleiche Weise wie normalerweise. Die Reihenfolge und Methoden für das Upgrade werden [hier](topology.md) und [hier behandelt.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>Prozess auf hoher Ebene

1. Testen Sie alle Schritte in Ihrer Übungseinheit, bevor Sie Produktionsserver konfigurieren.
2. Sichern und Beibehalten einer Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll. Registrierungsstellen können nicht zwischen Servern gemeinsam verwendet werden. sie enthalten eindeutige computerbasierte Schlüssel.
3. Aktualisieren Sie alle Skype for Business 2015-Server auf CU9 oder höher. Aktualisieren Sie für Skype for Business Server 2019 auf CU1 oder höher.
4. Installieren Sie alle erforderlichen Komponenten auf allen Servern.
5. Bereitstellen der erforderlichen Registrierungsschlüssel.
6. Stellen Sie sicher, dass alle In-Scope-Clients aktualisiert werden.
7. Deaktivieren Sie TLS 1.0 und 1.1 über den Registrierungsimport.
8. Überprüfen Sie, ob Arbeitsauslastungen wie erwartet funktionieren.
    - Wenn Probleme auftreten, Behandeln und Beheben von Problemen oder
    - Wiederherstellen der Registrierung aus Schritt 2 zur erneuten Aktivierung von TLS 1.0 und 1.1
9. Überprüfen Sie, ob nur TLS 1.2 verwendet wird.

### <a name="install-prerequisites-to-all-servers"></a>Installieren der erforderlichen Komponenten auf allen Servern

Eine umfassende Abhängigkeitsaktualisierung ist erforderlich, bevor Sie mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen. Es folgen die Mindestversionen, die TLS 1.2 unterstützen können. Stellen Sie alle erforderlichen Updates auf jedem Skype for Business-Server in Ihrer Umgebung zur Verfügung, bevor Sie mit der Deaktivierung von TLS 1.0 und 1.1 beginnen.

- Skype for Business Server 2015 CU9 6.0.9319.548 (Mai 2019) oder höher
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) oder höher, wenn SchUseStrongCrypto in der Registrierung aktiviert ist (siehe unten)
- SQL müssen auf allen Skype for Business 2015-Servern und -Back-Ends aktualisiert werden. Aktualisieren Sie zuerst SQL Enterprise Edition Pool und dann die entsprechenden FEs. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)oder höher / SQL Server 2012 SP2 + CU16 oder höher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)oder höher / SQL Server 2014 SP2
     - [SQL Server Systemeigener Client für SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 für SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)oder höher
     - [Freigegebene Verwaltungsobjekte für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Grundlegende Schritte zum Installieren von Voraussetzungen in der empfohlenen Reihenfolge der Vorgänge

1. Installieren Sie das Skype for Business Server CU9-Update auf allen Servern. 
    1. Installieren Sie das Update auf Komponenten mithilfe des Updaters.
    2. Aktualisieren von Datenbanken gemäß dokumentierten Verfahren. Informationen zu Skype for Business Server 2015 finden Sie unter KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie mit anderen Änderungen vorankommen.
2. Laden Sie .NET 4.7 Offline Installer herunter. 
    1. Referenz: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden.
    3. Referenz: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Führen Sie das Installationsprogrammpaket aus.
    7. Starten Sie den Server neu.
3. Aktualisieren SQL Express 2014 auf allen Servern. 
    1. Referenz: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Herunterladen SQL 2014 SP2 
        - Referenz: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Kopieren Sie die Installationsmedien in einen Ordner auf dem Server (z. B. C:\01_2014SqlSp2)
    4. Sicherstellen, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Öffnen Sie eine Administrator-Eingabeaufforderung, und aktualisieren Sie alle installierten Komponenten und Instanzen 
        - Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Aktualisieren SQL systemeigenen Clients. 
    1. Referenz: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Herunterladen von [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Beenden der SQL installierten Instanzen 
        - Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Nur Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installieren Sie das Update.
5. Aktualisieren von ODBC Driver 11 für SQL Server unterstützung für TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Laden [Sie ODBC Driver 11 für SQL Server - Windows herunter.](https://www.microsoft.com/download/confirmation.aspx?id=36434)
    2. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden.
        - Beispiel (Standard Edition): ```Stop-CsWindowsService```
        - Beispiel (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Installieren Sie das Update.
6. Bereitstellen der erforderlichen Registrierungsschlüssel.

### <a name="pre-requisite-registry-keys"></a>Erforderliche Registrierungsschlüssel

Kopieren/einfügen Sie den folgenden Test in Notepad, benennen Sie TLSPreReq.reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:

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

Für SQL für Enterprise #A0 sollten voraussetzungen und TLS deaktiviert wie alle SQL oder Betriebssystemupdates behandelt werden. siehe: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

Während sowohl die Schritte zum Deaktivieren der erforderlichen Anwendung als auch der TLS kombiniert werden können, wird dringend empfohlen, dass alle Voraussetzungen angewendet werden, bevor Sie mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene fortfahren. Die bewährte Methode wäre, die Umgebung vorzubereiten, indem alle voraussetzungen bereitgestellt, die Ordnungsgemäß und wie erwartet ausgeführten Arbeitsauslastungen validiert werden und dann mit der TLS 1.0/1.1-Deaktivierung zu einem späteren Zeitpunkt fortschreitet.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deaktivieren von TLS 1.0 und 1.1 über registrierungsimport

Bevor Sie mit den nächsten Schritten fortfahren, stellen Sie sicher, dass Sie alle Voraussetzungen erfüllt und *Skype for Business Server aktualisiert haben.*

Kopieren Sie den folgenden Text in eine Editordatei, und benennen Sie ihn **TLSDisable.reg um:**

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

Importieren Sie die .reg-Datei auf jedem Server, den Sie TLS 1.0 und 1.1 deaktivieren möchten. Starten Sie den Server neu. Sobald die Dienste wieder online sind, wechseln Sie zum nächsten Server. Der Ansatz für Enterprise Edition Pools ist die gleiche, die Sie für jedes Betriebssystemupdate nutzen würden.

Möglicherweise haben Sie bemerkt, dass wir hier nicht nur TLS 1.0 und 1.1 deaktivieren. Wir unterstützen die Neuordnung der Cipher Suite (wie oben gezeigt) und das Deaktivieren einiger älterer schwacher Chiffren. Dies ist das erste Mal, dass wir diese Änderungen an SCHANNEL und Crypto API auf Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir unterstützen und zurzeit getestet haben. Wir können in Zukunft möglicherweise zusätzliche Konfigurationen in Betracht ziehen, aber im Ersten sollten Sie die Registrierungsimportdatei in Ihrer Implementierung nicht ändern.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Überprüfen, ob Arbeitsauslastungen wie erwartet funktionieren

Nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Ihre Hauptarbeitsauslastungen wie erwartet funktionieren, z. B. Im-&-Anwesenheit, P2P-Anrufe, Enterprise-VoIP usw.

**Überprüfen, ob nur TLS 1.2 verwendet wird**

Ihr Sicherheitsteam muss eine neue Überwachung des Skype for Business-Datenverkehrs durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1.0 und 1.1 nicht mehr verwendet werden.

Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen zu Webdiensten von Skype for Business Server 2015 zu testen, nachdem TLS 1.0 und TLS 1.1 deaktiviert wurden.

1. Starten Sie Internet Explorer.
2. Wählen **Sie**  >  **Extras Internetoptionen aus.**
3. Wählen Sie die Registerkarte **Erweitert** aus.
4. Scrollen **Sie** unter Einstellungen nach unten.
5. Stellen Sie sicher, dass TLS 1.0, TLS 1.1 und TLS 1.2 aktiviert sind.
6. Durchsuchen Sie die URL des internen Webdiensts Ihres SfB 2015-Pools (sollte eine Verbindung erfolgreich herstellen).
7. Wechseln Sie zurück zu Internet Explorer, und deaktivieren Sie die Option, **nur TLS 1.2 zu** verwenden.
8. Durchsuchen Sie die URL des internen Webdiensts Ihres SfB 2015-Pools erneut (sollte keine Verbindung herstellen).

![Internetoptionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Erweiterte Bereitstellungsszenarien

Da einige Voraussetzungen für die Abhängigkeit zur Unterstützung von TLS 1.2 in Skype for Business Server 2015 erforderlich sind, kann die Installation von RTM-Medien auf jedem System fehlschlagen, auf dem TLS 1.0 und 1.1 deaktiviert wurden.

**Bereitstellen neuer Standard Edition-Server oder Enterprise Edition-Pools, nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert wurden.**

**Option 1:** Verwenden [Sie SmartSetup](../../deploy/install/install-skype-for-business-server.md). Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL in einer zukünftigen CU zu finden und diesen Artikel in Zukunft zu aktualisieren.

**Option 2:** Vorinstallation lokaler SQL Instanzen (RTCLOCAL und LYNCLOCAL)

1. Laden Sie die SQL Express 2014 SP2 (SQLEXPR_x64.exe) in den lokalen Ordner auf FE herunter und kopieren Sie sie. Angenommen, der Ordnerpfad <SQL_FOLDER_PATH>.
2. Starten Sie PowerShell oder Eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.
3. Erstellen Sie die RTCLOCAL SQL Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie fortfahren:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Erstellen Sie die LYNCLOCAL SQL Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie mit dem nächsten Schritt fortfahren:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Führen Sie skype for Business Server 2015 RTM setup aus.
2. Führen Sie die restlichen Schritte aus dem abschnitt "Voraussetzungen" weiter oben aus.

**Option 3:** Sie können binäre Dateien auch manuell in einem lokalen Installationsmedienverzeichnis wie folgt ersetzen:

1. [Installieren der erforderlichen Komponenten für Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installieren von .NET 4.7: 
      - **Hinweis:** Wir haben die Unterstützung für .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281) eingeführt. Daher aktualisieren wir in den nachfolgenden Schritten die Kernkomponenten vor der Hauptinstallation.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referenz: [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Kopieren von ISO-Dateien/Ordnern: 
    - Öffnen Sie, wenn die Skype for Business Server 2015-ISO angefügt ist, das Stammverzeichnis des Laufwerks, das als angefügt ist (Ex: D: \) im Datei-Explorer.
    - Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. B. C:\SkypeForBusiness2015ISO).
    - **Hinweis:** Vor der Installation von Komponenten müssen einige Dateien zur Unterstützung von TLS 1.2 aktualisiert werden.
4. Ersetzen Sie MSI/EXE-Pakete: 
    - Ersetzen Sie die vorhandenen MSI- und EXE-Pakete im Ordner /Setup/amd64/ der Installationsmedien auf dem lokalen Computer.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Benennen Sie SQLEXPR_x64 auf dem lokalen Computer um, und ersetzen Sie die vorhandene Datei im Ordner Setup/amd64/ des Installationsmediums.
    - SQL Systemeigener Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Hinweis:** Benennen Sie dies bei sqlncli.msi um, und ersetzen Sie dann die vorhandene Datei, die im Ordner Setup/amd64/ des Installationsmediums vorhanden ist.
    - SQL Verwaltungsobjekte: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können. Wählen Sie aus, um SharedManagementObjects.msi herunterzuladen.
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die im Ordner Setup/amd64/ des Installationsmediums vorhanden ist.
    - SQL CLR-Typen: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Feature Pack enthält viele Elemente, die heruntergeladen werden können. Wählen Sie aus, um CQLSysClrTypes.msi herunterzuladen
        - **Hinweis**: Ersetzen Sie die vorhandene Datei, die im Ordner Setup/amd64/ des Installationsmediums vorhanden ist.
5. Installieren von Kernkomponenten: 
    - Führen Setup.exe aus dem Ordner Setup/amd64/ des Installationsmediums aus. Befolgen Sie die Anweisungen zum Installieren von Kernkomponenten
    - Schließen Sie Kernkomponenten.
6. Aktualisieren von Kernkomponenten: 
    - Laden Sie das Skype for Business Update Installer herunter.
    - Führen Sie das Installationsprogramm aus, um Kernkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.
    - **Hinweis:** Ab der Veröffentlichung von CU6HF2 wird das Feature für automatische Updates derzeit nur bis zu CU6 installiert. Daher muss der Updater separat ausgeführt werden, um Die Kernkomponenten auf 6.0.9319.516 zu aktualisieren.
    - Referenz: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installieren von Verwaltungstools (optional): 
    - Dadurch werden die Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) und Microsoft System CLR Types für SQL Server 2014 (x64) mithilfe der aktualisierten Dateien installiert. Darüber hinaus stehen der Skype for Business Server 2015-Topologie-Generator und die Systemsteuerung auf dem lokalen Computer zur Verfügung.
8. Installieren des lokalen Konfigurationsspeichers (Schritt 1): 
     - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Skype for Business Server System installieren oder aktualisieren, und klicken Sie auf **Ausführen** unter Schritt 1: Installieren des lokalen Konfigurationsspeichers.
     - Klicken **Sie im** Dialogfeld Lokaler **Konfigurationsspeicher** installieren auf Weiter.
     ![Dialogfeld Lokaler Konfigurationsspeicher installieren](../../media/local-configuration-store.png)
     - Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Vorgangsstatus abgeschlossen ist. Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **Protokoll anzeigen klicken.**
     ![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)
     - Klicken Sie auf **Fertig stellen**.
9. Einrichten oder Entfernen von Skype for Business Server-Komponenten (Schritt 2):
    - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **Skype for Business Server System** installieren oder aktualisieren, und klicken Sie auf **Ausführen** unter Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten
    - Klicken **Sie im** Dialogfeld Skype for Business Server-Komponenten einrichten auf Weiter.
    ![Das Fenster Skype for Business Server-Komponenten einrichten](../../media/set-up-skype-for-business-server-components-window.png)
    - Überprüfen Sie das Protokoll mithilfe des Ansichtsprotokolls, und überprüfen Sie, ob das Setup ohne Probleme abgeschlossen wurde. 
    - Klicken Sie auf **Fertig stellen**.
10. Fahren Sie bei Bedarf mit zusätzlicher Installation und Konfiguration fort (Sie können die normalen Installationsverfahren an diesem Punkt fortsetzen).