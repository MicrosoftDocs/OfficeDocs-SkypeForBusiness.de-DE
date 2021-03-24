---
title: Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365- oder Office 365-Organisation
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Erfahren Sie, wie Sie die Cloud Connector-Integration in Ihre Microsoft 365- oder Office 365-Organisation konfigurieren.
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095089"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365- oder Office 365-Organisation

> [!Important] 
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie, wie Sie die Cloud Connector-Integration in Ihre Microsoft 365- oder Office 365-Organisation konfigurieren.
  
Nachdem die Skype for Business Cloud Connector Edition-Installation abgeschlossen ist, führen Sie die Schritte in diesem Abschnitt aus, um Ihre Bereitstellung zu konfigurieren und eine Verbindung mit Ihrer Microsoft 365- oder Office 365-Organisation herzustellen.
  
## <a name="configure-firewall-settings"></a>Konfigurieren von Firewalleinstellungen

Konfigurieren Sie die Firewalleinstellungen für Ihre internen und externen Firewalleinstellungen für Ihr Umkreisnetzwerk, um die erforderlichen Ports zu öffnen, wie unter [Ports und](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) Protokolle in Plan for Skype for Business Cloud Connector [Edition beschrieben.](plan-skype-for-business-cloud-connector-edition.md)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Einrichten von PstN-Gateways (Public Switched Telephone Network)

Richten Sie Trunks für jedes PSTN-Gateway ein, um für alle Appliances auf Vermittlungsserver zu verweisen. Da der Pool-FQDN für alle Server im Pool identisch ist, sollte jeder Trunk auf einen FQDN oder eine IP-Adresse des Vermittlungsservers anstelle des FQDN des Vermittlungsserverpools verweisen. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Befolgen Sie die Anweisungen des Anbieters des PSTN-Gateways zum Importieren der Stammzertifizierungsstelle.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dies mithilfe des Zertifizierungsstellesdiensts tun, der auf dem Cloud Connector Active Directory-Computer wie folgt ausgeführt wird:
    
   - Ändern Sie die vorhandene Webservervorlage, um authentifizierten Benutzern die Registrierung zu ermöglichen, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Fordern Sie mithilfe des Zertifikat-Snap-Ins ein Zertifikat an, das die aktivierte Webservervorlage aus wählt. Achten Sie darauf, unter Alternativer Name mit FQDN des Gateways allgemeinen Namen unter Betreff- und DNS-Name hinzuzufügen, und bestätigen Sie im privaten Schlüssel, dass Privater Schlüssel exportierbar machen unter Schlüsseloptionen ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit privatem Schlüssel, und befolgen Sie die Anweisungen ihres Anbieters für PSTN-Gateways zum Importieren des Zertifikats.
    
