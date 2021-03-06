---
title: Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation
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
description: Erfahren Sie, wie Sie die Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation konfigurieren.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359071"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Konfigurieren der Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation

> [!Important] 
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Erfahren Sie, wie Sie die Cloud Connector-Integration in Ihre Microsoft 365-oder Office 365-Organisation konfigurieren.
  
Nachdem die Skype for Business Cloud Connector Edition-Installation abgeschlossen ist, führen Sie die Schritte in diesem Abschnitt aus, um Ihre Bereitstellung zu konfigurieren und Sie mit Ihrer Microsoft 365-oder Office 365-Organisation zu verbinden.
  
## <a name="configure-firewall-settings"></a>Konfigurieren von Firewall-Einstellungen

Konfigurieren Sie die Firewalleinstellungen für Ihre internen und externen Firewalleinstellungen für Ihr Umkreisnetzwerk, um die erforderlichen Ports zu öffnen, wie in [Ports und Protokollen](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben.
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Einrichten von PSTN-Gateways (Public Switched Telephone Network)

Richten Sie Trunks auf jedem PSTN-Gateway so ein, dass Sie auf Vermittlungsserver für alle Appliances zurückgehen. Da der Pool-FQDN für alle Server im Pool gleich ist, sollte jeder trunk auf einen Vermittlungsserver FQDN oder eine IP-Adresse statt auf den FQDN des Vermittlungsserver Pools deuten. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:
  
1. Exportieren Sie die Stammzertifizierungsstelle aus dem Cloud Connector Active Directory Computer.
    
2. Folgen Sie den Anweisungen des Anbieters für das PSTN-Gateway zum Importieren der Stammzertifizierungsstelle.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde. Wenn Sie ein SSL-Zertifikat für das Gateway erhalten möchten, können Sie dies mit dem Zertifizierungsstellendienst ausführen, der auf dem Cloud Connector Active Directory Computer wie folgt verwendet wird:
    
   - Ändern Sie die vorhandene Webservervorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Anfordern eines Zertifikats mithilfe des Zertifikat-Snap-ins Auswählen der Webservervorlage, die Sie aktiviert haben. Achten Sie darauf, den allgemeinen Namen unter Betreff-und DNS-Name in alternativem Namen mit dem FQDN des Gateways hinzuzufügen, und bestätigen Sie mit dem privaten Schlüssel, der exportierbaren privaten Schlüssel auswählen Unterschlüssel Optionen. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und befolgen Sie die Anweisungen des Anbieters für den PSTN-Gateway, um das Zertifikat zu importieren.
    
## <a name="update-the-domain-for-your-tenant"></a>Aktualisieren der Domäne für Ihren Mandanten

Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Hinzufügen von DNS-Einträgen für Ihre Edge

Fügen Sie die folgenden DNS-Einträge zu Ihrer Microsoft 365-oder Office 365-Organisation hinzu. Informationen zum Hinzufügen von DNS-Einträgen finden Sie unter [Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen in Microsoft 365 oder Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Hinzufügen eines DNS-a-Eintrags für Access Edge.
    
2. SRV-Einträge werden automatisch von Microsoft 365 oder Office 365 und den Bereitstellungsskripts erstellt. Stellen Sie sicher, dass Sie die folgenden zwei SIP-Dienste auf dem Edge nachschlagen können: \_ SIP und \_ sipfederationtls.
    
     ![SRV-Eintrags Bestätigung](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Einrichten von Hybrid Konnektivität zwischen Cloud Connector Edition und Microsoft 365 oder Office 365

Um die hybride Konnektivität zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrer Microsoft 365-oder Office 365-Organisation zu konfigurieren, führen Sie das folgende Cmdlet in einer Remote-PowerShell-Sitzung aus. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
Das Cmdlet legt den externen FQDN des Access-Edges fest. Im ersten der Befehle \<External Access Edge FQDN\> sollte der für die SIP-Zugriffs-Edge-Rolle gelten. Standardmäßig sollte dies \<Domain Name\> AP. sein.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Der für das Peer-Ziel verwendete FQDN für den externen Zugriffs Rand sollte auf einen PSTN-Standort festgelegt werden, der nur dann als Fallback verwendet wird, wenn ein Benutzer keinem PSTN-Standort zugewiesen ist. Weitere Informationen finden Sie unter [Bereitstellen eines einzelnen Standorts in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Standorte in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Einrichten von PSTN-Gateways

Richten Sie Trunks auf jedem PSTN-Gateway so ein, dass Sie auf Vermittlungsserver für alle Appliances zurückgehen. Jeder trunk sollte auf einen Vermittlungsserver FQDN oder eine IP-Adresse statt auf den FQDN des Vermittlungsserver Pools hinweisen, da der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:
  
1. Exportieren Sie die Stammzertifizierungsstelle aus dem Cloud Connector Active Directory Computer.
    
2. Folgen Sie den Anweisungen des Anbieters für das PSTN-Gateway zum Importieren der Stammzertifizierungsstelle.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde. Wenn Sie ein SSL-Zertifikat für das Gateway erhalten möchten, können Sie dies mit dem Zertifizierungsstellendienst ausführen, der auf dem Cloud Connector Active Directory Computer wie folgt verwendet wird:
    
   - Ändern Sie die vorhandene Webservervorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Anfordern eines Zertifikats mithilfe des Zertifikat-Snap-ins Auswählen der Webservervorlage, die Sie aktiviert haben. Achten Sie darauf, den allgemeinen Namen unter Betreff-und DNS-Name in alternativem Namen mit dem FQDN des Gateways hinzuzufügen, und bestätigen Sie mit dem privaten Schlüssel, der exportierbaren privaten Schlüssel auswählen Unterschlüssel Optionen. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und befolgen Sie die Anweisungen des Anbieters für den PSTN-Gateway, um das Zertifikat zu importieren.
    
5. PSTN-Gateways an einem PSTN-Standort sollten nur eine Verbindung mit dem Vermittlungsserver am gleichen Standort herstellen.
    
## <a name="set-up-your-users"></a>Einrichten der Benutzer

Melden Sie sich beim Microsoft 365 Admin Center an, fügen Sie die Benutzer hinzu, die für Online-VoIP-Dienste aktiviert werden sollen, und weisen Sie diesen Benutzern eine E5-Lizenz oder ein Telefon System-Add-on zur E3-Lizenz zu. Weitere Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Microsoft 365 for Business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Aktivieren von Benutzern für Sprach-und Voicemail-Dienste für Telefonsysteme
 
Nachdem Sie Ihre Benutzer zu Microsoft 365 oder Office 365 hinzugefügt haben, aktivieren Sie deren Konten für VoIP-Dienste für Telefonsysteme, einschließlich Voicemail. Um diese Funktionen zu aktivieren, müssen Sie sich mit einem Konto, das eine globale Administrator Rolle ist, bei Ihrer Microsoft 365-oder Office 365-Organisation anmelden und Remote-PowerShell ausführen können. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Weisen Sie die Richtlinie Ihrem Benutzer zu, und konfigurieren Sie die geschäftliche Telefonnummer des Benutzers, die Sie mit dem Wert des Parameters **Identity** angeben:
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Eine Benutzeridentität kann mit der SIP-Adresse des Benutzers, dem Benutzerprinzipalnamen (User Principal Name, UPN) oder dem Active Directory Anzeigenamen des Benutzers angegeben werden (beispielsweise "Bob Kelly"). Das Sternchen ( \* ) kann auch mit dem Anzeigenamen als Benutzeridentität verwendet werden. Die Identität " \* Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen haben, der mit dem Zeichenfolgenwert "Smith" endet.
  
Anschließend können Sie überprüfen, ob die Benutzer mit dem folgenden Skript hinzugefügt und aktiviert wurden:
  
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

Sie müssen entscheiden, ob Ihre Benutzer internationale Anrufe tätigen können. Standardmäßig ist internationale Anrufe aktiviert. Sie können Benutzer für Internationale Einwahl mithilfe des Online Skype for Business Admin Center deaktivieren oder aktivieren.
  
Um internationale Anrufe pro Benutzer zu deaktivieren, führen Sie das folgende Cmdlet in Skype for Business Online PowerShell aus:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Um internationale Anrufe pro Benutzer nach der Deaktivierung erneut zu aktivieren, führen Sie das gleiche Cmdlet aus, ändern Sie jedoch den Wert für **PolicyName** in *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Zuweisen von Benutzern zu PSTN-Standorten

Verwenden Sie die mandantenfähige Remote-PowerShell, um Benutzern eine Website zuzuweisen, selbst wenn Sie nur einen einzigen Standort bereitgestellt haben. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Wenn keinem Benutzer ein PSTN-Standort zugewiesen ist, wird die hybridverbindung zwischen der Skype for Business Cloud Connector Edition-Bereitstellung und Ihrer Microsoft 365-oder Office 365-Organisation zurückgegeben, um die standardmäßige Mandantenebene (Peer-Ziel) zu verwenden, sodass Anrufe abgeschlossen werden können. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Konfigurieren von Online-Hybrid Vermittlungsserver-Einstellungen
<a name="BKMK_ConfigureMediationServer"> </a>

Wenn ein P2P-Anruf an eine PSTN-Konferenz weitergeleitet wird, sendet der Skype for Business Online Konferenzserver eine Einladung an den Cloud Connector Vermittlungsserver. Um sicherzustellen, dass diese Einladung von Microsoft 365 oder Office 365 erfolgreich weitergeleitet werden kann, müssen Sie für jeden Cloud Connector eine Einstellung in Ihrem Online Mandanten Vermittlungsserver wie folgt konfigurieren: 
  
1. Erstellen Sie einen Benutzer im Microsoft 365 Admin Center. Verwenden Sie einen beliebigen Benutzernamen, beispielsweise "MediationServer1".
    
    Verwenden Sie die standardmäßige SIP-Domäne von Cloud Connector (die erste SIP-Domäne in der INI-Datei) als Benutzerdomäne.
    
    Beachten Sie, dass die Lizenzzuweisung nur für die Benutzerverteilung in das Skype for Business Online-Verzeichnis erforderlich ist. Weisen Sie dem von Ihnen erstellten Konto eine Microsoft 365-oder Office 365-Lizenz (wie E5) zu, lassen Sie die Änderungen bis zu einer Stunde dauern, stellen Sie sicher, dass die Benutzerkonten ordnungsgemäß im Skype for Business Online-Verzeichnis bereitgestellt wurden, indem Sie das folgende Cmdlet ausführen, und entfernen Sie dann die Lizenz aus diesem Konto.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Starten Sie einen Mandanten Azure AD Remote-PowerShell-Sitzung mit ihren globalen oder Benutzer Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die Abteilung für das Azure AD Benutzerkonto festzulegen, das in Schritt 1 auf "HybridMediationServer" konfiguriert wurde:

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Starten Sie einen Mandanten Skype for Business Remote-PowerShell-Sitzung mit Ihren Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um den Vermittlungsserver und den Edgeserver-FQDN auf dieses Benutzerkonto festzulegen und \<DisplayName\> durch den Anzeigenamen des Benutzers für das in Schritt 1 erstellte Konto zu ersetzen:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Verwenden Sie für Identity den Anzeigenamen des Benutzerkontos, das Sie für diese Vermittlungsserver erstellt haben.
    
    Verwenden Sie für  *MediationServerFQDN*  den für Ihre Vermittlungsserver definierten internen FQDN.
    
    Verwenden Sie für  *EdgeServerExternalFQDN*  den externen FQDN, der für Edgeserver Zugriffs Proxy definiert ist. Wenn mehrere Cloud Connector-PSTN-Standorte vorhanden sind, wählen Sie den FQDN des Edgeserver Zugriffsproxys, der dem Standort zugewiesen ist, auf dem sich der Vermittlungsserver befindet.
    
4. Wenn mehrere Cloud Connector-Vermittlungsserver vorhanden sind (mehrere Standorte, ha), wiederholen Sie die vorherigen Schritte für jeden dieser Server.
    
