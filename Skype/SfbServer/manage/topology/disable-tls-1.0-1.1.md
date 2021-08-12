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
ms.openlocfilehash: 9bb737466595420770c4374d7d1b76bcc0319e38d188f550fb284b686df7e19f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337773"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Deaktivieren von TLS 1.0/1.1 in Skype for Business Server 2015

Dieser Artikel hilft Ihnen bei der Vorbereitung und Implementierung der Deaktivierung von TLS 1.0 und 1.1 in Ihren Umgebungen. Dieser Prozess erfordert eine umfassende Planung und Vorbereitung. Lesen Sie sorgfältig alle Informationen in diesem Artikel, während Sie planen, TLS 1.0 und 1.1 für Ihre Organisation zu deaktivieren. Es gibt viele externe Abhängigkeiten und Konnektivitätsbedingungen, die durch deaktivieren von TLS 1.0/1.1 beeinträchtigt werden können, sodass umfangreiche Planung und Tests erforderlich sind.

- [Hintergrund und Bereich](#background-and-scope)
- [Voraussetzungen und Prozess](#prerequisites-and-process)
- [Erweiterte Bereitstellungsszenarien](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Hintergrund und Bereich

Die wichtigsten Treiber für die Bereitstellung von TLS 1.0 und 1.1 deaktivieren die Unterstützung für Skype for Business Server lokal sind pci-Sicherheitsstandardsrat (Payment Card Industry) und Anforderungen der Federal Information Processing Standards. Weitere Informationen zu PCI-Anforderungen finden Sie [hier.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)  Microsoft kann keine Anleitung dazu bereitstellen, ob Ihre Organisation diese oder andere Anforderungen erfüllen muss. Sie müssen ermitteln, ob SIE TLS 1.0 und/oder 1.1 in Ihren Umgebungen deaktivieren müssen.

Microsoft hat ein Whitepaper zu TLS erstellt, das [hier](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)verfügbar ist, und wir empfehlen auch die Hintergrundlesung, die in diesem [Exchange Blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)zur Verfügung steht.

## <a name="supportability-scope"></a>Unterstützungsbereich

*Bereich* bezieht sich auf Unterstützungsgrenzen. *Vollständig getestet und unterstützt* bedeutet, dass wir die Deaktivierung von TLS 1.0 und 1.1 für die aufgeführten Produktversionen vollständig unterstützen und getestet haben. *Zurzeit wird* genau dies untersucht. wir untersuchen aktiv, diese Produkte in den Bereich der TLS-Deaktivierungsunterstützung zu bringen. *Außer Reichweite* bedeutet, dass diese Produktversionen das Deaktivieren von TLS 1.0 oder 1.1 nicht unterstützen und nicht funktionieren, mit den angegebenen Ausnahmen.

### <a name="fully-tested-and-supported-servers"></a>Vollständig getestete und unterstützte Server

- Skype for Business Server 2019 CU1 17.0.2046.123 (Juni 2019) oder höher
- Skype for Business Server 2015 CU9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder abgelösten Update), 2012 R2 oder 2016.
- Direktes Upgrade Skype for Business Server 2015 mit CU9 6.0.9319.548 (Mai 2019) oder höher auf Windows Server 2008 R2, 2012 (mit KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) oder abgelöster Aktualisierung) oder 2012 R2.
- Exchange Konnektivität und Outlook Web App mit Exchange Server 2010 SP3 RU19 oder [](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/) höher
- Survivable Branch Appliance (SBA) mit Skype for Business Server 2015 CU6 DOPPELKLICK2 oder höher (bestätigen Sie bei Ihrem Anbieter, dass sie die entsprechenden Updates gepackt und für Ihre Appliance zur Verfügung gestellt haben)
- Survivable Branch Server (SBS) mit Skype for Business Server 2015 CU6 WEBSERVER2 oder höher
- Lync Server 2013 **Nur Edgerolle**, dies liegt daran, dass die Edgerolle keine Abhängigkeit von Windows Fabric 1.0 aufweist.

### <a name="fully-tested-and-supported-clients"></a>Vollständig getestete und unterstützte Clients

- Lync 2013 (Skype for Business) Desktopclient, MSI und C2R, einschließlich Basic [15.0.5023.1000 oder höher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 oder höher,](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)einschließlich Basic
- Skype for Business 2016 Click to Run require the [April 2018](/officeupdates/release-notes-office365-proplus) Updates: 
    - Monatlich und Semi-Annual gezielt, 16 \. 0 \. 9126 \. 2152 oder höher
    - Semi-Annual und verzögerter Kanal, 16 \. 0 \. 8431 \. 2242 oder höher
- Skype for Business auf Mac 16.15 oder höher
- Skype for Business für iOS und Android 6.19 oder höher
- Microsoft Teams-Räume (früher bekannt als Skype Room System V2 SRS V2) 4.0.64.0 (Dezember 2018) oder höher
- Surface Hub Update für Team Edition basierend auf KB4499162 (Mai 2019, BETRIEBSSYSTEM Build 15063.1835) oder höher
- Skype Web App 2015 CU6 DOPPELKLICK2 oder höher (wird mit Server ausgeliefert)

### <a name="currently-being-investigated"></a>Wird derzeit untersucht

- Anrufqualitäts-Dashboard (neue Installation nach TLS 1.0, 1.1 wurde deaktiviert, siehe unten)*
 
### <a name="out-of-scope"></a>Nicht inbegriffen

Sofern nicht anders angegeben, sind die folgenden Produkte nicht für TLS 1.0/1.1 deaktiviert und funktionieren nicht in einer Umgebung, in der TLS 1.0 und 1.1 deaktiviert wurden. Dies bedeutet: Wenn Sie weiterhin nicht bereichsbezogene Server oder Clients verwenden, müssen Sie diese aktualisieren oder entfernen, wenn Sie TLS 1.0/1.1 an einer beliebigen Stelle in Ihrer Skype for Business Server lokalen Bereitstellung deaktivieren müssen.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 oder niedriger
- Lync für Mac 2011
- Lync 2013 für Mobile – iOS, iPad, Android oder Windows Phone
- Lync"MX"-Windows Store-Client
- Lync Room System (auch als Lync Room System bezeichnet) SRSv1). LRS hat am 9. Oktober 2018 das Ende des Supports erreicht und wird nicht aktualisiert, um TLS 1.2 zu unterstützen.
- Alle Lync 2010-Clients
- Lync Telefon Edition – aktualisierte Anleitung [hier.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- 2013-basierte Survivable Branch Appliance (SBA) oder Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Skype for Business für Windows Phone

### <a name="exceptions"></a>Ausnahmen

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 verwendet eine Abhängigkeit von Windows Fabric Version 1.0.  In der Entwurfsphase für Lync Server 2013 wurde Windows Fabric 1.0 für die ansprechende und neue verteilte Architektur ausgewählt, um Replikation, hohe Verfügbarkeit und Fehlertoleranz bereitzustellen.  Im Laufe der Zeit haben sowohl Skype for Business Server als auch Windows Fabric diese gemeinsame Architektur mit einem erheblichen Neuentwurf in nachfolgenden Versionen erheblich verbessert.  Der aktuelle Skype for Business 2015 Server verwendet beispielsweise Windows Fabric 3.0.

Leider unterstützt Windows Fabric 1.0 **TLS 1.2 nicht.  Es wird jedoch Lync Server 2013 aktualisiert, um mit TLS 1.2 zu arbeiten.** Dies wird im nächsten kumulativen Update für Lync Server 2013 verfügbar sein.  Wir bieten TLS 1.2-Unterstützung, um Koexistenz-, Migrations-, Verbund- und Hybridszenarien zu ermöglichen.

Wenn Ihre Organisation TLS 1.0 und 1.1 deaktivieren muss und Sie derzeit Lync Server 2013 verwenden, empfehlen wir, mit dem Planungsprozess zu beginnen, mit der Möglichkeit, ein direktes Upgrade durchzuführen oder parallel zu migrieren (neue Pools, Verschieben von Benutzern) zu Skype for Business Server 2015 oder höher.  Oder Sie möchten die Migration zu Skype for Business Online beschleunigen.

#### <a name="call-quality-dashboard"></a>Dashboard für Anrufqualität

Das Dashboard für lokale Anrufqualität ist derzeit während der Neuinstallation von TLS 1.0 abhängig (bei der ersten Installation in Ihren lokalen Umgebungen).  Wir untersuchen dieses Problem derzeit und planen, in naher Zukunft einen Fix zu veröffentlichen.  Wenn Sie beabsichtigen, CQD zu installieren und auch TLS 1.0 zu deaktivieren, empfehlen wir, zuerst die CQD-Installation abzuschließen und dann mit der Deaktivierung von TLS 1.0 fortzufahren.

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN-Manager

Skype for Business DER SDN-Manager, der SQL eine Datenbank verwendet, ist während der Neuinstallation von TLS 1.0 abhängig. Wenn Sie planen, Skype for Business SDN-Manager mit SQL einer Datenbank zu installieren und auch TLS 1.0 zu deaktivieren, empfehlen wir, zuerst Skype for Business SDN-Manager abzuschließen und dann mit der TLS 1.0-Deaktivierung fortzufahren. Für den Fall, dass TLS 1.0 vor der Installation deaktiviert wurde, sollten Sie TLS 1.0 vorübergehend wieder auf SQL Server Back-End-Server aktivieren, der zum Hosten Skype for Business SDN Manager SQL Datenbank verwendet wird.

#### <a name="third-party-devices"></a>Drittanbietergeräte

Überprüfen Sie auf Geräten von Drittanbietern wie 3PIP-Telefonen, Videokonferenzen, Reverseproxys und Lastenausgleich die Tls 1.2-Unterstützung, testen Sie sorgfältig, und wenden Sie sich bei Bedarf an den Anbieter.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Überlegungen zum Partnerverbund beim Deaktivieren von TLS 1.0/1.1 auf Edgeservern

Sie müssen die Auswirkungen der Deaktivierung von TLS 1.0/1.1 auf Ihre Edgeserver sorgfältig planen und berücksichtigen.  Sobald TLS 1.0 und 1.1 deaktiviert sind, stellen Sie möglicherweise fest, dass andere Organisationen nicht mehr in der Lage sind, sich mit Ihrer Organisation zu verbinden.

Sie können TLS 1.0/1.1 auf Ihren Edgeservern aktiviert lassen, um die Abwärtskompatibilität mit externen Systemen ohne Patch (SfB 2015, Lync 2013) oder älteren (2010) aufrechtzuerhalten.

Microsoft kann keine Ratschläge oder Empfehlungen dazu geben, ob Ihr Edgenetzwerk (oder ein Netzwerk) unter den PCI-Standard fällt. die von dem jeweiligen Unternehmen bestimmt werden müssen.

Skype for Business Online ist derzeit in der Lage, TLS 1.2 zu verwenden, sodass keine Auswirkungen auf Hybrid/Verbund mit Online erwartet werden.

PIC (Public IM Connectivity) to Skype Consumer service: We do not expecting TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC-Gateways sind bereits TLS 1.2-fähig.

## <a name="prerequisites-and-process"></a>Voraussetzungen und Prozess

Sofern oben nicht erwähnt, funktionieren Clients und Geräte, sobald TLS 1.0 und 1.1 außerhalb des Bereichs deaktiviert sind, länger ordnungsgemäß oder überhaupt. Dies kann bedeuten, dass Sie anhalten und auf aktualisierte Anleitungen von Microsoft warten müssen. Nachdem Sie sich vergewissert haben, dass Sie alle Anforderungen erfüllen und einen Plan zum Beheben von Lücken haben, fahren Sie fort.

Während Skype for Business Server 2019 für die Installation bereit ist, erfordert Skype for Business Server 2015, dass Sie CU9 installieren, erforderliche Updates auf .NET und SQL anwenden, erforderliche Registrierungsschlüssel und schließlich eine separate Runde von Betriebssystemkonfigurationsupdates bereitstellen (d. h. TLS 1.0 und 1.1 über den Registrierungsdateiimport deaktivieren). Es ist von entscheidender Bedeutung, dass Sie alle erforderlichen Komponenten, einschließlich Skype for Business Server 2015 CU6 TLS2, abschließen, bevor Sie TLS 1.0 und 1.1 auf jedem Server in Ihrer Umgebung deaktivieren. Jeder Skype for Business-Server, einschließlich Edgerolle und SQL-Back-Ends, erfordert die Updates. Stellen Sie außerdem sicher, dass alle unterstützten (im Umfang enthaltenen) Clients auf die erforderlichen Mindestversionen aktualisiert wurden. Vergessen Sie nicht, auch Verwaltungsarbeitsstationen zu aktualisieren.

Wir möchten die übliche Reihenfolge der Vorgänge von "inside out" für das Upgrade von Skype for Business Servern befolgen. Behandeln Sie Directorpools, beständigen Chat und gepaarte Pools auf die gleiche Weise wie normalerweise. Reihenfolge und Methoden für das Upgrade werden [hier](topology.md) und [hier](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)behandelt.

### <a name="high-level-process"></a>Allgemeiner Prozess

1. Testen Sie alle Schritte in Ihrer Übung, bevor Sie Produktionsserver konfigurieren.
2. Sichern und Beibehalten einer Kopie der exportierten Registrierung auf jedem einzelnen Server, der aktualisiert werden soll. Registrierungen können nicht zwischen Servern gemeinsam verwendet werden. sie enthalten eindeutige computerbasierte Schlüssel.
3. Aktualisieren Sie alle Skype for Business 2015-Server auf CU9 oder höher. Führen Sie für Skype for Business Server 2019 ein Upgrade auf CU1 oder höher durch.
4. Installieren Sie alle erforderlichen Komponenten auf allen Servern.
5. Stellen Sie erforderliche Registrierungsschlüssel bereit.
6. Stellen Sie sicher, dass alle clients im Bereich aktualisiert werden.
7. Deaktivieren Sie TLS 1.0 und 1.1 über den Registrierungsimport.
8. Überprüfen Sie, ob Workloads wie erwartet funktionieren.
    - Wenn Probleme auftreten, Problembehandlung und Lösung oder
    - Wiederherstellen der Registrierung aus Schritt 2 zum erneuten Aktivieren von TLS 1.0 und 1.1
9. Überprüfen Sie, ob nur TLS 1.2 verwendet wird.

### <a name="install-prerequisites-to-all-servers"></a>Installieren der erforderlichen Komponenten auf allen Servern

Bevor Sie mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene in Ihren Skype for Business Server 2015-Bereitstellungen beginnen, ist eine umfassende Aktualisierung von Abhängigkeiten erforderlich. Es folgen die Mindestversionen, die TLS 1.2 unterstützen können. Stellen Sie alle erforderlichen Updates auf jedem Skype for Business Server in Ihrer Umgebung bereit, bevor Sie mit dem Deaktivieren von TLS 1.0 und 1.1 beginnen.

- Skype for Business Server 2015 CU9 6.0.9319.548 (Mai 2019) oder höher
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) oder höher, wobei SchUseStrongCrypto in der Registrierung aktiviert ist (siehe unten).
- SQL muss auf allen Skype for Business 2015-Servern und Back-Ends aktualisiert werden. Aktualisieren Sie zuerst Enterprise Edition Pool SQL Back-Ends und dann die entsprechenden FEs. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)oder höher / SQL Server 2012 SP2 + CU16 oder höher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)oder höher / SQL Server 2014 SP2
     - [SQL Server Native Client für SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC-Treiber 11 für SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)oder höher
     - [Freigegebene Verwaltungsobjekte für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes für SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Grundlegende Schritte zum Installieren von Voraussetzungen in empfohlener Reihenfolge von Vorgängen

1. Installieren Sie das Skype for Business Server CU9-Update auf allen Servern. 
    1. Installieren Sie das Update mithilfe des Updaters auf Komponenten.
    2. Aktualisieren Sie Datenbanken gemäß dokumentierten Verfahren. Informationen Skype for Business Server 2015 finden Sie unter KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Überprüfen Sie die Produktfunktionalität in der Bereitstellung, bevor Sie mit anderen Änderungen weiterkommen.
2. Laden Sie .NET 4.7 Offline Installer herunter. 
    1. Verweis: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden.
    3. Verweis: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Beispiel (Standard Edition):```Stop-CsWindowsService```
    5. Beispiel (Enterprise Edition):```Invoke-CsComputerFailover```
    6. Führen Sie das Installationspaket aus.
    7. Starten Sie den Server neu.
3. Aktualisieren Sie SQL Express 2014 auf allen Servern. 
    1. Verweis: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Herunterladen SQL 2014 SP2 
        - Verweis: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Kopieren Sie das Installationsmedium in einen Ordner auf dem Server (z. B.: C:\01_2014SqlSp2)
    4. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden. 
        - Beispiel (Standard Edition):```Stop-CsWindowsService```
        - Beispiel (Enterprise Edition):```Invoke-CsComputerFailover```
    5. Öffnen Sie eine Eingabeaufforderung für Administratoren, und aktualisieren Sie alle installierten Komponenten und Instanzen. 
        - Beispiel: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Aktualisieren sie SQL Native Client. 
    1. Referenz: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Herunterladen von [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden. 
        - Beispiel (Standard Edition):```Stop-CsWindowsServices```
        - Beispiel (Enterprise Edition):```Invoke-CsComputerFailover```
    4. Beenden der Ausführung der installierten SQL Instanzen 
        - Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Beispiel (nur Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installieren Sie das Update.
5. Aktualisieren Sie ODBC-Treiber 11 für SQL Server, um Unterstützung für TLS 1.2 (KB [3135244)](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)einzuschließen.
    1. Laden Sie [ODBC-Treiber 11 für SQL Server – Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)herunter.
    2. Stellen Sie sicher, dass Skype for Business Server 2015-Dienste auf dem Front-End-Server beendet werden.
        - Beispiel (Standard Edition):```Stop-CsWindowsService```
        - Beispiel (Enterprise Edition):```Invoke-CsComputerFailover```
    3. Installieren Sie das Update.
6. Stellen Sie erforderliche Registrierungsschlüssel bereit.

### <a name="pre-requisite-registry-keys"></a>Erforderliche Registrierungsschlüssel

Kopieren/fügen Sie den folgenden Test in Editor ein, benennen Sie TLSPreReq.reg oder einen Namen Ihrer Wahl um, und importieren Sie dann:

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

Für SQL Back-Ends für Enterprise Edition Pools sollten Voraussetzungen und TLS-Deaktivierung wie alle SQL oder Betriebssystemupdates behandelt werden. weitere Informationen finden Sie unter:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

Während die Schritte zum Deaktivieren der erforderlichen Anwendung und der TLS-Deaktivierung kombiniert werden können, wird dringend empfohlen, alle erforderlichen Komponenten anzuwenden, bevor Sie mit der Deaktivierung von TLS 1.0 und 1.1 auf Betriebssystemebene fortfahren. Die bewährte Vorgehensweise besteht darin, die Umgebung vorzubereiten, indem alle erforderlichen Komponenten bereitgestellt, überprüft wird, dass alle Workloads ordnungsgemäß und wie erwartet funktionieren, und dann mit der Deaktivierung von TLS 1.0/1.1 zu einem späteren Zeitpunkt fortzufahren.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Deaktivieren von TLS 1.0 und 1.1 über den Registrierungsimport

Bevor Sie mit den nächsten Schritten fortfahren, *stellen Sie sicher, dass Sie alle Voraussetzungen erfüllt und Skype for Business Server aktualisiert haben.*

Kopieren Sie den folgenden Text in eine Editor Datei, und benennen Sie sie **in "TLSDisable.reg"** um:

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

Importieren Sie die REG-Datei auf jedem Server, auf dem Sie TLS 1.0 und 1.1 deaktivieren möchten. Starten Sie den Server neu. Sobald die Dienste wieder online sind, wechseln Sie zum nächsten Server. Der Ansatz für Enterprise Edition Pools ist der gleiche, den Sie bei jedem Betriebssystemupdate anwenden würden.

Vielleicht haben Sie bemerkt, dass wir hier mehr als nur TLS 1.0 und 1.1 deaktivieren. Wir unterstützen die Neureihenfolge von Cipher Suite (wie oben dargestellt) und die Deaktivierung einiger älterer schwacher Chiffren. Dies ist das erste Mal, dass wir diese Änderungen an der SCHANNEL- und Krypto-API auf Skype for Business Server offiziell unterstützt haben, und es ist wichtig zu beachten, dass diese Änderungen die einzigen sind, die wir derzeit unterstützen und getestet haben. Möglicherweise erwägen wir in Zukunft zusätzliche Konfigurationen, aber ändern Sie die Registrierungsimportdatei vorerst nicht in Ihrer Implementierung.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Überprüfen, ob Workloads wie erwartet funktionieren

Nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert wurden, stellen Sie sicher, dass alle Hauptarbeitslasten erwartungsgemäß funktionieren, z. B. Chat & Anwesenheit, P2P-Anrufe, Enterprise-VoIP usw.

**Überprüfen, ob nur TLS 1.2 verwendet wird**

Lassen Sie Ihr Sicherheitsteam eine neue Überwachung von Skype for Business Datenverkehr durchführen, um sicherzustellen, dass die älteren Protokolle TLS 1.0 und 1.1 nicht mehr verwendet werden.

Alternativ können Sie Internet Explorer verwenden, um TLS-Verbindungen mit Webdiensten ab Skype for Business Server 2015 zu testen, nachdem TLS 1.0 und TLS 1.1 deaktiviert wurden.

1. Starten Sie Internet Explorer.
2. Wählen Sie   >  **"Extras Internetoptionen" aus.**
3. Wählen Sie die Registerkarte **Erweitert** aus.
4. Scrollen Sie unter **Einstellungen** nach unten.
5. Stellen Sie sicher, dass TLS 1.0, TLS 1.1 und TLS 1.2 aktiviert sind.
6. Durchsuchen Sie die interne Webdienst-URL Ihres SfB 2015-Pools (sollte erfolgreich eine Verbindung herstellen).
7. Wechseln Sie zurück zu Internet Explorer, und deaktivieren Sie die Option, nur **TLS 1.2** zu verwenden.
8. Durchsuchen Sie die interne Webdienst-URL Ihres SfB 2015-Pools erneut (sollte keine Verbindung herstellen).

![Internetoptionen](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Erweiterte Bereitstellungsszenarien

Da einige Abhängigkeitsvoraussetzungen erforderlich sind, um TLS 1.2 in Skype for Business Server 2015 zu unterstützen, schlägt die Installation von RTM-Medien auf allen Systemen fehl, auf denen TLS 1.0 und 1.1 deaktiviert wurden.

**Bereitstellen neuer Standard Edition Server oder Enterprise Edition Pools, nachdem TLS 1.0 und 1.1 in Ihrer Umgebung deaktiviert wurden.**

**Option 1:** Verwenden Sie [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Beachten Sie, dass wir SmartSetup aktualisieren, um die aktualisierten SQL Binärdateien in einem zukünftigen CU aufzunehmen, und diesen Artikel in Zukunft aktualisieren werden.

**Option 2:** Vorinstallierte lokale SQL Instanzen (RTCLOCAL und LYNCLOCAL)

1. Laden Sie SQL Express 2014 SP2 (SQLEXPR_x64.exe) herunter, und kopieren Sie sie in den lokalen Ordner auf FE. Angenommen, ordnerpfad <SQL_FOLDER_PATH>.
2. Starten Sie PowerShell oder eingabeaufforderung, und navigieren Sie zu <SQL_FOLDER_PATH>.
3. Erstellen Sie die RTCLOCAL-SQL Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie fortfahren:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Auto csv
1. Erstellen Sie die LYNCLOCAL-SQL Instanz, indem Sie den folgenden Befehl ausführen. Warten Sie, bis SQLEXPR_x64.exe abgeschlossen ist, bevor Sie mit dem nächsten Schritt fortfahren:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Führen Sie Skype for Business Server 2015 RTM-Setup aus.
2. Führen Sie die restlichen Schritte aus dem Abschnitt "Voraussetzungen" oben aus.

**Option 3:** Sie können Binärdateien in einem lokalen Installationsmedienverzeichnis auch wie folgt manuell ersetzen:

1. [Installieren der erforderlichen Komponenten für Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installieren von .NET 4.7: 
      - **Hinweis:** Wir haben die Unterstützung für .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281) eingeführt. Daher aktualisieren wir in späteren Schritten unten die Hauptkomponenten vor der Hauptinstallation.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Referenz: [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. KOPIEREN VON ISO-Dateien/Ordnern: 
    - Öffnen Sie das Stammverzeichnis des angefügten Laufwerks mit dem Skype for Business Server 2015 ISO als (Beispiel: D: \) im Datei-Explorer).
    - Kopieren Sie alle Ordner und Dateien in einen Ordner auf einem lokalen Datenträger (z. B.: C:\SkypeForBusiness2015ISO).
    - **Hinweis:** Vor der Installation von Komponenten müssen einige Dateien für die Unterstützung von TLS 1.2 aktualisiert werden.
4. Ersetzen Sie MSI-/EXE-Pakete: 
    - Ersetzen Sie die vorhandenen MSI- und EXE-Pakete im Ordner /Setup/amd64/ des Installationsmediums auf dem lokalen Computer.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - Benennen Sie auf dem lokalen Computer in SQLEXPR_x64 um, und ersetzen Sie die vorhandene Datei im Ordner "Setup/amd64/" des Installationsmediums.
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **Hinweis:** Benennen Sie dies bei Bedarf in sqlncli.msi um, und ersetzen Sie dann die vorhandene Datei, die im Ordner Setup/amd64/ des Installationsmediums vorhanden ist.
    - SQL Verwaltungsobjekte:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Featurepaket enthält viele Elemente, die heruntergeladen werden können. Wählen Sie aus, um nur SharedManagementObjects.msi herunterzuladen.
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die im Ordner "Setup/amd64/" des Installationsmediums vorhanden ist.
    - SQL CLR-Typen:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Hinweis:** Das Featurepaket enthält viele Elemente, die heruntergeladen werden können. Nur CQLSysClrTypes.msi herunterladen
        - **Hinweis:** Ersetzen Sie die vorhandene Datei, die im Ordner "Setup/amd64/" des Installationsmediums vorhanden ist.
5. Installieren von Hauptkomponenten: 
    - Führen Sie Setup.exe aus dem Ordner "Setup/amd64/" des Installationsmediums aus. Folgen Sie den Anweisungen zum Installieren von Kernkomponenten
    - Schließen Sie die Hauptkomponenten.
6. Aktualisieren der Hauptkomponenten: 
    - Laden Sie das Skype for Business Update-Installationsprogramm herunter.
    - Führen Sie das Installationsprogramm aus, um die Kernkomponenten zu aktualisieren und die Leistungsindikatoren zu installieren.
    - **Hinweis:** Ab der Veröffentlichung von CU6HF2 wird das Feature für automatische Updates derzeit nur bis zu CU6 installiert. Daher muss der Updater separat ausgeführt werden, um die Kernkomponenten auf 6.0.9319.516 zu aktualisieren.
    - Verweis: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installieren von Verwaltungstools (optional): 
    - Dadurch werden die Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) und Microsoft System CLR Types for SQL Server 2014 (x64) mithilfe der aktualisierten Dateien installiert. Darüber hinaus sind der Skype for Business Server 2015-Topologie-Generator und die Systemsteuerung auf dem lokalen Computer verfügbar.
8. Installieren der lokalen Konfiguration Store (Schritt 1): 
     - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf Skype for Business Server System installieren oder aktualisieren, und klicken Sie auf **"Ausführen"** unter Schritt 1: Installieren der lokalen Konfiguration Store.
     - Klicken Sie im Dialogfeld **"Lokale Konfiguration Store installieren" auf** **"Weiter".**
     ![Dialogfeld "Lokale Konfiguration Store installieren"](../../media/local-configuration-store.png)
     - Überprüfen Sie die Ergebnisse, und stellen Sie sicher, dass der Aufgabenstatus abgeschlossen ist. Überprüfen Sie die resultierende Protokolldatei, indem Sie auf **"Protokoll anzeigen"** klicken.
     ![Vorgangsstatus wird als abgeschlossen angezeigt](../../media/local-configuration-task-completed.png)
     - Klicken Sie auf **Fertig stellen**.
9. Einrichten oder Entfernen Skype for Business Server Komponenten (Schritt 2):
    - Öffnen Sie den Bereitstellungs-Assistenten, klicken Sie auf **Skype for Business Server System installieren oder aktualisieren,** und klicken Sie auf **"Ausführen"** in Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten.
    - Klicken Sie im Dialogfeld "Einrichten Skype for Business Server Komponenten" auf **"Weiter".**
    ![das Fenster "Einrichten Skype for Business Server Komponenten"](../../media/set-up-skype-for-business-server-components-window.png)
    - Überprüfen Sie das Protokoll mithilfe von "Protokoll anzeigen", und überprüfen Sie, ob das Setup ohne Probleme abgeschlossen wurde. 
    - Klicken Sie auf **Fertig stellen**.
10. Fahren Sie mit der zusätzlichen Installation und Konfiguration nach Bedarf fort (Sie können die normalen Installationsverfahren an dieser Stelle fortsetzen).