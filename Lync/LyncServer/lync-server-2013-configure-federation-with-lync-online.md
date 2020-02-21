---
title: 'Lync Server 2013: Konfigurieren Sie den Verbund mit lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 957a0f338d0669d0c99570b541d6ddb4753c1145
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Konfigurieren des Verbund lync Server 2013 mit lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-08-15_

Führen Sie die Schritte in diesem Abschnitt aus, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype for Business Online zu konfigurieren.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Konfigurieren des lokalen Edge-Diensts für den Verbund mit Skype for Business Online

Durch einen Partnerverbund können Benutzer in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrem Unternehmen kommunizieren. Führen Sie die folgenden Cmdlets aus, um den Verbund zu konfigurieren:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Konfigurieren des Skype for Business Online Mandanten für einen freigegebenen SIP-Adressraum

Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine e-Mail-Adresse. Bevor Sie lync-Benutzer von lokal in Skype for Business Online verschieben, müssen Sie Ihren Office 365-Mandanten so konfigurieren, dass der SIP-Adressraum (Shared Session Initiation Protocol) mit Ihrer lokalen Bereitstellung freigegeben wird. Wenn diese nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:

Verschieben-CsUser: HostedMigration Fault: Error = (510), Description = (der Mandant des Benutzers ist für den freigegebenen SIP-Adressraum nicht aktiviert.)

Zum Konfigurieren eines freigegebenen SIP-Adressraums richten Sie eine Remote-PowerShell-Sitzung mit Skype for Business Online ein, und führen Sie dann das folgende Cmdlet aus:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Um eine Remote-PowerShell-Sitzung mit Skype for Business Online einzurichten, müssen Sie zunächst das Skype for Business Online-Modul für Windows PowerShell installieren, das Sie [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911)hier abrufen können:.

Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung mit den folgenden Cmdlets einrichten:

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit Skype for Business Online finden Sie unter [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Weitere Informationen zum Verwenden des Skype for Business Online-PowerShell-Moduls finden Sie unter [using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