## <a name="update-the-domain-for-your-tenant"></a>Aktualisieren der Domäne für Ihren Mandanten

Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit haben, DNS-Einträge hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter Hinzufügen einer Domäne zu [Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Hinzufügen von DNS-Einträgen für Ihren Edge

Fügen Sie Ihrer Microsoft 365- oder Office 365-Organisation die folgenden DNS-Einträge hinzu. Informationen zum Hinzufügen von DNS-Einträgen finden Sie unter Hinzufügen oder Bearbeiten benutzerdefinierter [DNS-Einträge in Microsoft 365 oder Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Fügen Sie einen DNS A-Eintrag für Access Edge hinzu.
    
2. SRV-Einträge werden automatisch von Microsoft 365 oder Office 365 und den Bereitstellungsskripts erstellt. Vergewissern Sie sich, dass Sie die folgenden beiden SIP-Dienste auf dem Edge nachschauen können: \_ sip \_ und sipfederationtls.
    
     ![BESTÄTIGUNG von SRV-Einträgen](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Einrichten der Hybridkonnektivität zwischen Cloud Connector Edition und Microsoft 365 oder Office 365

Führen Sie das folgende Cmdlet in einer Remote-PowerShell-Sitzung aus, um die Hybridkonnektivität zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrer Microsoft 365- oder Office 365-Organisation zu konfigurieren. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: Einrichten des Computers [für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
Das Cmdlet legt den externen Zugriffs-Edge-FQDN fest. Im ersten der Befehle sollte der für die \<External Access Edge FQDN\> SIP-Zugriffs-Edgerolle verwendet werden. Standardmäßig sollte dies ap \<Domain Name\> sein.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Der für Peerziel verwendete FQDN des Edge-FQDN für den externen Zugriff sollte auf einen PSTN-Standort festgelegt werden, der nur als Fallback verwendet wird, wenn ein Benutzer keinem PSTN-Standort zugewiesen ist. Weitere Informationen finden Sie unter [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Einrichten von PSTN-Gateways

Richten Sie Trunks für jedes PSTN-Gateway ein, um für alle Appliances auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse des Vermittlungsservers anstelle des FQDN des Vermittlungsserverpools verweisen, da der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Befolgen Sie die Anweisungen des Anbieters des PSTN-Gateways zum Importieren der Stammzertifizierungsstelle.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dies mithilfe des Zertifizierungsstellesdiensts tun, der auf dem Cloud Connector Active Directory-Computer wie folgt ausgeführt wird:
    
   - Ändern Sie die vorhandene Webservervorlage, um authentifizierten Benutzern die Registrierung zu ermöglichen, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Fordern Sie mithilfe des Zertifikat-Snap-Ins ein Zertifikat an, das die aktivierte Webservervorlage aus wählt. Achten Sie darauf, unter Alternativer Name mit FQDN des Gateways allgemeinen Namen unter Betreff- und DNS-Name hinzuzufügen, und bestätigen Sie im privaten Schlüssel, dass Privater Schlüssel exportierbar machen unter Schlüsseloptionen ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit privatem Schlüssel, und befolgen Sie die Anweisungen ihres Anbieters für PSTN-Gateways zum Importieren des Zertifikats.
    
5. PSTN-Gateways an einem PSTN-Standort sollten nur eine Verbindung mit den Vermittlungsservern am gleichen Standort herstellen.
    
## <a name="set-up-your-users"></a>Einrichten ihrer Benutzer

Melden Sie sich beim Microsoft 365 Admin Center an, fügen Sie die Benutzer hinzu, die für Online-Voicedienste aktiviert werden, und weisen Sie diesen Benutzern eine E5-Lizenz oder ein Telefonsystem-Add-On zur E3-Lizenz zu. Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Microsoft 365 Business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Aktivieren von Benutzern für Sprach- und Voicemaildienste des Telefonsystems
 
Nachdem Sie Ihre Benutzer zu Microsoft 365 oder Office 365 hinzugefügt haben, aktivieren Sie ihre Konten für Telefonsystem-Voicedienste, einschließlich Voicemail. Um diese Funktionen zu aktivieren, müssen Sie sich bei Ihrer Microsoft 365- oder Office 365-Organisation mit einem Konto anmelden, das eine globale Administratorrolle ist, und remote PowerShell ausführen können. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: Einrichten des Computers [für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- Weisen Sie die Richtlinie Ihrem Benutzer zu, und konfigurieren Sie die Geschäftliche Voicetelefonnummer des Benutzers, die Sie mit dem Wert des **Parameters Identity** angeben:
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Eine Benutzeridentität kann mithilfe der SIP-Adresse, des Benutzerprinzipalnamens (User Principal Name, UPN) oder des Active Directory-Anzeigenamens des Benutzers (z. B. "Bob Kelly") angegeben werden. Das Sternchen ( \* ) kann auch mit dem Anzeigenamen als Benutzeridentität verwendet werden. Der Identitätswert "Smith" gibt beispielsweise alle Benutzer zurück, deren Anzeigename mit dem \* Zeichenfolgenwert "Smith" endet.
  
Anschließend können Sie mithilfe des folgenden Skripts überprüfen, ob die Benutzer hinzugefügt und aktiviert wurden:
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Sie müssen entscheiden, ob Ihre Benutzer in der Lage sein sollen, internationale Anrufe zu machen. Standardmäßig sind internationale Anrufe aktiviert. Sie können Benutzer für die internationale Wählwahl über das Skype for Business Admin Center deaktivieren oder aktivieren.
  
Führen Sie das folgende Cmdlet in Skype for Business Online PowerShell aus, um internationale Anrufe pro Benutzer zu deaktivieren:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Führen Sie dasselbe Cmdlet aus, ändern Sie jedoch den Wert für **PolicyName** in *InternationalCallsAllowed,*  um internationale Anrufe pro Benutzer erneut zu aktivieren, nachdem sie deaktiviert wurden.
  
## <a name="assign-users-to-pstn-sites"></a>Zuweisen von Benutzern zu PSTN-Websites

Verwenden Sie Mandanten-Remote-PowerShell, um Benutzern eine Website zuzuordnen, auch wenn Sie nur einen einzelnen Standort bereitgestellt haben. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: Einrichten des Computers [für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Wenn einem Benutzer kein PSTN-Standort zugewiesen ist, wird die Hybridkonnektivität zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrer Microsoft 365- oder Office 365-Organisation auf die Verwendung der Standardverbindung auf Mandantenebene (PeerZiel) zurückgestellt, damit Anrufe abgeschlossen werden können. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Konfigurieren von Einstellungen für den Onlinehybridvermittlungsserver
<a name="BKMK_ConfigureMediationServer"> </a>

Wenn ein P2P-Anruf zu einer PSTN-Konferenz eskaliert wird, sendet der Skype for Business Online-Konferenzserver eine Einladung an den Cloud Connector Mediation Server. Um sicherzustellen, dass Microsoft 365 oder Office 365 diese Einladung erfolgreich routen kann, müssen Sie eine Einstellung in Ihrem Online-Mandanten für jeden Cloud Connector Mediation Server wie folgt konfigurieren: 
  
1. Erstellen Sie einen Benutzer im Microsoft 365 Admin Center. Verwenden Sie einen beliebigen Benutzernamen, z. B. "MediationServer1".
    
    Verwenden Sie die Standard-SIP-Domäne von Cloud Connector (die erste SIP-Domäne in der INI-Datei) als Benutzerdomäne.
    
    Beachten Sie, dass die Lizenzzuweisung nur für die Benutzerweitergabe in das Skype for Business-Onlineverzeichnis erforderlich ist. Weisen Sie dem von Ihnen erstellten Konto eine Microsoft 365- oder Office 365-Lizenz (z. B. E5) zu, lassen Sie bis zu einer Stunde zu, bis die Änderungen sich vermehren, überprüfen Sie, ob die Benutzerkonten ordnungsgemäß im Skype for Business-Onlineverzeichnis bereitgestellt wurden, indem Sie das folgende Cmdlet ausführen, und entfernen Sie dann die Lizenz aus diesem Konto.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Starten Sie eine Azure AD-Remote-PowerShell-Mandantensitzung mit Ihren globalen Anmeldeinformationen oder Benutzeradministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die Abteilung für das Azure AD-Benutzerkonto, das in Schritt 1 konfiguriert wurde, auf "HybridMediationServer" zu setzen:

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Starten Sie eine Skype for Business-Remote-PowerShell-Clientsitzung mit Ihren Skype for Business-Mandantenadministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um den Vermittlungsserver und den Edgeserver-FQDN auf dieses Benutzerkonto zu setzen, und ersetzen Sie durch den Anzeigenamen des Benutzers für das Konto, das Sie in Schritt 1 erstellt \<DisplayName\> haben:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Verwenden Sie für Identity den Anzeigenamen des Benutzerkontos, das Sie für diesen Vermittlungsserver erstellt haben.
    
    Verwenden  *Sie für MediationServerFQDN*  den internen FQDN, der für Ihren Vermittlungsserver definiert ist.
    
    Verwenden  *Sie für EdgeServerExternalFQDN*  den externen FQDN, der für den Edgeserverzugriffsproxy definiert ist. Wenn mehrere Cloud Connector-PSTN-Standorte vorhanden sind, wählen Sie den Edgeserverzugriffsproxy-FQDN aus, der dem Standort zugewiesen ist, an dem sich der Vermittlungsserver befindet.
    
4. Wenn mehrere Cloud Connector-Vermittlungsserver (mehrere Standorte, HA) vorhanden sind, wiederholen Sie die vorherigen Schritte für jeden einzelnen.
