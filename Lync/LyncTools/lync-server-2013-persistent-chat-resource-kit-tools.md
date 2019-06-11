---
title: Lync Server 2013-Ressourcensatz Tools für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013-Ressourcensatz Tools für beständigen Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Die lync Server 2013-Tools für beständigen Chat-Ressourcen Kits unterstützen Sie bei der Vereinfachung von Routineaufgaben für IT-Administratoren, die lync Server 2013 persistent Chat Server bereitstellen und verwalten. In diesem Thema werden neben den Installationsanweisungen auch der Zweck der einzelnen Tools und Beispiele für deren Verwendung beschrieben.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Zum Installieren der lync Server 2013, Resource Kit-Tools, laden Sie **PersistentChatReskit. msi**herunter. Führen Sie **PersistentChatReskit. msi** aus, um eine einfache Installation durchzuführen. Mit der MSI-Datei werden alle Tools im folgenden Pfad installiert \\: **Programm\\ Dateien Microsoft lync Server\\2013 beständiger Chat Server Resource Kit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.

<div>


> [!IMPORTANT]  
> Nachdem Sie die lync Server 2013, Resource Kit-Tools installiert haben, müssen Sie <STRONG>PsExec. exe</STRONG> installieren und " <STRONG>PsExec. exe</STRONG> " in \\den folgenden Pfad kopieren: <STRONG>Programmdateien \ Microsoft lync Server 2013 \ beständiger Chat Server Ressource Kit\ChatStressTool </STRONG>. Wenn Sie " <STRONG>PsExec. exe</STRONG>" nicht kopieren, löst das beständige Chat-Spannungs Tool eine Fehler Ausnahme aus, die nicht ordnungsgemäß ausgeführt wird. Stellen Sie sicher, dass Sie diese Voraussetzungen erfüllen, bevor Sie das Tool ausführen. Informationen zum Installieren von <STRONG>PsExec. exe</STRONG>finden Sie <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>unter.



</div>

</div>

<div>

## <a name="supported-environments"></a>Unterstützte Umgebungen

Um eine optimale Leistung zu erzielen, sollten die lync Server 2013, Resource Kit-Tools in der gleichen Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools – Übersicht

Nachfolgend finden Sie die Tools, die im lync Server 2013-Ressourcen Kit für beständige Chats bereitgestellt werden. Der folgende Abschnitt enthält eine Beschreibung der einzelnen Tools, einschließlich Anforderungen und Beispiel Verwendung.

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

Das AffCheck-Tool bestätigt, dass die Datensätze des beständigen Chat-Datenbankbenutzers und der Gruppenzugehörigkeit mit denen der Active Directory-Domänendienste übereinstimmen.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Das Tool wird mit dem PersistentChatResKit-Installationsprogramm auf einem Computer mit Domänenbeitritt installiert.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank des beständigen Chats und die Active Directory-Domänendienste verfügen.

</div>

<div>

## <a name="usage"></a>Verwendung

Konfigurieren Sie die Datei "AffCheck. exe. config" gemäß den Anweisungen in der config-Datei, und führen Sie das AffCheck-Tool ohne Befehlszeilenparameter aus. Im folgenden finden Sie den Inhalt der standardmäßigen Datei "AffCheck. exe. config".

**AffCheck. exe. config:**

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

Das PersistentChatMonitoringSummary-Tool verschiebt permanente Chat Überwachungsinformationen aus der Überwachungsdatenbank in eine angegebene CSV-Protokolldatei.

Die CSV-Datei enthält eine Aufschlüsselung der beständigen Chat Sitzungen nach Anzahl der Gesamt Sitzungen, erfolgreichen Sitzungen, unerwarteten Fehlern, erwarteten Fehlern und einer Aufschlüsselung der unerwarteten Fehler durch Diagnose-ID, Anzahl der Fehler und Fehlerbeschreibung.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Überwachungsdatenbank hat.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Überwachungsdatenbank verfügen.

