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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030721"
---
# <a name="configure-skype-for-business-hybrid"></a>Konfigurieren von Skype für hybride Business

Um Skype für hybride Business zu konfigurieren, müssen Sie:

- [Konfigurieren des Verbunds](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [Konfigurieren Sie einen freigegebenen Adressraum Session Initiation Protocol (SIP)](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [Konfigurieren der Server-zu-Server-Authentifizierung bei Bedarf](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Konfigurieren Sie Ihrer lokalen Edge-Dienst für den Verbund mit Skype für Business Online

Verbund ermöglicht Benutzern in Ihrer lokalen Bereitstellung mit Office 365-Benutzern in Ihrer Organisation kommunizieren. Um den Verbund zu konfigurieren, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Konfigurieren Sie Ihrer Skype für Business Online Mandanten für einen freigegebenen SIP-Adressraum

Eine SIP-Adresse (Session Initiation Protocol) ist ein eindeutiger Bezeichner für jeden Benutzer in einem Netzwerk, ähnlich wie eine Telefonnummer oder eine E-Mail-Adresse. Bevor Sie versuchen, den Benutzer aus der lokalen in Skype für Business Online zu verschieben, müssen Sie Ihre Office 365-Mandanten zum Freigeben von des Adressraums Shared Session Initiation Protocol (SIP) mit der lokalen Bereitstellung konfigurieren. Wenn dies nicht konfiguriert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:
  
Move-CsUser: HostedMigration Fehler: Error=(510), Beschreibung = (Mandant des Benutzers ist für freigegebenen Sip-Adressraum nicht aktiviert.)
  
Zum Konfigurieren eines freigegebenen SIP-Adressraums herstellen Sie eine remote-PowerShell-Sitzung mit Skype für Business Online, und führen Sie dann das folgende Cmdlet aus:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Das Attribut „SharedSipAddressSpace“ muss auf „True“ festgelegt bleiben, bis die Verschiebung in die lokale Bereitstellung abgeschlossen ist und keine lokalen Benutzer mehr vorhanden sind. 
  
Um eine remote-PowerShell-Sitzung mit Skype für Business Online eingerichtet haben, müssen Sie zuerst die Skype für Business Online Connector-Modul für Windows PowerShell installiert werden Sie erhalten [hier](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Nach der Installation des Moduls können Sie mit den folgenden Cmdlets eine Remotesitzung einrichten:
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

Weitere Informationen dazu, wie eine remote-PowerShell-Sitzung mit Skype für Business Online herstellen, und wie die Skype für Business Online Connector Modul verwendet finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="configure-server-to-server-authentication-if-required"></a>Konfigurieren der Server-zu-Server-Authentifizierung bei Bedarf

Je nach Typ des hybridumgebung, den Sie konfigurieren, müssen Sie die Server-zu-Server-Authentifizierung zu konfigurieren.  Weitere Informationen finden Sie unter [Manage Server-zu-Server-Authentifizierung in Skype für Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).


## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

