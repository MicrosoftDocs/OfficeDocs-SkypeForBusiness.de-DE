---
title: Konfigurieren des Mobilitätsdiensts für hohe Leistung
TOCTitle: Konfigurieren des Mobilitätsdiensts für hohe Leistung
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690042(v=OCS.15)
ms:contentKeyID: 49295315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Mobilitätsdiensts für hohe Leistung

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Wenn Sie den Lync Server 2013-Mobilitätsdienst unter Internetinformationsdienste (Internet Information Services, IIS) 7.5 installieren, konfiguriert der Mobilitätsdienst-Installer einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Wenn Sie IIS 7.0 unter Windows Server 2008 verwenden, müssen Sie diese Einstellungen manuell konfigurieren. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.

Die Leistungseinstellungen lauten wie folgt:

  - **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.

  - **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.

  - Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.

  - Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.

Wenn Sie IIS 7.0 verwenden, wird empfohlen, das Update aus dem Microsoft Knowledge Base-Artikel 2290617 "Update: Ein Hotfix ist verfügbar, um die Konfiguration von einigen ASP.NET-Eigenschaften für jeden Anwendungspool in IIS 7.0 zu aktivieren" unter <http://support.microsoft.com/kb/2290617/de-de> zu installieren, sodass Sie die Änderungen nur für den Mobilitätsdienst übernehmen können, ohne dass andere Webdienste davon betroffen sind.

Die folgende Vorgehensweise beschreibt, wie Sie die ASP.NET-Limits für die maximale Anzahl gleichzeitiger Anforderungen und Threads unter IIS 7.0 ändern können, wenn Sie das Update aus Knowledge Base-Artikel 2290617 nicht installieren. Aber auch wenn Sie das Update aus Knowledge Base-Artikel 2290617 installieren, sollten Sie gemäß der Dokumentation des Artikels dieselben Änderungen nur auf die internen und externen IIS-Anwendungspools des Mobilitätsdienst anwenden. In diesem Fall verwenden Sie eine separate Konfigurationsdatei für die ASP.NET-Einstellungen.


> [!IMPORTANT]
> Wenn Sie das folgende Verfahren zum Ändern der maximalen Anzahl verwenden, wirken sich die Änderungen auf alle IIS-Anwendungspools aus.



Ausführliche Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [http://go.microsoft.com/fwlink/?linkid=234537\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=234537%26clcid=0x407).

## So ändern Sie die maximale Anzahl gleichzeitiger Anforderungen und Threads

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Feld **Ausführen** Folgendes ein:
    
        notepad %SystemRoot%\Microsoft.NET\Framework64\v2.0.50727\Aspnet.config

3.  Klicken Sie auf **OK**.

4.  Fügen Sie der Datei Aspnet.config das folgende \<system.web\>-Element als untergeordnetes \<configuration\>-Element hinzu, oder ersetzen Sie das vorhandene Element:
    
        <system.web>
        <applicationPool maxConcurrentRequestsPerCPU="<#>" maxConcurrentThreadsPerCPU="0" requestQueueLimit="5000"/>
        </system.web>
    
    Wobei \# = 0 ist, um das Limit oder die neue Anzahl zu entfernen, so wie weiter oben in diesem Abschnitt beschrieben.

5.  Speichern Sie die Datei Aspnet.config, und schließen Sie Editor.

