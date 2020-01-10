---
title: Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Erfahren Sie, wie Sie die Integration von Cloud Connectors in Ihren Office 365-Mandanten konfigurieren.
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002855"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten
 
Erfahren Sie, wie Sie die Integration von Cloud Connectors in Ihren Office 365-Mandanten konfigurieren.
  
Führen Sie nach Abschluss der Installation der Skype for Business-Cloud Connector-Edition die Schritte in diesem Abschnitt durch, um Ihre Bereitstellung zu konfigurieren und diese mit Ihrem Office 365-Mandanten zu verbinden.
  
## <a name="configure-firewall-settings"></a>Konfigurieren von Firewall-Einstellungen

Konfigurieren Sie die Firewalleinstellungen für Ihre internen und externen Firewalleinstellungen für Ihr Umkreisnetzwerk, um die erforderlichen Ports zu öffnen, wie in [Ports und Protokollen](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben.
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Einrichten von PSTN-(Festnetz-)Gateways

Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:
    
   - Ändern Sie die vorhandene Webservervorlage, um authentifizierten Benutzern die Registrierung zu ermöglichen, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
   - Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen. Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.
    
## <a name="update-the-domain-for-your-tenant"></a>Aktualisieren der Domäne für Ihren Mandanten

Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Hinzufügen von DNS-Datensätzen in Office 365 für Ihre Edges

Fügen Sie Ihrem Office 365-Mandanten die folgenden DNS-Datensätze hinzu. Informationen zum Hinzufügen von DNS-Einträgen zu Ihrem Office 365-Mandanten finden Sie unter [Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Fügen Sie einen DNS-A-Eintrag für Zugriffs-Edges hinzu.
    
2. SRV-Einträge werden automatisch von Office 365 und den Bereitstellungsskripts erstellt. Überprüfen Sie, ob Sie die folgenden zwei SIP-Dienste auf dem Edge nachschlagen können: „_sip“ und „_sipfederationtls“.
    
     ![Bestätigen von SRV-Einträgen](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Einrichten von Hybrid-Anbindung zwischen Cloud Connector Edition und Office 365

Führen Sie das folgende Cmdlet in einer Remote-PowerShell-Sitzung aus, um die hybridverbindung zwischen der Bereitstellung von Skype for Business Cloud Connector Edition und Ihrem Office 365-Mandanten zu konfigurieren. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
Das Cmdlet legt den externen FQDN für Zugriffs-Edges fest. Im ersten der Befehle sollte der \<FQDN für den externen Access-\> Edge-Domänennamen für die SIP Access-Edge-Rolle vorhanden sein. Standardmäßig sollte dies AP.\<Domain-Name\>sein.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Der für das Peer Ziel verwendete FQDN des externen Zugriffs-Edge sollte auf eine PSTN-Website festgelegt werden, die nur dann als Fallback verwendet wird, wenn ein Benutzer nicht einer PSTN-Website zugewiesen ist. Weitere Informationen finden Sie unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Websites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Einrichten von PSTN-Gateways

Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.
  
Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:
  
1. Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.
    
2. Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.
    
3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:
    
   - Ändern Sie die vorhandene Webserver-Vorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webserver-Vorlage, um andere Eigenschaften zu konfigurieren und um authentifizierten Benutzern die Registrierung zu ermöglichen. Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen. Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist. 
    
4. Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.
    
5. PSTN-Gateways an einem PSTN-Standort sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.
    
## <a name="set-up-your-users-in-office-365"></a>Einrichten Ihrer Benutzer in Office 365

Melden Sie sich beim Office 365-Administratorportal an, fügen Sie die Benutzer hinzu, die für Online-Sprachdienste aktiviert werden, und weisen Sie diesen Benutzern eine E5-Lizenz oder ein Telefon System in Office 365-Add-on zur E3-Lizenz zu. Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Office 365 for Business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Aktivieren von Benutzern für das Telefon System in Office 365-sprach-und Voicemail-Diensten

Nachdem Sie Ihre Benutzer zu Office 365 hinzugefügt haben, aktivieren Sie Ihre Konten für das Telefon System in den Office 365-Sprachdiensten, einschließlich Voicemail. Um diese Funktionen zu aktivieren, müssen Sie sich bei Ihrem Office 365-Mandanten mit einem Konto anmelden, bei dem es sich um eine globale Office 365-Administratorrolle handelt, und in der Lage sein, das PowerShell-Modul remote auszuführen. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Weisen Sie die Richtlinie Ihrem Benutzer zu, und konfigurieren Sie die geschäftliche Telefonnummer des Benutzers, die Sie mit dem Wert des Parameters **Identity** angeben:
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Eine Benutzeridentität kann mit der SIP-Adresse des Benutzers, dem Benutzerprinzipalnamen (User Principal Name, UPN) oder dem Active Directory-Anzeigenamen des Benutzers (beispielsweise "Bob Kelly") angegeben werden. Das Sternchen (\*)-Zeichen kann auch mit dem Anzeigenamen als Benutzeridentität verwendet werden. Die Identität "\*Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.
  
Mit dem folgenden Skript können Sie dann überprüfen, ob die Benutzer hinzugefügt und aktiviert wurden:
  
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

Sie müssen festlegen, ob Ihre Benutzer internationale Anrufe tätigen können. Standardmäßig sind internationale Anrufe aktiviert. Im Online-Skype for Business-Admin Center können Sie die Option für internationale Anrufe aktivieren bzw. deaktivieren.
  
Um internationale Anrufe auf einer Pro-Benutzer-Basis zu deaktivieren, führen Sie das folgende Cmdlet in Skype for Business Online PowerShell aus:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Wenn Sie die internationale Anruffunktion nach der Deaktivierung pro Benutzer wieder aktivieren möchten, führen Sie dasselbe Cmdlet aus, aber ändern Sie den Wert für **PolicyName** in *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Zuweisen von Benutzern zu PSTN-Standorten

Verwenden Sie die Remote-PowerShell für Mandanten, um Benutzern einen Standort zuzuweisen, auch wenn Sie nur einen einzelnen Standort bereitgestellt haben. Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
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

Wenn ein P2P-Anruf an eine PSTN-Konferenz weitergeleitet wird, sendet der Skype for Business Online-Konferenzserver eine Einladung an den Cloud Connector-Vermittlungsserver. Um sicherzustellen, dass Office 365 diese Einladung erfolgreich weiterleiten kann, müssen Sie eine Einstellung in Ihrem Online Mandanten für jeden Cloud Connector-Vermittlungs Server wie folgt konfigurieren: 
  
1. Erstellen Sie im Office 365-Verwaltungsportal einen Benutzer. Verwenden Sie einen beliebigen Benutzernamen, beispielsweise "MediationServer1".
    
    Verwenden Sie die standardmäßige SIP-Domäne von Cloud Connector (der ersten SIP-Domäne in der INI-Datei) als Benutzerdomäne.
    
    Bitte beachten Sie, dass die Lizenzzuweisung nur für die Verbreitung des Nutzers in das Skype for Business Online-Verzeichnis erforderlich ist. Weisen Sie dem von Ihnen erstellten Konto eine Office 365-Lizenz (wie E5) zu, damit die Änderungen bis zu einer Stunde lang übertragen werden können, überprüfen Sie, ob die Benutzerkonten ordnungsgemäß für das Skype for Business Online-Verzeichnis bereitgestellt wurden, indem Sie folgendes Cmdlet ausführen, und entfernen Sie dann die Lizenz von diesem Konto.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Starten Sie eine Tenant Azure AD-Remote-PowerShell-Sitzung mit ihren globalen oder Benutzer-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die Abteilung für das Azure AD-Benutzerkonto festzulegen, das in Schritt 1 auf "HybridMediationServer" konfiguriert ist:

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Starten Sie eine Mandanten-Remote-PowerShell-Sitzung unter Verwendung Ihrer Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um den Vermittlungsserver und den Edge \<-\> Server-FQDN auf dieses Benutzerkonto festzulegen, und ersetzen Sie DisplayName durch den Anzeigenamen des Benutzers für das Konto, das Sie in Schritt 1 erstellt haben:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Verwenden Sie für „Identity“ den Anzeigenamen des Office 365-Benutzerkontos, das Sie für diesen Vermittlungsserver erstellt haben.
    
    Verwenden Sie für *MediationServerFQDN* den internen FQDN, der für Ihren Vermittlungs Server definiert ist.
    
    Verwenden Sie für *EdgeServerExternalFQDN* den externen FQDN, der für den Edge-Server-Zugriffs Proxy definiert ist. Wenn mehrere Cloud Connector PSTN-Standorte vorhanden sind, wählen Sie den Edgeserver-Zugriffsproxy-FQDN aus, der dem Standort zugewiesen ist, an dem sich der Vermittlungsserver befindet.
    
4. 	Wenn mehrere Cloud Connector-Vermittlungsserver (mehrere Standorte, HA) vorhanden sind, wiederholen Sie die vorherigen Schritte für jeden einzelnen Server.
    

