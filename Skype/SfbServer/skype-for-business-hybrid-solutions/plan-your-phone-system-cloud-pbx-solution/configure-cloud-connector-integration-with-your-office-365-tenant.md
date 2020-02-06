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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Erfahren Sie, wie Sie die Integration von Cloud Connectors in Ihren Office 365-Mandanten konfigurieren.
ms.openlocfilehash: 3e451757d82957987b394b67babe88dac199715b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803585"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="e9656-103">Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="e9656-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="e9656-104">Erfahren Sie, wie Sie die Integration von Cloud Connectors in Ihren Office 365-Mandanten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="e9656-105">Führen Sie nach Abschluss der Installation der Skype for Business-Cloud Connector-Edition die Schritte in diesem Abschnitt durch, um Ihre Bereitstellung zu konfigurieren und diese mit Ihrem Office 365-Mandanten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="e9656-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="e9656-106">Konfigurieren von Firewall-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e9656-106">Configure firewall settings</span></span>

<span data-ttu-id="e9656-107">Konfigurieren Sie die Firewalleinstellungen für Ihre internen und externen Firewalleinstellungen für Ihr Umkreisnetzwerk, um die erforderlichen Ports zu öffnen, wie in [Ports und Protokollen](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9656-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="e9656-108">Einrichten von PSTN-(Festnetz-)Gateways</span><span class="sxs-lookup"><span data-stu-id="e9656-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="e9656-p101">Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e9656-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="e9656-112">Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e9656-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="e9656-113">Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.</span><span class="sxs-lookup"><span data-stu-id="e9656-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="e9656-114">Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="e9656-p102">Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="e9656-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="e9656-117">Ändern Sie die vorhandene Webservervorlage, um authentifizierten Benutzern die Registrierung zu ermöglichen, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="e9656-118">Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9656-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="e9656-119">Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen.</span><span class="sxs-lookup"><span data-stu-id="e9656-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="e9656-120">Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="e9656-121">Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="e9656-122">Aktualisieren der Domäne für Ihren Mandanten</span><span class="sxs-lookup"><span data-stu-id="e9656-122">Update the domain for your tenant</span></span>

<span data-ttu-id="e9656-123">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9656-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e9656-124">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e9656-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="e9656-125">Hinzufügen von DNS-Datensätzen in Office 365 für Ihre Edges</span><span class="sxs-lookup"><span data-stu-id="e9656-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="e9656-126">Fügen Sie Ihrem Office 365-Mandanten die folgenden DNS-Datensätze hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9656-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="e9656-127">Informationen zum Hinzufügen von DNS-Einträgen zu Ihrem Office 365-Mandanten finden Sie unter [Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="e9656-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="e9656-128">Fügen Sie einen DNS-A-Eintrag für Zugriffs-Edges hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9656-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="e9656-p107">SRV-Einträge werden automatisch von Office 365 und den Bereitstellungsskripts erstellt. Überprüfen Sie, ob Sie die folgenden zwei SIP-Dienste auf dem Edge nachschlagen können: „_sip“ und „_sipfederationtls“.</span><span class="sxs-lookup"><span data-stu-id="e9656-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Bestätigen von SRV-Einträgen](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="e9656-132">Einrichten von Hybrid-Anbindung zwischen Cloud Connector Edition und Office 365</span><span class="sxs-lookup"><span data-stu-id="e9656-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="e9656-133">Führen Sie das folgende Cmdlet in einer Remote-PowerShell-Sitzung aus, um die hybridverbindung zwischen der Bereitstellung von Skype for Business Cloud Connector Edition und Ihrem Office 365-Mandanten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="e9656-134">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9656-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="e9656-135">Das Cmdlet legt den externen FQDN für Zugriffs-Edges fest.</span><span class="sxs-lookup"><span data-stu-id="e9656-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="e9656-136">Im ersten der Befehle sollte der \<FQDN für den externen Access-\> Edge-Domänennamen für die SIP Access-Edge-Rolle vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="e9656-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="e9656-137">Standardmäßig sollte dies AP.\<Domain-Name\>sein.</span><span class="sxs-lookup"><span data-stu-id="e9656-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="e9656-138">Der für das Peer Ziel verwendete FQDN des externen Zugriffs-Edge sollte auf eine PSTN-Website festgelegt werden, die nur dann als Fallback verwendet wird, wenn ein Benutzer nicht einer PSTN-Website zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="e9656-139">Weitere Informationen finden Sie unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Websites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e9656-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="e9656-140">Einrichten von PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="e9656-140">Set up PSTN gateways</span></span>

<span data-ttu-id="e9656-p111">Richten Sie Trunks auf allen PSTN-Gateways ein, um für alle Appliances zurück auf Vermittlungsserver zu verweisen. Jeder Trunk sollte auf einen FQDN oder eine IP-Adresse für Vermittlungsserver anstatt auf den Pool-FQDN für Vermittlungsserver verweisen, weil der Pool-FQDN für alle Server im Pool identisch ist. Trunks sollten in derselben Priorität festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e9656-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="e9656-144">Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver zur Unterstützung von MTLS wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e9656-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="e9656-145">Exportieren Sie die Stammzertifizierungsstelle vom Cloud Connector Active Directory-Computer.</span><span class="sxs-lookup"><span data-stu-id="e9656-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="e9656-146">Folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um die Stammzertifizierungsstelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="e9656-p112">Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das für Ihr Gateway auf dem Vermittlungsserver ausgegebene Zertifikat. Wenn Sie ein SSL-Zertifikat für das Gateway abrufen müssen, können Sie dafür den Zertifizierungsstellen-Dienst verwenden, der auf dem Cloud Connector Active Directory-Computer ausgeführt wird. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="e9656-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="e9656-149">Ändern Sie die vorhandene Webserver-Vorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webserver-Vorlage, um andere Eigenschaften zu konfigurieren und um authentifizierten Benutzern die Registrierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e9656-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="e9656-150">Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9656-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="e9656-151">Fordern Sie ein Zertifikat mit dem Zertifikat-Snap-In an, indem Sie die aktivierte Webservervorlage auswählen.</span><span class="sxs-lookup"><span data-stu-id="e9656-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="e9656-152">Vergewissern Sie sich, dass Sie als Antragsteller den allgemeinen Namen und den DNS-Namen als alternativen Namen mit dem FQDN des Gateways hinzufügen, und prüfen Sie, dass für „Privater Schlüssel“ unter den Schlüsseloptionen die Option „Privaten Schlüssel exportierbar machen“ ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="e9656-153">Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und folgen Sie den Anweisungen für PSTN-Gateways Ihres Anbieters, um das Zertifikat zu importieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="e9656-154">PSTN-Gateways an einem PSTN-Standort sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="e9656-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="e9656-155">Einrichten Ihrer Benutzer in Office 365</span><span class="sxs-lookup"><span data-stu-id="e9656-155">Set up your users in Office 365</span></span>

<span data-ttu-id="e9656-156">Melden Sie sich beim Office 365-Administratorportal an, fügen Sie die Benutzer hinzu, die für Online-Sprachdienste aktiviert werden, und weisen Sie diesen Benutzern eine E5-Lizenz oder ein Telefon System in Office 365-Add-on zur E3-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="e9656-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="e9656-157">Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Office 365 for Business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="e9656-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="e9656-158">Aktivieren von Benutzern für das Telefon System in Office 365-sprach-und Voicemail-Diensten</span><span class="sxs-lookup"><span data-stu-id="e9656-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="e9656-159">Nachdem Sie Ihre Benutzer zu Office 365 hinzugefügt haben, aktivieren Sie Ihre Konten für das Telefon System in den Office 365-Sprachdiensten, einschließlich Voicemail.</span><span class="sxs-lookup"><span data-stu-id="e9656-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="e9656-160">Um diese Funktionen zu aktivieren, müssen Sie sich bei Ihrem Office 365-Mandanten mit einem Konto anmelden, bei dem es sich um eine globale Office 365-Administratorrolle handelt, und in der Lage sein, das PowerShell-Modul remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e9656-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="e9656-161">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9656-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="e9656-162">Weisen Sie die Richtlinie Ihrem Benutzer zu, und konfigurieren Sie die geschäftliche Telefonnummer des Benutzers, die Sie mit dem Wert des Parameters **Identity** angeben:</span><span class="sxs-lookup"><span data-stu-id="e9656-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="e9656-163">Eine Benutzeridentität kann mit der SIP-Adresse des Benutzers, dem Benutzerprinzipalnamen (User Principal Name, UPN) oder dem Active Directory-Anzeigenamen des Benutzers (beispielsweise "Bob Kelly") angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e9656-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="e9656-164">Das Sternchen (\*)-Zeichen kann auch mit dem Anzeigenamen als Benutzeridentität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9656-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="e9656-165">Die Identität "\*Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen aufweisen, der mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="e9656-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="e9656-166">Mit dem folgenden Skript können Sie dann überprüfen, ob die Benutzer hinzugefügt und aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="e9656-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="e9656-p118">Sie müssen festlegen, ob Ihre Benutzer internationale Anrufe tätigen können. Standardmäßig sind internationale Anrufe aktiviert. Im Online-Skype for Business-Admin Center können Sie die Option für internationale Anrufe aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9656-p118">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="e9656-170">Um internationale Anrufe auf einer Pro-Benutzer-Basis zu deaktivieren, führen Sie das folgende Cmdlet in Skype for Business Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="e9656-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="e9656-171">Wenn Sie die internationale Anruffunktion nach der Deaktivierung pro Benutzer wieder aktivieren möchten, führen Sie dasselbe Cmdlet aus, aber ändern Sie den Wert für **PolicyName** in *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="e9656-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="e9656-172">Zuweisen von Benutzern zu PSTN-Standorten</span><span class="sxs-lookup"><span data-stu-id="e9656-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="e9656-173">Verwenden Sie die Remote-PowerShell für Mandanten, um Benutzern einen Standort zuzuweisen, auch wenn Sie nur einen einzelnen Standort bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="e9656-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="e9656-174">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten Ihres Computers für Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e9656-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="e9656-175">Wenn einem Benutzer kein PSTN-Standort zugewiesen ist, wird ein Fallback der Hybrid-Anbindung zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrem Office 365-Mandanten auf die Verwendung der Standardbereitstellung auf Mandantenebene festgelegt (Peer-Ziel), sodass die Anrufe abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="e9656-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="e9656-176">Konfigurieren von Einstellungen für einen hybriden Onlinevermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e9656-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="e9656-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="e9656-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="e9656-178">Wenn ein P2P-Anruf an eine PSTN-Konferenz weitergeleitet wird, sendet der Skype for Business Online-Konferenzserver eine Einladung an den Cloud Connector-Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="e9656-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="e9656-179">Um sicherzustellen, dass Office 365 diese Einladung erfolgreich weiterleiten kann, müssen Sie eine Einstellung in Ihrem Online Mandanten für jeden Cloud Connector-Vermittlungs Server wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e9656-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="e9656-180">Erstellen Sie im Office 365-Verwaltungsportal einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e9656-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="e9656-181">Verwenden Sie einen beliebigen Benutzernamen, beispielsweise "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="e9656-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="e9656-182">Verwenden Sie die standardmäßige SIP-Domäne von Cloud Connector (der ersten SIP-Domäne in der INI-Datei) als Benutzerdomäne.</span><span class="sxs-lookup"><span data-stu-id="e9656-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="e9656-183">Bitte beachten Sie, dass die Lizenzzuweisung nur für die Verbreitung des Nutzers in das Skype for Business Online-Verzeichnis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="e9656-184">Weisen Sie dem von Ihnen erstellten Konto eine Office 365-Lizenz (wie E5) zu, damit die Änderungen bis zu einer Stunde lang übertragen werden können, überprüfen Sie, ob die Benutzerkonten ordnungsgemäß für das Skype for Business Online-Verzeichnis bereitgestellt wurden, indem Sie folgendes Cmdlet ausführen, und entfernen Sie dann die Lizenz von diesem Konto.</span><span class="sxs-lookup"><span data-stu-id="e9656-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="e9656-185">Starten Sie eine Tenant Azure AD-Remote-PowerShell-Sitzung mit ihren globalen oder Benutzer-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die Abteilung für das Azure AD-Benutzerkonto festzulegen, das in Schritt 1 auf "HybridMediationServer" konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e9656-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="e9656-186">Starten Sie eine Mandanten-Remote-PowerShell-Sitzung unter Verwendung Ihrer Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um den Vermittlungsserver und den Edge \<-\> Server-FQDN auf dieses Benutzerkonto festzulegen, und ersetzen Sie DisplayName durch den Anzeigenamen des Benutzers für das Konto, das Sie in Schritt 1 erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="e9656-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="e9656-187">Verwenden Sie für „Identity“ den Anzeigenamen des Office 365-Benutzerkontos, das Sie für diesen Vermittlungsserver erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e9656-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="e9656-188">Verwenden Sie für *MediationServerFQDN* den internen FQDN, der für Ihren Vermittlungs Server definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="e9656-189">Verwenden Sie für *EdgeServerExternalFQDN* den externen FQDN, der für den Edge-Server-Zugriffs Proxy definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e9656-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="e9656-190">Wenn mehrere Cloud Connector PSTN-Standorte vorhanden sind, wählen Sie den Edgeserver-Zugriffsproxy-FQDN aus, der dem Standort zugewiesen ist, an dem sich der Vermittlungsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="e9656-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="e9656-191">	Wenn mehrere Cloud Connector-Vermittlungsserver (mehrere Standorte, HA) vorhanden sind, wiederholen Sie die vorherigen Schritte für jeden einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="e9656-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

