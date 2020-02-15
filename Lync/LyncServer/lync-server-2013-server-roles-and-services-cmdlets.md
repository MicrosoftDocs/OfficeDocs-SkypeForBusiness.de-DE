---
title: 'Lync Server 2013: Cmdlets für Server Rollen und Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7b44cb01ed5ff967f47d46bffa833fe5007ff6f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a>Cmdlets für Server Rollen und Dienste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-29_

Viele Microsoft lync Server 2013-Komponenten werden als Server Rollen oder als Dienste ausgeführt. Lync Server 2013 wird mit einer Reihe von Cmdlets ausgeliefert, mit denen Sie diese Server Rollen und-Dienste verwalten können.

<div>

## <a name="server-roles-and-services-cmdlets"></a>Cmdlets für Serverrollen und -dienste

Viele (aber nicht alle) Verwaltungsaufgaben, die für Server und Dienstrollen gelten, können in der lync Server-Systemsteuerung ausgeführt werden. Beispielsweise können Sie Archivierungsserver Einstellungen verwalten, jedoch keine Adressbuch Server Einstellungen mithilfe von lync Server-Systemsteuerung. Allerdings können alle diese Aufgaben mit Cmdlets aus dem lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden; mit einem Skript können Sie bestimmte Aufgaben automatisieren. Im folgenden finden Sie eine Liste der Cmdlets, die direkt mit der Verwaltung von Serverrollen und-Diensten in Zusammenhangstehen:

**[Cmdlets für den Adressbuch Server in lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Gruppe-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-csaddressbookreplication "](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

**[Cmdlets für Archivierung und Überwachung in lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**

  - <span></span>  
    [Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - <span></span>  
    [New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Gruppe-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - <span></span>  
    [New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Gruppe-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - <span></span>  
    [New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Gruppe-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - <span></span>  
    [New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - <span></span>  
    [Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Gruppe-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - <span></span>  
    [Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csreportingconfiguration "](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - <span></span>  
    [New-csreportingconfiguration "](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - <span></span>  
    [Remove-csreportingconfiguration "](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - <span></span>  
    [Gruppe-csreportingconfiguration "](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Gruppe-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - <span></span>  
    [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Gruppe-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - <span></span>  
    [Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csextendedtest "](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

**[Cmdlets für Database und Management Server in lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**

  - <span></span>  
    [Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - <span></span>  
    [Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - <span></span>  
    [Gruppe-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - <span></span>  
    [Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - <span></span>  
    [Deinstallieren-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

<!-- end list -->

  - [Invoke-csdatabasefailover "](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

<!-- end list -->

  - [Get-csdatabasemirrorstate "](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

<!-- end list -->

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Deinstallieren-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - <span></span>  
    [Gruppe-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - <span></span>  
    [Gruppe-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

<!-- end list -->

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

**[Edgeserver-Cmdlets in lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**

  - <span></span>  
    [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Gruppe-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - <span></span>  
    [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Gruppe-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csavedgeconnectivity "](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

**[Weitere Cmdlets für Serverrollen in lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**

  - <span></span>  
    [Gruppe-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

**[Cmdlets für Registrierungsstellen und Directors in lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**

  - <span></span>  
    [Gruppe-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - <span></span>  
    [New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - <span></span>  
    [Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - <span></span>  
    [Gruppe-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

**[Cmdlets für Dienste in lync Server 2013](lync-server-2013-services-cmdlets.md)**

  - <span></span>  
    [Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - <span></span>  
    [Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - <span></span>  
    [Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

**[Problembehandlung für Serverrollen und-Dienste-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Gruppe-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - <span></span>  
    [New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Gruppe-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

**[Cmdlets für Webserver und Dienste in lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**

  - <span></span>  
    [New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - <span></span>  
    [New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - <span></span>  
    [Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - <span></span>  
    [Gruppe-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - <span></span>  
    [New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - <span></span>  
    [Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - <span></span>  
    [Gruppe-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Gruppe-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server PowerShell-Blog](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