Die Datei "PersistentChatMonitoringSummary. exe. config \<\> " muss einen connectionStrings-Abschnitt enthalten, der die Verbindungszeichenfolge zur Überwachungsdatenbank definiert. Darüber hinaus muss ein Schlüssel für das PersistentChatEndpointUri-Objekt enthalten sein, für das die Überwachungsdaten gesammelt werden, und ein Dateipfad zu einem Speicherort für die CSV-Datei, die generiert wird. Beispiele finden Sie in der installierten Konfigurationsdatei. Die Datei muss sich im gleichen Verzeichnis wie das Tool befinden.

</div>

<div>

## <a name="usage"></a>Verwendung

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Diese Parameter definieren die Auswahl der Daten:

Start **Datum:** Gibt optional das Startdatum des Auswahlzeitraums an. Standard: 1/1/1753 12:00:00 am

**Enddatum:** Gibt optional das letzte Datum des Auswahlzeitraums an. Standard: jetzt

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

Das Stress Tool für beständigen Chat bietet eine einfache Möglichkeit, die Nutzung von beständigem Chat zu simulieren, um die Leistung in der realen Welt zu testen, einschließlich unterschiedlicher Benutzermodelle, die ihren erwarteten Nutzungsszenarien besser entsprechen.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank des beständigen Chats hat.

Zusätzlich zu diesem *Controller* -Computer sind mehrere *Loader* -Maschinen erforderlich. Für alle 10K-Benutzer in Ihrem Benutzermodell benötigen Sie mindestens 4 GB freien RAM auf einem Loader-Computer. Beispielsweise erfordert ein Run mit 80K-Benutzern etwa 32 GB Arbeitsspeicher, die auf allen Loader-Computern verbreitet werden. Wir empfehlen, dass Sie über mindestens drei Ladegeräte verfügen, unabhängig von der erwarteten Auslastung.

Loader-Computer müssen das .NET 4,5-Framework sowie die Visual C++ 2012-verteilbare Version installiert haben.

</div>

<div>

## <a name="configuration"></a>Konfiguration

Kopieren Sie ChatStressTool-Dateien in einen freigegebenen Ordner, auf den alle Loader-Computer zugreifen können.

Erstellen von Benutzern und Kanälen zur Verwendung im Spannungsverlauf:

  - Erstellen Sie so viele Benutzer, wie Sie von Ihrem Benutzermodell aufgerufen werden, aktivieren Sie diese für lync, und legen Sie die Richtlinie für beständigen Chat auf aktiviert fest.

  - Erstellen Sie eine Kategorie für Ihre Spannungskanäle, und erstellen Sie dann so viele Räume, wie Sie unter dieser Kategorie benötigt werden. In der Kategorie sollten alle Belastungs Benutzer in **** der Liste der zulässigen Daten enthalten sein (indem Sie Ihre OU hinzufügen), und bei den Belastungs Räumen sollte eine Privatsphäre-Einstellung **geöffnet**sein.

  - Wir empfehlen, zusätzliche Belastungs Räume zu erstellen. Sie können 50.000-Räume mit dem folgenden Befehlszeilen-Schnittstellenbefehl der Windows PowerShell erstellen:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Bearbeiten Sie die Konfigurationsdateien so, dass Sie in Ihre Topologie passen:

Ändern Sie in **LoaderProcess. exe. config**"Controller.contoso.com" in den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Controllers.

In **StressLauncher. exe. config:**

1.  Ändern Sie den Wert für die Einstellung "LoaderBinary" in den Pfad des freigegebenen Ordners.

2.  Ändern Sie "abzüglicher"/"AdminPassword" in Anmeldeinformationen, die Administratorzugriff auf Loader-Computer haben.

3.  Ändern Sie "ChannelCategory" in den Namen der Kategorie, unter der Spannungskanäle erstellt wurden.

4.  Ändern Sie "UserNamePattern" und "UserPasswordPattern" in eine Vorlage, die Ihren Stress-Benutzeranmeldeinformationen entspricht. {0}wird durch die Indexnummer des Benutzers ersetzt.

5.  Ändern Sie "Domäne" in die SIP-Domäne ihrer Testtopologie.

6.  Ändern Sie "ConnectionString" in eine Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats.

7.  Ändern Sie "UserIndexStart" in den Index des ersten Belastungs Benutzers.

8.  Ändern Sie "LyncFQDN" in den FQDN des Front-End-Pools.

