---
title: 'Lync Server 2013: Vorbereiten von Active Directory-Domänendienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Vorbereiten Active Directory-Domänendienste in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-19_

In lync Server 2013 können Sie den lync Server-Bereitstellungs-Assistenten verwenden, um Active Directory-Domänendienste vorzubereiten, oder Sie können lync Server-Verwaltungsshell-Cmdlets direkt verwenden. Darüber hinaus können Sie das Befehlszeilentool "ldifde.exe" direkt für Ihre Domänencontroller ausführen, wie weiter unten in diesem Thema beschrieben.

Der Assistent für die lync Server-Bereitstellung führt Sie durch jede Active Directory Vorbereitungs Aufgabe. Der Bereitstellungs-Assistent führt lync Server-Verwaltungsshell-Cmdlets aus. Dieses Tool eignet sich für Umgebungen mit einer einzelnen Domäne und einer Topologie mit einer einzelnen Gesamtstruktur oder einer ähnlichen Topologie.

<div>


> [!IMPORTANT]  
> Sie können lync Server in einer Gesamtstruktur oder Domäne bereitstellen, in der Domänencontroller 32-Bit-Versionen einiger Betriebssysteme ausführen (Ausführliche Informationen finden Sie unter <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure Requirements for lync Server 2013</A>). Sie können jedoch nicht den lync Server-Bereitstellungs-Assistenten verwenden, um Schema-, Gesamtstruktur-und Domänenvorbereitung in diesen Umgebungen auszuführen, da der Bereitstellungs-Assistent und die unterstützenden Dateien nur 64-Bit sind. Stattdessen können Sie auf einem 32-Bit-Domänencontroller "ldifde.exe" und die zugehörigen IDF-Dateien verwenden, um das Schema, die Gesamtstruktur und die Domäne vorzubereiten. Weitere Informationen finden Sie im Abschnitt "Verwenden von Cmdlets und 'Ldifde.exe'" weiter unten in diesem Thema.



</div>

Sie können lync Server-Verwaltungsshell-Cmdlets verwenden, um Aufgaben Remote oder für komplexere Umgebungen auszuführen.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Voraussetzungen für die Active Directory-Vorbereitung

Sie müssen Active Directory Vorbereitungsschritte auf einem Computer ausführen, auf dem Windows Server 2012, Windows Server 2012 R2 oder Windows Server 2008 R2 mit SP1 (64-Bit) ausgeführt wird. Für Active Directory Vorbereitung sind lync Server-Verwaltungsshell und OCSCore erforderlich.

