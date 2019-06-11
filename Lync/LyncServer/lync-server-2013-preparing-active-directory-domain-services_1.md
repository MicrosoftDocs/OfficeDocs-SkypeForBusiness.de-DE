---
title: 'Lync Server 2013: Vorbereiten der Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Vorbereiten der Active Directory-Domänendienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-19_

In lync Server 2013 können Sie den lync Server-Bereitstellungs-Assistenten verwenden, um Active Directory-Domänendienste vorzubereiten, oder Sie können Cmdlets für die lync Server-Verwaltungsshell direkt verwenden. Sie können das Befehlszeilentool Ldifde. exe auch direkt auf Ihren Domänencontrollern verwenden, wie weiter unten in diesem Thema beschrieben.

Der lync Server-Bereitstellungs-Assistent führt Sie durch die einzelnen Active Directory-Vorbereitungsaufgaben. Der Bereitstellungs-Assistent führt Cmdlets der lync Server-Verwaltungsshell aus. Dieses Tool eignet sich für Umgebungen mit einer einzelnen Domäne und einer einzelnen Gesamtstrukturtopologie oder einer anderen ähnlichen Topologie.

<div>


> [!IMPORTANT]  
> Sie können lync Server in einer Gesamtstruktur oder Domäne bereitstellen, auf der Domänencontroller 32-Bit-Versionen einiger Betriebssysteme ausführen (Einzelheiten finden Sie unter <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory-Infrastrukturanforderungen für lync Server 2013</A>). Sie können den lync Server-Bereitstellungs-Assistenten jedoch nicht verwenden, um Schema-, Gesamtstruktur-und Domänenvorbereitung in diesen Umgebungen auszuführen, da der Bereitstellungs-Assistent und die unterstützenden Dateien nur 64-Bit sind. Stattdessen können Sie Ldifde. exe und die zugehörigen LDF-Dateien auf einem 32-Bit-Domänencontroller verwenden, um das Schema, die Gesamtstruktur und die Domäne vorzubereiten. Weitere Informationen finden Sie im Abschnitt "Verwenden von Cmdlets und Ldifde. exe" weiter unten in diesem Thema.



</div>

Sie können Cmdlets der lync Server-Verwaltungsshell verwenden, um Aufgaben Remote oder für komplexere Umgebungen auszuführen.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Voraussetzungen für die Active Directory-Vorbereitung

Sie müssen Active Directory-Vorbereitungsschritte auf einem Computer ausführen, auf dem Windows Server 2012, Windows Server 2012 R2 oder Windows Server 2008 R2 mit SP1 (64-Bit) ausgeführt wird. Für die Active Directory-Vorbereitung ist die lync Server-Verwaltungsshell und OCSCore erforderlich.