9.  Ändern Sie die Liste "Computer", um Computernamen für alle Ladegeräte Computer einzubeziehen.

10. Ändern Sie die BaseAddress des Dienstendpunkts (Standard ist "Controller.contoso.com") auf den FQDN Ihres Controllercomputers.

</div>

<div>

## <a name="usage"></a>Verwendung

Öffnen Sie nach Abschluss der Konfiguration StressLauncher. exe auf dem Controllercomputer. Sie können StressLauncher als beliebigen Benutzer starten. Die Anmeldeinformationen, unter denen die Loader-Prozesse auf den Loader-Computern gestartet werden, müssen in der config-Datei angegeben werden. Sie müssen auch eine Verbindungszeichenfolge angeben, die über Lesezugriff auf die Back-End-Datenbank des beständigen Chats verfügt. Wenn diese Verbindungszeichenfolge die integrierte Windows-Authentifizierung verwendet, müssen Sie StressLauncher als Benutzer mit diesem Zugriff starten.

Ändern Sie die Benutzermodell Einstellungen nach Bedarf. Klicken Sie auf **Load starten** , um einen Testlauf zu initiieren. Nach ungefähr einer Minute werden die Benutzer angemeldet, und die Statusleiste beginnt zu füllen. An diesem Punkt können Sie den Controller-Computer verwenden und Leistungsmessungen durchführen.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Beschreibung

ChatUpgradeVerifier ist ein beständiger Chat-spezifischer Datenbankvergleichstool. Das Tool vergleicht entweder die Gruppen-Chat-2007 R2-oder Gruppen-Chat 2010-Datenbank (2007/2010Db) mit der beständigen Chat-2013-Datenbank (2013Db).

Das Tool überprüft einzeln jede Kategorie, beständigen Chatroom und Add-in in 2007/2010Db, um festzustellen, ob Sie im 2013Db angezeigt wird. Der Vergleich umfasst die Überprüfung aller Einstellungen für die Kategorie, den Chatroom oder das Add-in, alle Prinzipale im Bereich der Kategorie sowie alle Prinzipale in einer Rolle in der Kategorie oder im Chatroom. Wenn eine Kategorie oder ein Chatroom im 2013Db nicht richtig angezeigt wird, werden die Unterschiede in einer Konfliktdatei ausgegeben. Wenn nach dem Upgrade die Version 2007/2010Db geändert wird und dann dieses Tool ausgeführt wird, gibt es Unterschiede, die in der Dateikonflikte ausgegeben werden. Beachten Sie, dass diese Anwendung nur ein Tool zum Vergleichen von Datenbanken ist und den Upgradeprozess nicht überprüft.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbanken des beständigen Chats (frühere und aktuelle Versionen für beständigen Chat) hat.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die persistenten Chat Datenbanken verfügen.

Die Datei "ChatUpgradeVerifier. exe. config" muss entweder den GroupChat2007R2Db-Parameter oder den GroupChat2010Db-Parameter enthalten, mit einer Verbindungszeichenfolge zur entsprechenden Gruppen Chat Datenbank (entweder Groupchat 2007R2 oder 2010). Sie muss auch einen PersistentChat2013Db-Parameter mit einer Verbindungszeichenfolge zur 2013-Datenbank des beständigen Chats enthalten.

</div>

<div>

## <a name="usage"></a>Verwendung

Führen Sie **ChatUpgradeVerifier** ohne Parameter aus.

</div>

<div>

## <a name="example"></a>Beispiel