Zur Ausführung der Active Directory-Vorbereitungsaufgaben sind die folgenden Komponenten erforderlich:

  - Lync Server Kernkomponenten (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie lync Server-Verwaltungsshell für die Active Directory Vorbereitung verwenden möchten, müssen Sie zuerst den lync Server-Bereitstellungs-Assistenten ausführen, um Hauptkomponenten zu installieren.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Für Windows Server 2012 und Windows Server 2012 R2 installieren und aktivieren Sie .NET Framework 4.5 mit dem Server-Manager. Ausführliche Informationen finden Sie unter "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">zusätzlichen Softwareanforderungen für lync Server 2013</A>. Laden Sie für&nbsp;Windows&nbsp;Server 2008 R2 <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> von der Microsoft-Website herunter, und installieren Sie es.

    
    </div>

  - Remoteserver-Verwaltungstools (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Schritte zur Active Directory-Vorbereitung nicht auf einem Domänencontroller, sondern auf einem Mitgliedsserver ausführen, werden einige Remoteserver-Verwaltungstools benötigt. Installieren Sie die AD DS-Snap-Ins und Befehlszeilentools sowie das Active Directory-Modul für Windows PowerShell aus dem Knoten AD DS und AD LDS-Tools im Server-Manager.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Wenn diese erforderliche Komponente noch nicht auf dem Computer installiert ist, werden Sie beim Ausführen von Setup zur Installation aufgefordert. Das Paket wird Ihnen zur Verfügung gestellt, sodass Sie es nicht separat erwerben müssen.

    
    </div>

  - Windows PowerShell 3,0 (64-Bit)
    
    Für Windows Server 2012 und Windows Server 2012 R2 sollte Windows PowerShell 3,0 in ihrer lync Server 2013 Installation enthalten sein. Für Windows Server 2008 R2 müssen Sie Windows PowerShell 3,0 installieren oder ein Upgrade darauf durchführen. Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Administratorrechte und -rollen

In der folgenden Tabelle sind die Administratorrechte und -rollen aufgeführt, die für die einzelnen Aufgaben zur Active Directory-Vorbereitung erforderlich sind.

### <a name="user-rights-required-for-active-directory-preparation"></a>Erforderliche Benutzerrechte für die Vorbereitung von Active Directory

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
<td><p>Schemavorbereitung</p></td>
<td><p>Mitglied der Gruppe "Schema-Admins" für die Stammdomäne einer Gesamtstruktur und Administratorrechte für den Schemamaster</p></td>
</tr>
<tr class="even">
<td><p>Gesamtstrukturvorbereitung</p></td>
<td><p>Mitglied der Gruppe "Organisations-Admins" für die Gesamtstruktur</p></td>
</tr>
<tr class="odd">
<td><p>Domänenvorbereitung</p></td>
<td><p>Mitglied der Gruppe "Organisations-Admins" oder "Domänen-Admins" für die angegebene Domäne</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets für die Active Directory-Vorbereitung

In der folgenden Tabelle werden die lync Server-Verwaltungsshell-Cmdlets verglichen, mit denen AD DS auf die LcsCmd-Befehle zum Vorbereiten von AD DS in Microsoft Office Communications Server 2007 R2 vorbereitet werden.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets im Vergleich zu "LcsCmd"

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
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Anforderungen für gesperrtes Active Directory

Wenn die Berechtigungsvererbung deaktiviert wurde oder Berechtigungen für authentifizierte Benutzer in der Organisation deaktiviert werden müssen, sind während der Domänenvorbereitung zusätzliche Schritte erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Berechtigungen für benutzerdefinierte Container

Wenn in Ihrer Organisation statt der drei integrierten Container (Benutzer, Computer und Domänencontroller) benutzerdefinierte Container verwendet werden, muss die Gruppe der authentifizierten Benutzer über Lesezugriff für die benutzerdefinierten Container verfügen. Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Verwenden von Cmdlets und "Ldifde.exe"

Der Schritt **Schema vorbereiten** im lync Server-Bereitstellungs-Assistenten und das Cmdlet **install-CsAdServerSchema** erweitern das Active Directory Schema auf Domänencontrollern mit einem 64-Bit-Betriebssystem. Wenn Sie das Active Directory Schema auf einem Domänencontroller erweitern müssen, auf dem ein 32-Bit-Betriebssystem ausgeführt wird, können Sie das Cmdlet **install-CsAdServerSchema** Remote von einem Mitgliedsserver aus ausführen (empfohlener Ansatz). Wenn Sie die Schemavorbereitung direkt auf dem Domänencontroller ausführen müssen, können Sie das Tool LDIFDE. exe verwenden, um die Schemadateien zu importieren. Das Tool "Ldifde. exe" enthält die meisten Versionen des Windows-Betriebssystems.

Bei Verwendung von "Ldifde.exe" zum Importieren der Schemadateien, müssen Sie unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation ausführen, alle vier Dateien importieren. Die Dateien müssen mit der folgenden Reihenfolge importiert werden:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Die vier IDF-Dateien befinden sich im Verzeichnis "\Support\Schema" des Installationsmediums oder Downloads.



</div>

Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich um den Schemamaster handelt:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Beispiel:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Verwenden Sie den Parameter "b" nur, wenn Sie als ein anderer Benutzer angemeldet sind. Ausführliche Informationen zu den erforderlichen Benutzerrechten finden Sie im Abschnitt "Administratorrechte und -rollen" weiter oben in diesem Thema.



</div>

Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich nicht um den Schemamaster handelt:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ausführliche Informationen zur Verwendung von LDIFDE finden Sie im [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)Microsoft Knowledge Base-Artikel 237677, "Verwenden von LDIFDE zum Importieren und Exportieren von Verzeichnisobjekten in Active Directory" unter.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten des Active Directory Schemas in lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Vorbereiten der Gesamtstruktur auf lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

