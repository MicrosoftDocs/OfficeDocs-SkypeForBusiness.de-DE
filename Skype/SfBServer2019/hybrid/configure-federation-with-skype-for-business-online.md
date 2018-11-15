---
title: Konfigurieren von Skype für hybride Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532777"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren von Skype für hybride Business

Um Skype für hybride Business zu konfigurieren, müssen Sie:

- [Konfigurieren Sie die lokale Umgebung für einen Verbund mit Office 365 konfigurieren.](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [Konfigurieren Ihrer lokalen Umgebung zu Office 365-Vertrauensstellung und Aktivieren von freigegebenen SIP-Adressraums mit Office 365.](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Aktivieren von freigegebenen SIP-Adressraums in Ihrem Office 365-Mandanten.](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> Wenn Sie lokale Exchange-Organisation haben, sollten Sie OAuth zwischen Ihrer Exchange lokal und Skype für Business Online-Umgebung konfigurieren. Weitere Informationen finden Sie unter [Manage Server-zu-Server-Authentifizierung in Skype für Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) und [Planen der Integration von Skype für Unternehmen und Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Konfigurieren Sie Ihrer lokalen Edge-Dienst den Verbund mit Office 365

Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren. Um den Verbund zu konfigurieren, führen Sie das folgende Cmdlet in der Skype für Business Server-Verwaltungsshell:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Konfigurieren Sie Ihrer lokalen Umgebung zum Aktivieren von freigegebenen SIP-Adressraums mit Office 365

Sie müssen auch Konfigurieren Ihrer lokalen Umgebung zu Office 365-Vertrauensstellung und Aktivieren von freigegebenen SIP-Adressraums mit Office 365. Dies bedeutet, dass Office 365 können potenziell Hosten von Benutzerkonten für den gleichen Satz von SIP-Domänen als Ihrer lokalen Umgebung und Nachrichten zwischen Benutzern, die lokal gehostet weitergeleitet und online sein können.  Zu diesem Zweck konfigurieren einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com wie unten beschrieben.

Überprüfen Sie zunächst, wenn Sie bereits einen Hostinganbieter mit ProxyFqdn=sipfed.online.lync.com verfügen. Sofern vorhanden, entfernen Sie es mithilfe des folgenden Befehls:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Erstellen Sie einen neuen Hostinganbieter, verwenden Sie das New-CsHostingProvider-Cmdlet wie folgt: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Aktivieren von freigegebenen SIP-Adressraums in Ihrem Office 365-Mandanten
  
Zusätzlich zu den in Ihrer lokalen Bereitstellung vorgenommene Änderung müssen Sie die entsprechenden in Ihrem Office 365-Mandanten aktiviert freigegebenen SIP-Adressraums mit der lokalen Bereitstellung ändern.  

Freigegebenen SIP-Adressraums in Ihrem Office 365-Mandanten zu aktivieren, um herstellen Sie eine remote-PowerShell-Sitzung mit Skype für Business Online, und führen Sie dann das folgende Cmdlet aus:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das Attribut „SharedSipAddressSpace“ muss auf „True“ festgelegt bleiben, bis die Verschiebung in die lokale Bereitstellung abgeschlossen ist und keine lokalen Benutzer mehr vorhanden sind. 
  
Um eine remote-PowerShell-Sitzung mit Teams oder Skype für Business Online eingerichtet haben, müssen Sie zuerst die Skype für Business Online Connector-Modul für Windows PowerShell installiert werden Sie erhalten [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Weitere Informationen dazu, wie eine remote-PowerShell-Sitzung mit Skype für Business Online herstellen, und wie die Skype für Business Online Connector Modul verwendet finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

