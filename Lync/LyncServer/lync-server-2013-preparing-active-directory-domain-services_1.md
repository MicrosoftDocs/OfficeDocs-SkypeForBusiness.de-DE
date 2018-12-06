---
title: 'Lync Server 2013: Vorbereiten der Active Directory-Domänendienste'
TOCTitle: Vorbereiten der Active Directory-Domänendienste
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398607(v=OCS.15)
ms:contentKeyID: 49294499
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten der Active Directory-Domänendienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können zur Vorbereitung von Active Directory-Domänendienste den Lync Server-Bereitstellungs-Assistenten in Lync Server 2013 oder direkt die Cmdlets der Lync Server-Verwaltungsshell verwenden. Darüber hinaus können Sie das Befehlszeilentool "ldifde.exe" direkt für Ihre Domänencontroller ausführen, wie weiter unten in diesem Thema beschrieben.

Der Lync Server-Bereitstellungs-Assistent leitet Sie durch die einzelnen Aufgaben zur Active Directory-Vorbereitung. Der Bereitstellungs-Assistent führt die Cmdlets der Lync Server-Verwaltungsshell aus. Dieses Tool ist nützlich für Umgebungen mit einer einzelnen Domäne und Gesamtstrukturtopologie bzw. einer anderen ähnlichen Topologie.


> [!IMPORTANT]
> Sie können Lync Server in einer Gesamtstruktur oder Domäne mit Domänencontrollern bereitstellen, auf denen 32-Bit-Versionen einiger Betriebssysteme ausgeführt werden (ausführliche Informationen finden Sie unter <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory-Infrastrukturanforderungen für Lync Server 2013</A>). Sie können den Lync Server-Bereitstellungs-Assistenten jedoch nicht zum Ausführen der Schema-, Gesamtstruktur- und Domänenvorbereitung in diesen Umgebungen verwenden, da dieses Tool und unterstützende Dateien nur für 64-Bit-Betriebssysteme verwendet werden können. Stattdessen können Sie auf einem 32-Bit-Domänencontroller "ldifde.exe" und die zugehörigen IDF-Dateien verwenden, um das Schema, die Gesamtstruktur und die Domäne vorzubereiten. Weitere Informationen finden Sie im Abschnitt "Verwenden von Cmdlets und 'Ldifde.exe'" weiter unten in diesem Thema.



Sie können die Cmdlets der Lync Server-Verwaltungsshell verwenden, um Aufgaben remote oder für komplexere Umgebungen auszuführen.

## Voraussetzungen für die Active Directory-Vorbereitung

Sie müssen auf einem Computer mit Windows Server 2012, Windows Server 2012 R2 oder Windows Server 2008 R2 mit SP1 (64 Bit) Schritte zur Active Directory-Vorbereitung ausführen. Für die Active Directory-Vorbereitung sind die Lync Server-Verwaltungsshell und OCSCore erforderlich.

