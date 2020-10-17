---
title: Beständiger Chat von lync Server 2013 Resource Kit-Tools
description: Beständiger Chat von lync Server 2013 Resource Kit-Tools.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542351"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Beständiger Chat von lync Server 2013 Resource Kit-Tools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Mit den beständiger Chat von lync Server 2013 Resource Kit-Tools können Sie Routineaufgaben für IT-Administratoren vereinfachen, die beständiger Chat von lync Server 2013 Server bereitstellen und verwalten. In diesem Thema werden neben den Installationsanweisungen der Zweck der einzelnen Tools und Beispiele für deren Verwendung beschrieben.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Zum Installieren der lync Server 2013, Resource Kit-Tools, laden Sie **PersistentChatReskit.msi**herunter. Führen Sie **PersistentChatReskit.msi** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: \\ **Programmdateien \\ Microsoft lync Server 2013 \\ beständiger Chat Server Resource Kit**. Tools mit eigenständigen ausführbaren Dateien befinden sich in diesem Ordner. Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.

<div>


> [!IMPORTANT]  
> Nachdem Sie die lync Server 2013, Resource Kit-Tools installiert haben, müssen Sie <STRONG>PsExec.exe</STRONG> installieren und <STRONG>PsExec.exe</STRONG> auf den folgenden Pfad kopieren: \\ <STRONG>Programmdateien \ Microsoft lync Server 2013 \ persistent Chat Server Resource Kit\ChatStressTool</STRONG>. Wenn Sie <STRONG>PsExec.exe</STRONG>nicht kopieren, löst das Belastungs Tool für beständigen Chat eine Fehler Ausnahme aus und wird nicht ordnungsgemäß ausgeführt. Stellen Sie sicher, dass diese Voraussetzungen erfüllt sind, bevor Sie das Tool ausführen. Ausführliche Informationen zum Installieren von <STRONG>PsExec.exe</STRONG>finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .



</div>

</div>

<div>

## <a name="supported-environments"></a>Unterstützte Umgebungen

Für eine optimale Leistung sollten die lync Server 2013 Resource Kit-Tools in derselben Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools (Übersicht)

Hier sind die Tools, die im beständiger Chat von lync Server 2013 Resource Kit bereitgestellt werden. Der folgende Abschnitt enthält eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung.

  - AffCheck

  - ChatMonitoringSummary

  - ChatStress-Tool

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>Beschreibung

Mit dem AffCheck-Tool wird bestätigt, dass die Back-End-Datenbankbenutzer und Gruppen zugehörigkeitsdaten Sätze des persistent Chats mit dem Active Directory-Domänendienste übereinstimmen.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Das Tool wird mit dem PersistentChatResKit-Installationsprogramm auf einem Computer installiert, der einer Domäne angehört.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank für beständigen Chat und Active Directory-Domänendienste verfügen.

</div>

<div>

## <a name="usage"></a>Verwendung

Konfigurieren Sie die AffCheck.exe.config Datei gemäß den Anweisungen in der Konfigurationsdatei, und führen Sie das AffCheck-Tool ohne Befehlszeilenparameter aus. Im folgenden finden Sie den Inhalt der Standard AffCheck.exe.config.

**AffCheck.exe.config:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>Beschreibung

Das PersistentChatMonitoringSummary-Tool verschiebt die Überwachungsinformationen für beständigen Chat aus der Überwachungsdatenbank in eine angegebene CSV-Protokolldatei.

Die CSV-Datei enthält eine Aufschlüsselung der Sitzungen für beständigen Chat nach der Anzahl der Sitzungen insgesamt, erfolgreicher Sitzungen, unerwarteter Fehler, erwarteter Fehler und einer Aufschlüsselung der unerwarteten Fehler durch Diagnose-ID, Anzahl der Fehler und Beschreibung des Fehlers.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Installieren Sie die Resource Kit-Tools für den beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf das Überwachungsdatenbank hat.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Überwachungsdatenbank verfügen.