![Ausführen von ChatUpgradeVerifier. exe.] (images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Ausführen von ChatUpgradeVerifier. exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Verwendungsbericht für beständigen Chat

<div>

## <a name="description"></a>Beschreibung

Das ChatUsageReport-Tool generiert einen HTML-Bericht zur Verwendung des beständigen Chat Diensts.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die Ressourcen Kit-Tools für beständigen Chat auf einem Computer mit Domänenbeitritt, der Zugriff auf die Back-End-Datenbank des beständigen Chats hat.

Das Benutzerkonto, unter dem das Tool ausgeführt wird, muss über Lesezugriff auf die Back-End-Datenbank des beständigen Chats verfügen.

Die Datei "ChatUsageReport. exe. config \<\> " muss einen connectionStrings-Abschnitt enthalten, der die Verbindungszeichenfolge für die Back-End-Datenbank des beständigen Chats definiert. Der Inhalt der Standardkonfigurationsdatei wird hier als Referenz angegeben.

</div>

<div>

## <a name="usage"></a>Verwendung

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Diese Parameter definieren die Auswahl der Daten:

**StartDate:** Gibt optional das UTC-Anfangsdatum des Auswahlzeitraums an. Standard: frühestes Datum

**EndDate:** Gibt optional das UTC-Enddatum des Auswahlzeitraums an. Standard: jetzt

Diese Parameter definieren, wie und welche Daten angezeigt werden:

**TopActiveUsers:** Wenn dies angegeben ist, enthält der Bericht die n meisten aktiven Benutzer in Bezug auf die Anzahl der Nachrichten, die der Benutzer im Chatroom für den ausgewählten Zeitraum gepostet hat. Standard: 10

**TopActiveRooms:** Wenn dies angegeben ist, enthält der Bericht die n aktivsten Chatrooms in Bezug auf die Anzahl der Nachrichten, die in dem Raum für den ausgewählten Zeitraum gepostet wurden. Standard: 10

**LeastActiveRooms:** Wenn dieser Wert angegeben wird, enthält der Bericht die mindestens aktiven Chatrooms in Bezug auf die Anzahl der Nachrichten, die im Chatroom für den ausgewählten Zeitraum gepostet wurden. Für Chatrooms wird mindestens eine Nachricht bereitgestellt. Standard: 10

**RoomsInactiveSince:** Wenn dieser Wert angegeben wird, enthält der Bericht eine Liste der Chatrooms, die seit dem angegebenen Datum inaktiv sind. Standard: ganze Zeit

**OutputFolder:** Der Ordner, in dem die ChatUsageReport. html-und die Graph-Bilder abgelegt werden. Dies muss in der config-Datei oder in der Befehlszeile definiert werden.

Alle Befehlszeilenparameter Werte können auch in der Datei "ChatUsageReport. exe. config" angegeben werden, die sich im gleichen Verzeichnis wie das Tool befindet. Wenn ein beliebiger Wert sowohl in der config-Datei als auch in der Befehlszeile angegeben wird, wird der Wert der config-Datei durch den Befehlszeilenwert überschrieben.

</div>

<div>

## <a name="output"></a>Ausgabe

Der Bericht enthält immer die folgende Ausgabe:

  - Die meisten aktiven Chatrooms nach Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Die meisten aktiven Benutzer nach der Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Top n least Active Chatrooms nach Anzahl der Nachrichten Beiträge für den ausgewählten Zeitraum.

  - Chatrooms, die für die gesamte Lebensdauer der Datenbank oder seit dem angegebenen Datum inaktiv sind.

  - Täglicher Nachrichten-Trend für ausgewählten Zeitraum.

  - Wöchentlicher Nachrichten Post-Trend für ausgewählten Zeitraum.

  - Monatlicher Nachrichten-Post-Trend für ausgewählten Zeitraum.

  - Nachrichten Beiträge für ausgewählten Zeitraum insgesamt.

  - Die Gesamtzahl der aktivierten Chatrooms.

</div>

<div>

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Nutzungsbericht für das gesamte Jahr 2001 generiert, und der Bericht wird in der in der Datei "ChatUsageReport. exe. config" angegebenen OutputFolder platziert.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport. exe. config:

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

ScheduleADSyncForPrincipal ist ein Microsoft SQL Server 2012-Skript, das direkt in SQL Server Management Studio ausgeführt werden muss, wenn eine Verbindung mit der Back-End-Datenbank des beständigen Chats besteht. Mit diesem Skript können Sie beständigen Chat zwingen, seine Einträge eines Benutzers mit denen der Active Directory-Domänendienste zu synchronisieren, anstatt auf die geplante Synchronisierungszeit zu warten.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Das Benutzerkonto, unter dem das Skript ausgeführt wird, muss über Besitzer Zugriff auf die Back-End-Datenbank des beständigen Chats verfügen.

</div>

<div>

## <a name="usage"></a>Verwendung

Im folgenden finden Sie die Inhalte des Standardskripts:

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

