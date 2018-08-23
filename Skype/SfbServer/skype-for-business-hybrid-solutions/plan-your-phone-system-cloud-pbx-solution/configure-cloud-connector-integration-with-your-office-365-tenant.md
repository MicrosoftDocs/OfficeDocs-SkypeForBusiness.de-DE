---
title: Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informationen Sie zum Konfigurieren der Integration mit Cloud mit Ihrem Office 365-Mandanten.
ms.openlocfilehash: 01a3eac7356846b7d3b153ff4e01c9b52c3744ce
ms.sourcegitcommit: 5943c41bac520558733d08f4a9ecc4425c422ff9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2018
ms.locfileid: "22599414"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten
 
Informationen Sie zum Konfigurieren der Integration mit Cloud mit Ihrem Office 365-Mandanten.
  
Führen Sie nach Abschluss der Installation der Skype for Business-Cloud Connector-Edition die Schritte in diesem Abschnitt durch, um Ihre Bereitstellung zu konfigurieren und diese mit Ihrem Office 365-Mandanten zu verbinden.
  
## <a name="configure-firewall-settings"></a>Konfigurieren von Firewall-Einstellungen

Konfigurieren Sie die Firewalleinstellungen für die internen und externen Firewalleinstellungen für Sie Umkreisnetzwerk um die erforderlichen Ports zu öffnen, wie beschrieben unter [Ports und Protokolle](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Skype für Business Cloud Connector Edition planen](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Einrichten von PSTN-(Festnetz-)Gateways

Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:
    
  - Ändern Sie die vorhandene Webservervorlage zum Aktivieren von authentifizierten Benutzern die Registrierung, oder erstellen Sie eine neue Webserver-Vorlage, um andere Eigenschaften konfigurieren und Aktivieren von authentifizierten Benutzern die Registrierung. Weitere Informationen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
  - Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen. Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.
    
## <a name="update-the-domain-for-your-tenant"></a>Aktualisieren der Domäne für Ihren Mandanten

Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen. Weitere Informationen dazu, wie Sie Ihre Domäne in Office 365 einrichten finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Hinzufügen von DNS-Datensätzen in Office 365 für Ihre Edges

Fügen Sie Ihrem Office 365-Mandanten die folgenden DNS-Datensätze hinzu. Informationen dazu, wie Sie Ihre Office 365-Mandanten DNS-Datensätze hinzufügen finden Sie unter [Hinzufügen oder Bearbeiten benutzerdefinierter DNS-Einträgen in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Fügen Sie einen DNS-A-Eintrag für Zugriffs-Edges hinzu.
    
2. SRV-Einträge werden automatisch von Office 365 und den Bereitstellungsskripts erstellt. Überprüfen Sie, ob Sie die folgenden zwei SIP-Dienste auf dem Edge nachschlagen können: „_sip“ und „_sipfederationtls“.
    
     ![Bestätigen von SRV-Einträgen](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Einrichten von Hybrid-Anbindung zwischen Cloud Connector Edition und Office 365

Führen Sie das folgende Cmdlet in einer remote-PowerShell-Sitzung, um hybridkonnektivität zwischen Ihrer Skype für Business Cloud Connector Edition-Bereitstellung und Ihres Office 365-Mandanten zu konfigurieren. Gewusst wie: Einrichten einer PowerShell-Remotesitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
Mit dem Cmdlet wird der externe FQDN des Zugriffsedge eingerichtet. In der ersten der Befehle die \<externer FQDN der Access Edge\> sollte demjenigen, der für die SIP-Zugriffs-Edgeservers-Rolle sein. In der Standardeinstellung sollte dies ap.\<Domänennamen\>.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Den externen Zugriff Edge-FQDN verwendet für Peer-Ziel sollte auf eine PSTN-Website festgelegt werden, die nur als Fallback verwendet werden für den Fall, dass ein Benutzer eine PSTN-Website zugewiesen ist nicht. Weitere Informationen finden Sie unter [Bereitstellen einer einzelnen Website in der Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [mehrere Standorte in der Cloud Connector bereitstellen](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Einrichten von PSTN-Gateways

Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:
    
  - Ändern Sie die vorhandene Webservervorlage, um die Registrierung authentifizierter Benutzer zuzulassen, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und die Registrierung authentifizierter Benutzer zuzulassen. Weitere Informationen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).
    
  - Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen. Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.
    
5. PSTN-Gateways an einem PSTN-Standort sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.
    
## <a name="set-up-your-users-in-office-365"></a>Einrichten Ihrer Benutzer in Office 365

Melden Sie sich bei Office 365 Admin-Portal, die Benutzer, die für VoIP online Services aktiviert, und weisen Sie eine Lizenz für E5 oder Telefonsystem in Office 365 Add-on der Lizenz E3 diese Benutzer hinzufügen. Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Office 365 für Unternehmen](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Aktivieren von Benutzern für Telefonsystem in Office 365 Sprach- und Voicemail-Dienste

Aktivieren Sie nach dem Hinzufügen Ihrer Benutzer zu Office 365, deren Konten für Telefonsystem in Office 365-VoIP-Dienste, einschließlich Voicemail. Um diese Funktionen zu aktivieren, müssen Sie sich bei Ihrem Office 365-Mandanten mit einem Konto anmelden, bei dem es sich um eine globale Office 365-Administratorrolle handelt, und in der Lage sein, das PowerShell-Modul remote auszuführen. Gewusst wie: Einrichten einer PowerShell-Remotesitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Ihre Benutzer zuweisen der Richtlinie und Konfigurieren des Benutzers geschäftliche Telefonnummer des VoIP, die Sie mit dem Wert des Parameters **Identity** angeben:
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Sie können die Identität eines Benutzers auch über seine SIP-Adresse, den Benutzerprinzipalnamen (UPN), den Domänennamen und Benutzernamen (Domäne\Benutzername) und den Anzeigenamen in Active Directory („Bob Kelly“) kenntlich machen.  
  
Dann können Sie anhand des folgenden Skripts überprüfen, ob die Benutzer hinzugefügt und aktiviert wurden:
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Sie müssen festlegen, ob Ihre Benutzer internationale Anrufe tätigen dürfen. Standardmäßig sind internationale Anrufe aktiviert. Verwenden Sie das Skype for Business Admin Center online, um internationale Anrufe für die Benutzer zu deaktivieren oder zu aktivieren.
  
Um internationale Anrufe für einzelne Benutzer zu deaktivieren, führen Sie in der Skype for Business Online-PowerShell das folgende Cmdlet aus:
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Um reaktivieren internationale für jeden Benutzer einzeln aufrufen, nachdem er deaktiviert wurde, führen Sie die gleichen Cmdlet aus, aber ändern Sie den Wert für den **Parameter "PolicyName"** auf *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Zuweisen von Benutzern zu PSTN-Standorten

Verwenden Sie die Remote-PowerShell für Mandanten, um Benutzern einen Standort zuzuweisen, auch wenn Sie nur einen einzelnen Standort bereitgestellt haben. Gewusst wie: Einrichten einer PowerShell-Remotesitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Wenn einem Benutzer kein PSTN-Standort zugewiesen ist, wird ein Fallback der Hybrid-Anbindung zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrem Office 365-Mandanten auf die Verwendung der Standardbereitstellung auf Mandantenebene festgelegt (Peer-Ziel), sodass die Anrufe abgeschlossen werden können. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Konfigurieren von Einstellungen für einen hybriden Onlinevermittlungsserver
<a name="BKMK_ConfigureMediationServer"> </a>

Wenn ein P2P-Aufruf für eine PSTN-Konferenz eskaliert wird, sendet die Skype für Business Online Konferenzserver Einladungen zum Vermittlungsserver Cloud-Connector. Um sicherzustellen, dass diese Einladung erfolgreich von Office 365 weitergeleitet werden können, müssen Sie eine Einstellung in der online-Mandanten für jeden Vermittlungsserver von Cloud-Connector wie folgt konfigurieren: 
  
1. Erstellen Sie im Office 365-Verwaltungsportal einen Benutzer. Verwenden Sie Benutzernamen gewünschten, z. B. "MediationServer1."
    
    Verwenden Sie die standardmäßige SIP-Domäne der Cloud-Verbindung (die erste SIP-Domäne in der INI-Datei) als Domäne des Benutzers ein.
    
    Beachten Sie, dass die Lizenz-Zuordnung ist nur für die Weitergabe Benutzer in der Skype für Business online Directory erforderlich. Weisen Sie das Konto erstellen, können bis zu einer Stunde, damit die Änderungen zu übernehmen und dann entfernen die Lizenz aus dieses Konto ein Office 365-Lizenzen (beispielsweise E5).
    
2. Starten Sie eine mit Mandanten Azure AD remote PowerShell-Sitzung mit den globalen oder Benutzeranmeldeinformationen Admin, und führen Sie dann in das folgende Cmdlet die Abteilung für das Benutzerkonto Azure AD festgelegt konfigurierten Schritt 1 "HybridMediationServer":

 ```
  Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
  ```

3. Starten Sie einen Mandanten Skype für Business remote PowerShell-Sitzung mithilfe Ihrer Skype für Business Mandanten-Admin-Anmeldeinformationen, und führen Sie dann das folgende Cmdlet für diesen Benutzer dem Vermittlungsserver und Edge-Server-FQDN festzulegen berücksichtigt, ersetzen \<DisplayName\> mit dem Anzeigenamen für das Konto des Benutzers, die Sie in Schritt 1 erstellt haben:
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    Verwenden Sie für „Identity“ den Anzeigenamen des Office 365-Benutzerkontos, das Sie für diesen Vermittlungsserver erstellt haben.
    
    Verwenden Sie für *MediationServerFQDN* den internen FQDN für einen Vermittlungsserver definiert ist.
    
    Verwenden Sie für *EdgeServerExternalFQDN* den externen FQDN für Edge-Server-Zugriffsproxy definiert ist. Wenn mehrere Cloud Connector PSTN-Standorte vorhanden sind, wählen Sie den Edgeserver-Zugriffsproxy-FQDN aus, der dem Standort zugewiesen ist, an dem sich der Vermittlungsserver befindet.
    
3. 	Wenn mehrere Cloud Connector-Vermittlungsserver (mehrere Standorte, HA) vorhanden sind, wiederholen Sie die vorherigen Schritte für jeden einzelnen Server.
    