Die Datei PersistentChatMonitoringSummary.exe.config muss einen \<connectionStrings\> Abschnitt enthalten, der die Verbindungszeichenfolge für die Überwachungsdatenbank definiert. Es muss auch einen Schlüssel für die PersistentChatEndpointUri enthalten, für die die Überwachungsdaten erfasst werden, und einen Dateipfad zu einem Speicherort für die CSV-Datei, die generiert wird. Beispiele dazu erhalten Sie in der installierten Konfigurationsdatei. Die Datei muss sich im gleichen Verzeichnis wie das Tool befinden.

</div>

<div>

## <a name="usage"></a>Verwendung

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Mit diesen Parametern wird die Auswahl der Daten definiert:

**Startdatum:** Gibt optional das Startdatum des Auswahlzeitraums an. Standard: 1/1/1753 12:00:00 Uhr

**EndDate:** Gibt optional das letzte Datum des Auswahlzeitraums an. Standard: jetzt

</div>

<div>

## <a name="example"></a>Beispiel

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Stress Tool für beständigen Chat

<div>

## <a name="description"></a>Beschreibung

Das Stress Tool für beständigen Chat bietet eine einfache Möglichkeit zum Simulieren der Verwendung des beständigen Chats zum Testen der realen Leistung, einschließlich variierter Benutzermodelle, um Ihre erwarteten Nutzungsszenarien besser zu erfüllen.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Installieren Sie die Resource Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank für beständigen Chat hat.

Zusätzlich zu diesem *Controller* -Computer benötigen Sie mehrere *Lade* Geräte. Für alle 10K-Benutzer in Ihrem Benutzermodell benötigen Sie mindestens 4 GB freien RAM auf einem Loader-Computer. Beispielsweise erfordert ein Run mit 80K-Benutzern etwa 32 GB RAM, verteilt auf alle Loader-Computer. Es wird empfohlen, dass Sie über mindestens drei Loader-Computer verfügen, unabhängig von der erwarteten Last.

Loader-Computer müssen das .NET 4,5-Framework sowie die Visual C++ 2012 Redistributable installiert haben.

</div>

<div>

## <a name="configuration"></a>Konfiguration

Kopieren Sie ChatStressTool-Dateien in einen freigegebenen Ordner, auf den alle Loader-Computer zugreifen können.

Erstellen von Benutzern und Kanälen zur Verwendung in der Belastungs Ausführung:

  - Erstellen Sie so viele Benutzer, wie Ihr Benutzermodell anruft, aktivieren Sie Sie für lync, und legen Sie Ihre Richtlinie für beständigen Chat auf aktiviert fest.

  - Erstellen Sie eine Kategorie für Ihre Spannungskanäle, und erstellen Sie dann so viele Räume, wie Sie in dieser Kategorie benötigt werden. Die Kategorie sollte alle Stress-Benutzer in Ihrer **zulässigen** Liste (durch Hinzufügen Ihrer OU) haben, und Stress rooms sollte eine Einstellung für den Datenschutz von **Open**haben.

  - Es wird empfohlen, zusätzliche Belastungs Räume zu erstellen. Sie können 50.000-Räume mit dem folgenden Befehl Windows PowerShell Befehlszeilenschnittstelle erstellen:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Bearbeiten Sie die Konfigurationsdateien so, dass Sie Ihrer Topologie entsprechen:

Ändern Sie in **LoaderProcess.exe.config**"Controller.contoso.com" in den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Controllercomputers.

In **StressLauncher.exe.config:**

1.  Ändern Sie den Wert für die Einstellung "LoaderBinary" in den Pfad des freigegebenen Ordners.

2.  Ändern Sie "anzüglicher"/"AdminPassword" auf Anmeldeinformationen, die Administratorzugriff auf Loader-Computer haben.

3.  Ändern Sie "ChannelCategory" in den Namen der Kategorie, unter der die Spannungskanäle erstellt wurden.

4.  Ändern Sie "UserNamePattern" und "UserPasswordPattern" in eine Vorlage, die mit Ihren Stress-Benutzeranmeldeinformationen übereinstimmt. {0} wird durch die Indexnummer des Benutzers ersetzt.

5.  Ändern Sie "Domäne" in die SIP-Domäne ihrer Testtopologie.

6.  Ändern Sie "ConnectionString" in eine Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats.

