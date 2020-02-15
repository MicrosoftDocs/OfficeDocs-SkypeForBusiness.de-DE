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
description: Hier erfahren Sie, wie Sie die Cloud Connector-Integration mit Ihrem Office 365 Mandanten konfigurieren.
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050207"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="fd100-103">Konfigurieren der Cloud Connector-Integration mit Ihrem Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="fd100-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="fd100-104">Hier erfahren Sie, wie Sie die Cloud Connector-Integration mit Ihrem Office 365 Mandanten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="fd100-105">Nachdem die Skype for Business Cloud Connector Edition-Installation abgeschlossen ist, führen Sie die Schritte in diesem Abschnitt aus, um Ihre Bereitstellung zu konfigurieren und Sie mit Ihrem Office 365-Mandanten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="fd100-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="fd100-106">Konfigurieren von Firewall-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="fd100-106">Configure firewall settings</span></span>

<span data-ttu-id="fd100-107">Konfigurieren Sie die Firewalleinstellungen für Ihre internen und externen Firewalleinstellungen für Ihr Umkreisnetzwerk, um die erforderlichen Ports zu öffnen, wie in [Ports und Protokollen](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd100-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="fd100-108">Einrichten von PSTN-Gateways (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="fd100-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="fd100-109">Richten Sie Trunks auf jedem PSTN-Gateway so ein, dass Sie auf Vermittlungsserver für alle Appliances zurückgehen.</span><span class="sxs-lookup"><span data-stu-id="fd100-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="fd100-110">Da der Pool-FQDN für alle Server im Pool gleich ist, sollte jeder trunk auf einen Vermittlungsserver FQDN oder eine IP-Adresse statt auf den FQDN des Vermittlungsserver Pools deuten.</span><span class="sxs-lookup"><span data-stu-id="fd100-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="fd100-111">Trunks sollten in derselben Priorität festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd100-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="fd100-112">Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:</span><span class="sxs-lookup"><span data-stu-id="fd100-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="fd100-113">Exportieren Sie die Stammzertifizierungsstelle aus dem Cloud Connector Active Directory Computer.</span><span class="sxs-lookup"><span data-stu-id="fd100-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="fd100-114">Folgen Sie den Anweisungen des Anbieters für das PSTN-Gateway zum Importieren der Stammzertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fd100-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="fd100-115">Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd100-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="fd100-116">Wenn Sie ein SSL-Zertifikat für das Gateway erhalten möchten, können Sie dies mit dem Zertifizierungsstellendienst ausführen, der auf dem Cloud Connector Active Directory Computer wie folgt verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="fd100-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="fd100-117">Ändern Sie die vorhandene Webservervorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="fd100-118">Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd100-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="fd100-119">Anfordern eines Zertifikats mithilfe des Zertifikat-Snap-ins Auswählen der Webservervorlage, die Sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="fd100-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="fd100-120">Achten Sie darauf, den allgemeinen Namen unter Betreff-und DNS-Name in alternativem Namen mit dem FQDN des Gateways hinzuzufügen, und bestätigen Sie mit dem privaten Schlüssel, der exportierbaren privaten Schlüssel auswählen Unterschlüssel Optionen.</span><span class="sxs-lookup"><span data-stu-id="fd100-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="fd100-121">Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und befolgen Sie die Anweisungen des Anbieters für den PSTN-Gateway, um das Zertifikat zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="fd100-122">Aktualisieren der Domäne für Ihren Mandanten</span><span class="sxs-lookup"><span data-stu-id="fd100-122">Update the domain for your tenant</span></span>

<span data-ttu-id="fd100-123">Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben.</span><span class="sxs-lookup"><span data-stu-id="fd100-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="fd100-124">Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="fd100-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="fd100-125">Hinzufügen von DNS-Einträgen in Office 365 für Ihre Edge</span><span class="sxs-lookup"><span data-stu-id="fd100-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="fd100-126">Fügen Sie dem Office 365 Mandanten die folgenden DNS-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd100-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="fd100-127">Informationen zum Hinzufügen von DNS-Einträgen zu Ihrem Office 365 Mandanten finden Sie unter [Hinzufügen oder Bearbeiten von benutzerdefinierten DNS-Einträgen in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="fd100-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="fd100-128">Hinzufügen eines DNS-a-Eintrags für Access Edge.</span><span class="sxs-lookup"><span data-stu-id="fd100-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="fd100-129">SRV-Einträge werden automatisch von Office 365 und den Bereitstellungsskripts erstellt.</span><span class="sxs-lookup"><span data-stu-id="fd100-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="fd100-130">Stellen Sie sicher, dass Sie die folgenden zwei SIP-Dienste auf der Edge-Seite suchen können: _sip und _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="fd100-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV-Eintrags Bestätigung](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="fd100-132">Einrichten von Hybrid Konnektivität zwischen Cloud Connector Edition und Office 365</span><span class="sxs-lookup"><span data-stu-id="fd100-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="fd100-133">Führen Sie das folgende Cmdlet in einer Remote-PowerShell-Sitzung aus, um die hybride Konnektivität zwischen Ihrer Skype for Business Cloud Connector Edition-Bereitstellung und Ihrem Office 365 Mandanten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="fd100-134">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd100-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="fd100-135">Das Cmdlet legt den externen FQDN des Access-Edges fest.</span><span class="sxs-lookup"><span data-stu-id="fd100-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="fd100-136">Im ersten der Befehle sollte der \<externe Zugriffs-Edge-FQDN\> für die SIP-Zugriffs-Edge-Rolle angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fd100-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="fd100-137">Standardmäßig sollte dies AP.\<Domain-Name\>sein.</span><span class="sxs-lookup"><span data-stu-id="fd100-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="fd100-138">Der für das Peer-Ziel verwendete FQDN für den externen Zugriffs Rand sollte auf einen PSTN-Standort festgelegt werden, der nur dann als Fallback verwendet wird, wenn ein Benutzer keinem PSTN-Standort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fd100-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="fd100-139">Weitere Informationen finden Sie unter [Bereitstellen eines einzelnen Standorts in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Standorte in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fd100-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="fd100-140">Einrichten von PSTN-Gateways</span><span class="sxs-lookup"><span data-stu-id="fd100-140">Set up PSTN gateways</span></span>

<span data-ttu-id="fd100-141">Richten Sie Trunks auf jedem PSTN-Gateway so ein, dass Sie auf Vermittlungsserver für alle Appliances zurückgehen.</span><span class="sxs-lookup"><span data-stu-id="fd100-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="fd100-142">Jeder trunk sollte auf einen Vermittlungsserver FQDN oder eine IP-Adresse statt auf den FQDN des Vermittlungsserver Pools hinweisen, da der Pool-FQDN für alle Server im Pool identisch ist.</span><span class="sxs-lookup"><span data-stu-id="fd100-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="fd100-143">Trunks sollten in derselben Priorität festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd100-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="fd100-144">Wenn Sie TLS zwischen Vermittlungsservern und Gateways verwenden, müssen Sie die Gateways und Vermittlungsserver so konfigurieren, dass MTLS wie folgt unterstützt wird:</span><span class="sxs-lookup"><span data-stu-id="fd100-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="fd100-145">Exportieren Sie die Stammzertifizierungsstelle aus dem Cloud Connector Active Directory Computer.</span><span class="sxs-lookup"><span data-stu-id="fd100-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="fd100-146">Folgen Sie den Anweisungen des Anbieters für das PSTN-Gateway zum Importieren der Stammzertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fd100-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="fd100-147">Importieren Sie das Zertifikat der Stammzertifizierungsstelle für das Zertifikat, das für Ihr Gateway auf den Vermittlungsservern ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd100-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="fd100-148">Wenn Sie ein SSL-Zertifikat für das Gateway erhalten möchten, können Sie dies mit dem Zertifizierungsstellendienst ausführen, der auf dem Cloud Connector Active Directory Computer wie folgt verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="fd100-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="fd100-149">Ändern Sie die vorhandene Webservervorlage, damit sich authentifizierte Benutzer registrieren können, oder erstellen Sie eine neue Webservervorlage, um andere Eigenschaften zu konfigurieren und authentifizierte Benutzer für die Registrierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="fd100-150">Ausführliche Anweisungen finden Sie unter [Zertifikatvorlagen](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd100-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="fd100-151">Anfordern eines Zertifikats mithilfe des Zertifikat-Snap-ins Auswählen der Webservervorlage, die Sie aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="fd100-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="fd100-152">Achten Sie darauf, den allgemeinen Namen unter Betreff-und DNS-Name in alternativem Namen mit dem FQDN des Gateways hinzuzufügen, und bestätigen Sie mit dem privaten Schlüssel, der exportierbaren privaten Schlüssel auswählen Unterschlüssel Optionen.</span><span class="sxs-lookup"><span data-stu-id="fd100-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="fd100-153">Exportieren Sie das SSL-Zertifikat mit dem privaten Schlüssel, und befolgen Sie die Anweisungen des Anbieters für den PSTN-Gateway, um das Zertifikat zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="fd100-154">PSTN-Gateways an einem PSTN-Standort sollten nur eine Verbindung mit dem Vermittlungsserver am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="fd100-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="fd100-155">Einrichten der Benutzer in Office 365</span><span class="sxs-lookup"><span data-stu-id="fd100-155">Set up your users in Office 365</span></span>

<span data-ttu-id="fd100-156">Melden Sie sich beim Office 365-Verwaltungsportal an, fügen Sie die Benutzer hinzu, die für Online-VoIP-Dienste aktiviert werden sollen, und weisen Sie in Office 365 Add-on der E3-Lizenz für diese Benutzer eine E5-Lizenz oder ein Telefon System zu.</span><span class="sxs-lookup"><span data-stu-id="fd100-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="fd100-157">Informationen zum Hinzufügen von Benutzern finden Sie unter [Hinzufügen von Benutzern zu Office 365 für Unternehmen](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="fd100-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="fd100-158">Aktivieren von Benutzern für das Telefon System in Office 365 Voice-und Voicemail-Diensten</span><span class="sxs-lookup"><span data-stu-id="fd100-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="fd100-159">Nachdem Sie Ihre Benutzer Office 365 hinzugefügt haben, aktivieren Sie Ihre Konten für das Telefon System in Office 365 VoIP-Dienste, einschließlich Voicemail.</span><span class="sxs-lookup"><span data-stu-id="fd100-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="fd100-160">Um diese Funktionen zu aktivieren, müssen Sie sich mit einem Konto, das eine Office 365 globale Administrator Rolle ist, bei Ihrem Office 365 Mandanten anmelden und Remote-PowerShell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="fd100-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="fd100-161">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd100-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="fd100-162">Weisen Sie die Richtlinie Ihrem Benutzer zu, und konfigurieren Sie die geschäftliche Telefonnummer des Benutzers, die Sie mit dem Wert des Parameters **Identity** angeben:</span><span class="sxs-lookup"><span data-stu-id="fd100-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="fd100-163">Eine Benutzeridentität kann mit der SIP-Adresse des Benutzers, dem Benutzerprinzipalnamen (User Principal Name, UPN) oder dem Active Directory Anzeigenamen des Benutzers angegeben werden (beispielsweise "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="fd100-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="fd100-164">Das Sternchen (\*) kann auch mit dem Anzeigenamen als Benutzeridentität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd100-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="fd100-165">Die Identität "\*Smith" gibt beispielsweise alle Benutzer zurück, die einen Anzeigenamen haben, der mit dem Zeichenfolgenwert "Smith" endet.</span><span class="sxs-lookup"><span data-stu-id="fd100-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="fd100-166">Anschließend können Sie überprüfen, ob die Benutzer mit dem folgenden Skript hinzugefügt und aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="fd100-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="fd100-167">Sie müssen entscheiden, ob Ihre Benutzer internationale Anrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="fd100-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="fd100-168">Standardmäßig ist internationale Anrufe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fd100-168">By default, international calling is enabled.</span></span> <span data-ttu-id="fd100-169">Sie können Benutzer für Internationale Einwahl mithilfe des Online Skype for Business Admin Center deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd100-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="fd100-170">Um internationale Anrufe pro Benutzer zu deaktivieren, führen Sie das folgende Cmdlet in Skype for Business Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="fd100-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="fd100-171">Um internationale Anrufe pro Benutzer nach der Deaktivierung erneut zu aktivieren, führen Sie das gleiche Cmdlet aus, ändern Sie jedoch den Wert für **PolicyName** in *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="fd100-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="fd100-172">Zuweisen von Benutzern zu PSTN-Standorten</span><span class="sxs-lookup"><span data-stu-id="fd100-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="fd100-173">Verwenden Sie die mandantenfähige Remote-PowerShell, um Benutzern eine Website zuzuweisen, selbst wenn Sie nur einen einzigen Standort bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="fd100-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="fd100-174">Informationen zum Einrichten einer Remote-PowerShell-Sitzung finden Sie unter: [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd100-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="fd100-175">Wenn keinem Benutzer ein PSTN-Standort zugewiesen ist, wird die hybridverbindung zwischen der Skype for Business Cloud Connector Edition-Bereitstellung und dem Office 365-Mandanten zurückgegeben, um die standardmäßige Mandantenebene (Peer-Ziel) zu verwenden, sodass Anrufe abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="fd100-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="fd100-176">Konfigurieren von Online-Hybrid Vermittlungsserver-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="fd100-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="fd100-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="fd100-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="fd100-178">Wenn ein P2P-Anruf an eine PSTN-Konferenz weitergeleitet wird, sendet der Skype for Business Online Konferenzserver eine Einladung an den Cloud Connector Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="fd100-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="fd100-179">Um sicherzustellen, dass Office 365 diese Einladung erfolgreich weiterleiten können, müssen Sie für jeden Cloud Connector eine Einstellung in Ihrem Online Mandanten Vermittlungsserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="fd100-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="fd100-180">Erstellen Sie einen Benutzer im Office 365 Administratorportal.</span><span class="sxs-lookup"><span data-stu-id="fd100-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="fd100-181">Verwenden Sie einen beliebigen Benutzernamen, beispielsweise "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="fd100-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="fd100-182">Verwenden Sie die standardmäßige SIP-Domäne von Cloud Connector (die erste SIP-Domäne in der INI-Datei) als Benutzerdomäne.</span><span class="sxs-lookup"><span data-stu-id="fd100-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="fd100-183">Beachten Sie, dass die Lizenzzuweisung nur für die Benutzerverteilung in das Skype for Business Online-Verzeichnis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fd100-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="fd100-184">Weisen Sie dem von Ihnen erstellten Konto eine Office 365 Lizenzen (wie E5) zu, lassen Sie bis zu einer Stunde für die Änderungen zu, überprüfen Sie, ob die Benutzerkonten ordnungsgemäß im Skype for Business Online-Verzeichnis bereitgestellt wurden, indem Sie das folgende Cmdlet ausführen, und entfernen Sie dann die Lizenz von diesem Konto.</span><span class="sxs-lookup"><span data-stu-id="fd100-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="fd100-185">Starten Sie einen Mandanten Azure AD Remote-PowerShell-Sitzung mit ihren globalen oder Benutzer Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die Abteilung für das Azure AD Benutzerkonto festzulegen, das in Schritt 1 auf "HybridMediationServer" konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="fd100-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="fd100-186">Starten Sie einen Mandanten Skype for Business Remote-PowerShell-Sitzung mit Ihren Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um den Vermittlungsserver \<und\> den Edgeserver-FQDN für dieses Benutzerkonto festzulegen und DisplayName durch den Anzeigenamen des Benutzers für das in Schritt 1 erstellte Konto zu ersetzen:</span><span class="sxs-lookup"><span data-stu-id="fd100-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="fd100-187">Verwenden Sie für Identity den Anzeigenamen des Office 365 Benutzerkontos, das Sie für diese Vermittlungsserver erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="fd100-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="fd100-188">Verwenden Sie für *MediationServerFQDN* den für Ihre Vermittlungsserver definierten internen FQDN.</span><span class="sxs-lookup"><span data-stu-id="fd100-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="fd100-189">Verwenden Sie für *EdgeServerExternalFQDN* den externen FQDN, der für Edgeserver Zugriffs Proxy definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fd100-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="fd100-190">Wenn mehrere Cloud Connector-PSTN-Standorte vorhanden sind, wählen Sie den FQDN des Edgeserver Zugriffsproxys, der dem Standort zugewiesen ist, auf dem sich der Vermittlungsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="fd100-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="fd100-191">Wenn mehrere Cloud Connector-Vermittlungsserver vorhanden sind (mehrere Standorte, ha), wiederholen Sie die vorherigen Schritte für jeden dieser Server.</span><span class="sxs-lookup"><span data-stu-id="fd100-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