Zur Ausführung der Active Directory-Vorbereitungsaufgaben sind die folgenden Komponenten erforderlich:

  - Die Lync Server-Hauptkomponenten (OCScore.msi)
    

    > [!NOTE]
    > Wenn Sie die Lync Server-Verwaltungsshell zur Active Directory-Vorbereitung verwenden möchten, müssen Sie zunächst mithilfe des Lync Server-Bereitstellungs-Assistenten die Hauptkomponenten installieren.



  - Microsoft .NET Framework 4.5
    

    > [!NOTE]
    > Für Windows Server 2012 und Windows Server 2012 R2 wird .NET Framework&nbsp;4.5 über den Server-Manager installiert und aktiviert. Ausführliche Informationen finden Sie unter "Microsoft .NET Framework&nbsp;4.5" in <A href="lync-server-2013-additional-software-requirements.md">Zusätzliche Softwareanforderungen für Lync Server 2013</A>. Für Windows Server&nbsp;2008&nbsp;R2 müssen Sie <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework&nbsp;4.5</A> von der Microsoft-Website herunterladen und installieren.



  - Remoteserver-Verwaltungstools (RSAT)
    

    > [!NOTE]
    > Wenn Sie die Schritte zur Active Directory-Vorbereitung nicht auf einem Domänencontroller, sondern auf einem Mitgliedsserver ausführen, werden einige Remoteserver-Verwaltungstools benötigt. Installieren Sie die AD&nbsp;DS-Snap-Ins und Befehlszeilentools sowie das Active Directory-Modul für die Windows PowerShell über den Knoten mit den AD&nbsp;DS- und AD&nbsp;LDS-Tools im Server-Manager.



  - Microsoft Visual C++ 11 Redistributable
    

    > [!NOTE]
    > Wenn diese erforderliche Komponente noch nicht auf dem Computer installiert ist, werden Sie beim Ausführen von Setup zur Installation aufgefordert. Das Paket wird Ihnen zur Verfügung gestellt, sodass Sie es nicht separat erwerben müssen.



  - Windows PowerShell 3.0 (64 Bit)
    
    Für Windows Server 2012 und Windows Server 2012 R2 muss Windows PowerShell 3.0 in Ihre Lync Server 2013-Installation eingebunden sein. Für Windows Server 2008 R2 müssen Sie Windows PowerShell 3.0 installieren oder ein Upgrade auf diese Version ausführen. Detaillierte Informationen finden Sie unter [Installieren von Windows PowerShell 3.0 für Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

## Administratorrechte und -rollen

In der folgenden Tabelle sind die Administratorrechte und -rollen aufgeführt, die für die einzelnen Aufgaben zur Active Directory-Vorbereitung erforderlich sind.

### Erforderliche Benutzerrechte für die Vorbereitung von Active Directory

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
<td><p>Mitglied der Gruppe &quot;Schema-Admins&quot; für die Stammdomäne einer Gesamtstruktur und Administratorrechte für den Schemamaster</p></td>
</tr>
<tr class="even">
<td><p>Gesamtstrukturvorbereitung</p></td>
<td><p>Mitglied der Gruppe &quot;Organisations-Admins&quot; für die Gesamtstruktur</p></td>
</tr>
<tr class="odd">
<td><p>Domänenvorbereitung</p></td>
<td><p>Mitglied der Gruppe &quot;Organisations-Admins&quot; oder &quot;Domänen-Admins&quot; für die angegebene Domäne</p></td>
</tr>
</tbody>
</table>


## Cmdlets für die Active Directory-Vorbereitung

In der folgenden Tabelle werden die Cmdlets der Lync Server-Verwaltungsshell zur AD DS-Vorbereitung mit den LcsCmd-Befehlen verglichen, die in Microsoft Office Communications Server 2007 R2 zur AD DS-Vorbereitung verwendet werden.

### Cmdlets im Vergleich zu "LcsCmd"

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


## Anforderungen für gesperrtes Active Directory

Wenn die Berechtigungsvererbung deaktiviert wurde oder Berechtigungen für authentifizierte Benutzer in der Organisation deaktiviert werden müssen, sind während der Domänenvorbereitung zusätzliche Schritte erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten gesperrter Active Directory-Domänendienste in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

## Berechtigungen für benutzerdefinierte Container

Wenn in Ihrer Organisation statt der drei integrierten Container (Benutzer, Computer und Domänencontroller) benutzerdefinierte Container verwendet werden, muss die Gruppe der authentifizierten Benutzer über Lesezugriff für die benutzerdefinierten Container verfügen. Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich. Ausführliche Informationen finden Sie unter [Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md).

## Verwenden von Cmdlets und "Ldifde.exe"

Der Schritt **Schema vorbereiten** im Lync Server-Bereitstellungs-Assistenten und das Cmdlet **Install-CsAdServerSchema** erweitern das Active Directory-Schema auf Domänencontrollern, auf denen ein 64-Bit-Betriebssystem ausgeführt wird. Wenn das Active Directory-Schema auf einem Domänencontroller mit einem 32-Bit-Betriebssystem erweitert werden muss, können Sie das Cmdlet **Install-CsAdServerSchema** remote über einen Mitgliedsserver ausführen. Dies ist die empfohlene Vorgehensweise. Wenn Sie die Schemavorbereitung jedoch direkt auf dem Domänencontroller ausführen müssen, können Sie das Tool "Ldifde.exe" zum Importieren der Schemadateien verwenden. Das Tool "Ldifde.exe" gehört zum Lieferumfang der meisten Versionen des Windows-Betriebssystems.

Bei Verwendung von "Ldifde.exe" zum Importieren der Schemadateien, müssen Sie unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation ausführen, alle vier Dateien importieren. Die Dateien müssen mit der folgenden Reihenfolge importiert werden:

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf


> [!NOTE]
> Die vier IDF-Dateien befinden sich im Verzeichnis "\Support\Schema" des Installationsmediums oder Downloads.



Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich um den Schemamaster handelt:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Beispiel:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password


> [!NOTE]
> Verwenden Sie den Parameter "b" nur, wenn Sie als ein anderer Benutzer angemeldet sind. Ausführliche Informationen zu den erforderlichen Benutzerrechten finden Sie im Abschnitt "Administratorrechte und -rollen" weiter oben in diesem Thema.



Verwenden Sie das folgende Format, um "Ldifde.exe" zum Importieren der vier Schemadateien auf einem Domänencontroller zu verwenden, bei dem es sich nicht um den Schemamaster handelt:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Ausführliche Informationen zum Verwenden von "Ldifde" finden Sie im Microsoft Knowledge Base-Artikel 237677, "Importieren und Exportieren von Verzeichnisobjekten in bzw. aus Active Directory mit LDIFDE", unter [http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0x407).

## In diesem Abschnitt

  - [Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

