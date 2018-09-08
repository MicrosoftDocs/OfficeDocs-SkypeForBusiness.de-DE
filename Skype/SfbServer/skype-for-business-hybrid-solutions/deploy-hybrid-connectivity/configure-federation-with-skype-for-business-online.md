---
title: Konfigurieren eines Partnerverbunds in Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.'
ms.openlocfilehash: 7367a1fa7bf7eb305a8b72582e488cfd6ba6fa1c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884120"
---
# <a name="configure-federation-with-skype-for-business-online"></a>Konfigurieren eines Partnerverbunds in Skype for Business Online
 
**Zusammenfassung:** Informationen Sie zum Konfigurieren der Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online.
  
Führen Sie die Schritte in diesem Abschnitt, um die Interoperabilität zwischen Ihrer lokalen Bereitstellung und Skype für Business Online zu konfigurieren.
  
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
  
Um eine remote-PowerShell-Sitzung mit Skype für Business Online eingerichtet haben, müssen Sie zuerst die Skype für Business Online Connector-Modul für Windows PowerShell installiert werden Sie hier erhalten können: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Weitere Informationen zum Verwenden von PowerShell mit Skype für Business Online finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

  
## <a name="see-also"></a>Siehe auch

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)