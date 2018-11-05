---
title: Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst mithilfe von PowerShell
TOCTitle: Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst mithilfe von PowerShell
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49891016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst mithilfe von PowerShell

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der Zentraler Protokollierungsdienst wird durch Einstellungen und Parameter gesteuert und konfiguriert, die vom Zentraler Protokollierungsdienst-Controller (CLSController) erstellt und verwendet werden, um Befehle an den Zentraler Protokollierungsdienst-Agent (CLSAgent) des einzelnen Computers zu senden. Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Falle eines Start-Befehls) die Konfiguration der Szenarios, Anbieter, Protokollgröße, Ablaufverfolgungsdauer und Flags, um mit der Erfassung von Ablaufverfolgungsprotokollen gemäß den bereitgestellten Konfigurationsinformationen zu beginnen.


> [!IMPORTANT]
> Nicht alle Windows PowerShell-Cmdlets, die für den Zentraler Protokollierungsdienst aufgelistet werden, sind für die Verwendung mit lokalen Lync Server 2013-Bereitstellungen vorgesehen. Auch wenn die folgenden Cmdlets scheinbar funktionieren, sind sie nicht für die Ausführung mit lokalen Lync Server 2013-Bereitstellungen entwickelt worden: 
> <UL>
> <LI>
> <P><STRONG>"CsClsRegion"-Cmdlets:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsRegion">Get-CsClsRegion</A>, <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsRegion">Set-CsClsRegion</A>, <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsRegion">New-CsClsRegion</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsRegion">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>"CsClsSearchTerm"-Cmdlets:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSearchTerm">Get-CsClsSearchTerm</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSearchTerm">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>"CsClsSecurityGroup"-Cmdlets:</STRONG> <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsSecurityGroup">Get-CsClsSecurityGroup</A>, <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsSecurityGroup">Set-CsClsSecurityGroup</A>, <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsSecurityGroup">New-CsClsSecurityGroup</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsSecurityGroup">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Die in diesen Cmdlets definierten Einstellungen können ein nachteiliges Verhalten weder verhindern noch verursachen, sind aber für die Verwendung mit Microsoft Office 365 vorgesehen und liefern in lokalen Bereitstellungen nicht die erwarteten Ergebnisse. Das bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht von Nutzen sind, ihre Verwendung ist aber ein komplexes Thema, dessen Beschreibung den Rahmen dieser Dokumentation sprengen würde.



## In diesem Abschnitt

In den Themen in diesem Abschnitt werden die Konfigurationsoptionen, Parameter und Einstellungen für den Zentraler Protokollierungsdienst behandelt. Informationen zum Konfigurieren des Zentraler Protokollierungsdiensts, Abrufen der Konfigurationseinstellungen, Erstellen von Szenarios, Verwalten von Sicherheitsgruppen für den Zentraler Protokollierungsdienst, Durchführen von Suchläufen usw. finden Sie in den folgenden Themen.

  - [Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst auf Computer-, Standort- und globaler Ebene](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

## Siehe auch

#### Konzepte

[Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets für die zentralisierte Protokollierung](https://docs.microsoft.com/en-us/powershell/module/skype/)