7.  Ändern Sie "UserIndexStart" in den Index des ersten Stress Benutzers.

8.  Ändern Sie "LyncFQDN" in den FQDN Ihrer Front-End-Pool.

9.  Ändern Sie die Liste "Computer" so, dass Computernamen für alle Ladegeräte Computer enthalten sind.

10. Ändern Sie die BaseAddress des Dienstendpunkts (Standardwert "Controller.contoso.com") in den FQDN des Controllercomputers.

</div>

<div>

## <a name="usage"></a>Verwendung

Öffnen Sie nach Abschluss der Konfiguration StressLauncher.exe auf dem Controllercomputer. Sie können StressLauncher als beliebigen Benutzer starten. Die Anmeldeinformationen, unter denen das Ladeprogramm auf den Loader-Computern gestartet wird, müssen in der Konfigurationsdatei angegeben werden. Außerdem müssen Sie eine Verbindungszeichenfolge mit Lesezugriff für die Back-End-Datenbank für beständigen Chat eingeben. Wenn diese Verbindungszeichenfolge die integrierte Windows-Authentifizierung verwendet, müssen Sie StressLauncher als Benutzer starten, der über diesen Zugriff verfügt.

Ändern Sie die Benutzermodell Einstellungen nach Bedarf. Klicken Sie auf **Start laden** , um eine Ausführung zu initiieren. Nach etwa einer Minute beginnen Benutzer mit der Anmeldung, und die Statusleiste beginnt zu füllen. An dieser Stelle können Sie den Controller-Computer arbeiten und Leistungsmessungen durchführen.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Beschreibung

ChatUpgradeVerifier ist ein spezifischer Datenbankvergleichstool für beständigen Chat. Das Tool vergleicht die Datenbank "Group Chat 2007 R2" oder "Group Chat 2010" (2007/2010Db) mit der Datenbank für beständigen Chat 2013 (2013Db).

Das Tool überprüft eine nach der anderen, jede Kategorie, den beständigen Chatroom und das Add-in in 2007/2010Db, um zu sehen, ob Sie im 2013Db angezeigt wird. Der Vergleich umfasst das Überprüfen aller Einstellungen für die Kategorie, den Chatroom oder das Add-in, alle Prinzipale im Bereich der Kategorie und alle Prinzipale in einer Rolle in der Kategorie oder im Chatroom. Wenn eine Kategorie oder ein Chatroom in der 2013Db nicht ordnungsgemäß angezeigt wird, werden die Unterschiede in einer Konfliktdatei ausgegeben. Wenn nach dem Upgrade der Wert 2007/2010Db geändert wurde und dieses Tool ausgeführt wird, wird die Ausgabe der Konfliktdatei unterschiedlich ausgegeben. Beachten Sie, dass diese Anwendung nur ein Datenbankvergleichstool ist und den Upgradeprozess nicht überprüft.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Installieren Sie die Ressourcen Kit-Tools für den beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbanken für beständigen Chat hat (frühere und aktuelle Versionen für beständigen Chat).

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Datenbanken für beständigen Chat verfügen.

Die ChatUpgradeVerifier.exe.config Datei muss entweder den GroupChat2007R2Db-Parameter oder den GroupChat2010Db-Parameter enthalten, mit einer Verbindungszeichenfolge für die entsprechende Gruppen Chat Datenbank (entweder Groupchat 2007R2 oder 2010). Es muss auch einen PersistentChat2013Db-Parameter mit einer Verbindungszeichenfolge für die Datenbank persistent Chat 2013 enthalten.

</div>

<div>

## <a name="usage"></a>Verwendung

Führen Sie **ChatUpgradeVerifier** ohne Parameter aus.

</div>

<div>

## <a name="example"></a>Beispiel