Zum Ausführen von Active Directory-Vorbereitungsaufgaben sind die folgenden Komponenten erforderlich:

  - Lync Server Core Components (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie beabsichtigen, die lync Server-Verwaltungsshell für die Active Directory-Vorbereitung zu verwenden, müssen Sie zuerst den lync Server-Bereitstellungs-Assistenten ausführen, um Kernkomponenten zu installieren.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Für Windows Server 2012 und Windows Server 2012 R2 installieren und aktivieren Sie .NET Framework 4,5 mithilfe des Server-Managers. Ausführliche Informationen finden Sie unter "Microsoft .NET Framework 4,5" unter <A href="lync-server-2013-additional-software-requirements.md">zusätzliche Softwareanforderungen für lync Server 2013</A>. Für Windows Server&nbsp;2008&nbsp;R2 laden Sie <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> von der Microsoft-Website herunter, und installieren Sie es.

    
    </div>

  - Remote Server-Verwaltungs Tools (Remote Server)
    
    <div>
    

    > [!NOTE]  
    > Einige Tools für Remotetools sind erforderlich, wenn Sie Active Directory-Vorbereitungsschritte auf einem Mitgliedsserver statt auf einem Domänencontroller ausführen. Installieren Sie die AD DS-Snap-Ins und-Befehlszeilentools sowie das Active Directory-Modul für Windows PowerShell über den Knoten AD DS und AD LDS-Tools im Server-Manager.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Setup fordert Sie auf, diese Voraussetzungen zu installieren, wenn Sie noch nicht auf dem Computer installiert sind. Das Paket wird für Sie bereitgestellt, und Sie müssen es nicht separat erwerben.

    
    </div>

  - Windows PowerShell 3,0 (64-Bit)
    
    Für Windows Server 2012 und Windows Server 2012 R2 sollte Windows PowerShell 3,0 in ihrer lync Server 2013-Installation enthalten sein. Für Windows Server 2008 R2 müssen Sie Windows PowerShell 3,0 installieren oder aktualisieren. Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Administrator Rechte und-Rollen

In der folgenden Tabelle sind die Administratorrechte und-Rollen aufgeführt, die für die einzelnen Active Directory-Vorbereitungsaufgaben erforderlich sind.

### <a name="user-rights-required-for-active-directory-preparation"></a>Für die Active Directory-Vorbereitung erforderliche Benutzerrechte

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Verfahren</th>
<th>Rechte oder Rollen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Schema Vorbereitung</p></td>
<td><p>Mitglied der Gruppe "Schemaadministratoren" für die Gesamtstruktur-Stammdomäne und Administratorrechte für den Schemamaster</p></td>
</tr>
<tr class="even">
<td><p>Gesamtstrukturvorbereitung</p></td>
<td><p>Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur</p></td>
</tr>
<tr class="odd">
<td><p>Domänenvorbereitung</p></td>
<td><p>Mitglied der Gruppe "Unternehmensadministratoren" oder "Domänen-Admins" für die angegebene Domäne</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets für die Active Directory-Vorbereitung

In der folgenden Tabelle werden die Cmdlets der lync Server-Verwaltungsshell verglichen, die zum Vorbereiten von AD DS auf die LcsCmd-Befehle zum Vorbereiten von AD DS in Microsoft Office Communications Server 2007 R2 verwendet werden.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets im Vergleich zu LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlets</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>LcsCmd/Forest/Action: SchemaPrep/SchemaType: Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>LcsCmd/Forest/Action: CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Deaktivieren-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Deaktivieren-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Active Directory-Anforderungen gesperrt

Wenn die Vererbung von Berechtigungen deaktiviert ist oder die Berechtigungen für authentifizierte Benutzer in Ihrer Organisation deaktiviert werden müssen, müssen Sie während der Domänenvorbereitung weitere Schritte ausführen. Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Benutzerdefinierte Container Berechtigungen

Wenn in Ihrer Organisation benutzerdefinierte Container anstelle der drei integrierten Container (also Benutzer, Computer und Domänencontroller) verwendet werden, müssen Sie den benutzerdefinierten Containern Lesezugriff für die Gruppe Authentifizierte Benutzer erteilen. Für die Domänenvorbereitung ist Lesezugriff auf die Container erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Verwenden von Cmdlets und Ldifde. exe

Der Schritt " **Schema vorbereiten** " im lync Server-Bereitstellungs-Assistenten und dem Cmdlet " **install-CsAdServerSchema** " erweitern das Active Directory-Schema auf Domänencontrollern, auf denen ein 64-Bit-Betriebssystem ausgeführt wird. Wenn Sie das Active Directory-Schema auf einem Domänencontroller erweitern müssen, auf dem ein 32-Bit-Betriebssystem ausgeführt wird, können Sie das Cmdlet " **Installieren-CsAdServerSchema** " Remote von einem Mitgliedsserver ausführen (empfohlener Ansatz). Wenn Sie die Schemavorbereitung aber direkt auf dem Domänencontroller ausführen müssen, können Sie die Schemadateien mit dem Tool "Ldifde. exe" importieren. Das Tool "Ldifde. exe" umfasst die meisten Versionen des Windows-Betriebssystems.

Wenn Sie die Schemadateien mithilfe von Ldifde. exe importieren, müssen Sie alle vier Dateien importieren, unabhängig davon, ob Sie eine frühere Version migrieren oder eine Neuinstallation durchführen. Sie müssen Sie in der folgenden Reihenfolge importieren:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Die vier LDF-Dateien befinden sich im \Support\Schema-Verzeichnis Ihres Installationsmediums oder herunterladen.



</div>

Wenn Sie Ldifde. exe verwenden möchten, um die vier Schemadateien auf einem Domänencontroller zu importieren, bei dem es sich um den Schemamaster handelt, verwenden Sie das folgende Format:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Beispiel:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Verwenden Sie den Parameter b nur, wenn Sie als anderer Benutzer angemeldet sind. Details zu den erforderlichen Benutzerrechten finden Sie weiter oben in diesem Thema im Abschnitt "Administrator Rechte und-Rollen".



</div>

Wenn Sie Ldifde. exe verwenden möchten, um die vier Schemadateien auf einem Domänencontroller zu importieren, bei dem es sich nicht um den Schemamaster handelt, verwenden Sie das folgende Format:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ausführliche Informationen zur Verwendung von LDIFDE finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)Microsoft Knowledge Base-Artikel 237677, "Verwenden von LDIFDE zum Importieren und Exportieren von Verzeichnisobjekten in Active Directory" unter.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

