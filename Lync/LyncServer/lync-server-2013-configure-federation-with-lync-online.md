---
title: 'Lync Server 2013: Konfigurieren des Partnerverbunds mit Lync Online'
TOCTitle: Konfigurieren des Partnerverbunds mit Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205126(v=OCS.15)
ms:contentKeyID: 49294938
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Partnerverbunds von Lync Server 2013 mit Lync Online

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Führen Sie die Schritte in diesem Abschnitt aus, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online zu konfigurieren.

## Konfigurieren Ihres Edgediensts für den Partnerverbund mit Skype for Business Online

Durch einen Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrem Unternehmen kommunizieren. Führen Sie zum Konfigurieren des Partnerverbunds die folgenden Cmdlets aus:

    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting

   &nbsp;

    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

## Konfigurieren Ihres Skype for Business Online-Mandanten für einen freigegebenen SIP-Adressbereich

Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse. Bevor Sie versuchen, Lync-Benutzer von einer lokalen Bereitstellung zu Skype for Business Online zu verschieben, müssen Sie Ihren Office 365-Mandanten für die Verwendung eines freigegebenen SIP-Adressbereichs mit Ihrer lokalen Bereitstellung konfigurieren. Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:

Move-CsUser : HostedMigration fault: Error=(510), Description=(Der Mandant dieses Benutzers ist nicht für den freigegebenen SIP-Adressbereich aktiviert.)

Zum Konfigurieren eines freigegebenen SIP-Adressbereichs richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein und führen Sie dann das folgende Cmdlet aus:

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online müssen Sie zunächst das Skype for Business Online-Modul für Windows PowerShell installieren, das Sie hier erhalten: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:

    Import-Module LyncOnlineConnector

   &nbsp;

    $cred = Get-Credential

   &nbsp;

    $CSSession = New-CsOnlineSession -Credential $cred

   &nbsp;

    Import-PSSession $CSSession -AllowClobber

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online finden Sie unter [Herstellen der Verbindung zu Lync Online mit Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Weitere Informationen zur Verwendung des Skype for Business Online PowerShell-Moduls finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

## Siehe auch

#### Weitere Ressourcen

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