![ChatUpgradeVerifier.exe wird gestartet.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe wird gestartet.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Verwendungsbericht für beständigen Chat

<div>

## <a name="description"></a>Beschreibung

Das ChatUsageReport-Tool generiert einen HTML-Bericht über die Verwendung von beständigen Chat Diensten.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Installieren Sie die Resource Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank für beständigen Chat hat.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank für beständigen Chat verfügen.

Die Datei ChatUsageReport.exe.config muss einen Abschnitt enthalten, \<connectionStrings\> der die Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats definiert. Der Inhalt der Standardkonfigurationsdatei wird hier als Referenz aufgeführt.

</div>

<div>

## <a name="usage"></a>Verwendung

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Mit diesen Parametern wird die Auswahl der Daten definiert:

**StartDate:** Gibt optional das UTC-Startdatum des Auswahlzeitraums an. Standard: frühestes Datum

**EndDate:** Gibt optional das UTC-Enddatum des Auswahlzeitraums an. Standard: jetzt

Diese Parameter definieren, wie und welche Daten angezeigt werden:

**TopActiveUsers:** Wenn dieser Wert angegeben ist, enthält der Bericht die n aktivsten Benutzer im Hinblick auf die Anzahl der Nachrichten, die der Benutzer für den ausgewählten Zeitraum im Chatroom bereitgestellt hat. Standard: 10

**TopActiveRooms:** Wenn dieser Wert angegeben ist, enthält der Bericht die n aktivsten Chatrooms im Hinblick auf die Anzahl der Nachrichten, die im Raum für den ausgewählten Zeitraum gebucht werden. Standard: 10

**LeastActiveRooms:** Wenn dieser Wert angegeben ist, enthält der Bericht die mindestens aktiven Chatrooms im Hinblick auf die Anzahl der Nachrichten, die für den ausgewählten Zeitraum im Chatroom gepostet wurden. Für Chatrooms wird mindestens eine Nachricht bereitgestellt. Standard: 10

**RoomsInactiveSince:** Wenn dies angegeben wird, enthält der Bericht eine Liste der Chatrooms, die seit dem angegebenen Datum inaktiv sind. Standard: gesamte Zeit

**OutputFolder:** Der Ordner, in dem die ChatUsageReport.html und die Grafik Bilder eingefügt werden. Dies muss in der Konfigurationsdatei oder in der Befehlszeile definiert werden.

Alle Befehlszeilenparameter Werte können auch in der ChatUsageReport.exe.config Datei angegeben werden, die sich im gleichen Verzeichnis wie das Tool befindet. Wenn ein beliebiger Wert sowohl in der Konfigurationsdatei als auch in der Befehlszeile angegeben wird, überschreibt der Wert der Befehlszeile den Wert der Konfigurationsdatei.

</div>

<div>

## <a name="output"></a>Output

Der Bericht wird immer die folgende Ausgabe enthalten:

  - Top n die aktivsten Chatrooms nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Top n die aktivsten Benutzer nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Top n mindestens aktive Chatrooms nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Chatrooms, die für die gesamte Lebensdauer der Datenbank oder seit dem angegebenen Datum inaktiv sind.

  - Täglicher Nachrichten Post-Trend für den ausgewählten Zeitraum.

  - Trend zur wöchentlichen Nachrichten Bereitstellung für den ausgewählten Zeitraum.

  - Monatlicher Nachrichten Post-Trend für den ausgewählten Zeitraum.

  - Nachrichten Beiträge für den ausgewählten Zeitraum insgesamt.

  - Die Gesamtzahl der aktivierten Räume.

</div>

<div>

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Verwendungsbericht für das gesamte Jahr 2001 generiert, und der Bericht wird in der im ChatUsageReport.exe.config angegebenen OutputFolder platziert.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>Beschreibung

ScheduleADSyncForPrincipal ist ein Microsoft SQL Server 2012-Skript, das direkt in SQL Server Management Studio ausgeführt werden muss, wenn es mit der Back-End-Datenbank des beständigen Chats verbunden ist. Mit diesem Skript können Sie beständigen Chat zwingen, seine Einträge eines Benutzers mit denen von Active Directory-Domänendienste zu synchronisieren, anstatt auf die geplante Synchronisierungszeit zu warten.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Das Benutzerkonto, unter dem das Skript ausgeführt wird, muss über Besitzer Zugriff auf die Back-End-Datenbank für beständigen Chat verfügen.

</div>

<div>

## <a name="usage"></a>Verwendung

Im folgenden finden Sie den Inhalt des Standardskripts:

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

