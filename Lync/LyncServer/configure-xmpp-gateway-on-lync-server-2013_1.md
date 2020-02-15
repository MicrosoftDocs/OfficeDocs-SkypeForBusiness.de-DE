---
title: Konfigurieren des XMPP-Gateways auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5735c9e4786548ce7b12ab82327ffc72c27873bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="ea717-102">Konfigurieren des XMPP-Gateways auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea717-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea717-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ea717-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ea717-104">Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartnern (extensible Messaging and Presence Protocol) gelten die Richtlinien für Benutzer von XMPP-Partnerverbunddomänen, aber nicht für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder von SIP-Partnerverbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="ea717-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="ea717-105">Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Partnerverbunddomäne, der Ihre Benutzer Kontakte hinzufügen und mit der sie kommunizieren sollen können.</span><span class="sxs-lookup"><span data-stu-id="ea717-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="ea717-106">Sobald die Richtlinien vorhanden sind, umfassen zusätzliche Aufgaben das Konfigurieren der XMPP-Gateway-Zertifikate, die Bereitstellung des lync Server 2013 XMPP-Gateways und das schließliche Aktualisieren der DNS-Einträge für das XMPP-Gateway.</span><span class="sxs-lookup"><span data-stu-id="ea717-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="ea717-107">Konfigurieren von XMPP-Gatewayzertifikaten auf dem Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="ea717-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="ea717-108">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ea717-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="ea717-109">Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird anstelle von "Erneut ausführen" die Option "Ausführen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea717-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="ea717-110">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ea717-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="ea717-111">Klicken Sie auf der Seite **Zertifikatanforderung** auf **Externes Edgezertifikat**.</span><span class="sxs-lookup"><span data-stu-id="ea717-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="ea717-112">Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden**.</span><span class="sxs-lookup"><span data-stu-id="ea717-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="ea717-113">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: Zertifikat "\_Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="ea717-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="ea717-114">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea717-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="ea717-115">Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="ea717-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="ea717-116">Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="ea717-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="ea717-117">Geben Sie unter **Bitlänge** die Bitlänge ein (normalerweise wird der Standardwert 2048 verwendet).</span><span class="sxs-lookup"><span data-stu-id="ea717-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="ea717-118">Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea717-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="ea717-119">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="ea717-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="ea717-120">Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="ea717-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="ea717-p102">Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.</span><span class="sxs-lookup"><span data-stu-id="ea717-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="ea717-123">Aktivieren Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** das Kontrollkästchen Domäne, um ein SIP hinzuzufügen. \<sipdomain "\> -Eintrag zur Liste der alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="ea717-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="ea717-124">Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea717-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="ea717-p103">Bei der Installation des XMPP-Proxys wird in den Einträgen für den alternativen Antragstellernamen standardmäßig der Domänenname (z. B. contoso.com) gefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie diese in diesem Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="ea717-p103">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="ea717-127">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea717-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="ea717-128">Nachdem die Ausführung der Befehle abgeschlossen ist, können Sie die Option \*\*Protokoll anzeigen \*\* verwenden oder auf **Weiter** klicken, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="ea717-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="ea717-129">Auf der Seite **Zertifikatsanforderungsdatei** können Sie die erstellte Datei für Signieranforderung für das Zertifikat anzeigen, indem Sie auf "Anzeigen" klicken, oder Sie können den Zertifikat-Assistenten beenden, indem Sie auf **Fertig stellen** klicken.</span><span class="sxs-lookup"><span data-stu-id="ea717-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="ea717-130">Kopieren Sie die Anforderungsdatei, und übermitteln Sie diese an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="ea717-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="ea717-p104">Nachdem das öffentliche Zertifikat empfangen, importiert und zugewiesen wurde, müssen Sie die Edgeserverdienste beenden und neu starten. Geben Sie in der Lync Server-Verwaltungskonsole dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ea717-p104">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="ea717-133">Konfigurieren eines neuen Lync Server 2013-XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="ea717-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="ea717-134">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ea717-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="ea717-135">Klicken Sie in der linken Navigationsleiste auf **Partnerverbund- und
externer Zugriff** und dann auf **XMPP-Verbundpartner**.</span><span class="sxs-lookup"><span data-stu-id="ea717-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="ea717-136">Klicken Sie auf **Neu**, um eine neue Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea717-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="ea717-137">Definieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ea717-137">Define the following settings:</span></span>

5.  <span data-ttu-id="ea717-138">**Primäre Domäne**     (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="ea717-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="ea717-139">Die primäre Domäne ist die Basisdomäne des XMPP-Partners.</span><span class="sxs-lookup"><span data-stu-id="ea717-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="ea717-140">Sie können beispielsweise **fabrikam.com** als Domänennamen für den XMPP-Partner eingeben.</span><span class="sxs-lookup"><span data-stu-id="ea717-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="ea717-141">Dies ist ein erforderlicher Eintrag.</span><span class="sxs-lookup"><span data-stu-id="ea717-141">This is a required entry.</span></span>

6.  <span data-ttu-id="ea717-142">**Description**   die Beschreibung ist für Notizen oder andere identifizierende Informationen für diese bestimmte Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ea717-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="ea717-143">Dieser Eintrag ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea717-143">This entry is optional.</span></span>

7.  <span data-ttu-id="ea717-144">**Zusätzliche**   Domänen zusätzliche Domänen sind Domänen, die Bestandteil der Domäne Ihres XMPP-Partners sind, die als Teil der zulässigen XMPP-Kommunikation einbezogen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ea717-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="ea717-145">Wenn die primäre Domäne z. B. **fabrikam.com** lautet, führen Sie alle anderen Domänen von "fabrikam.com" auf, mit denen Sie per XMPP kommunizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ea717-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="ea717-146">**Partnertyp**   der **Partnertyp** ist eine erforderliche Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ea717-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="ea717-147">Wählen Sie eine der folgenden Optionen aus, um zu beschreiben und vorzugeben, welche Kontakte hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="ea717-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="ea717-148">Die Optionen lauten:</span><span class="sxs-lookup"><span data-stu-id="ea717-148">You can select from:</span></span>
    
      - <span data-ttu-id="ea717-149">**Verbund** Ein **Verbund** Partnertyp stellt eine hohe Vertrauensebene zwischen der lync Server-Bereitstellung und dem XMPP-Partner dar.</span><span class="sxs-lookup"><span data-stu-id="ea717-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="ea717-150">Dieser Partnertyp wird für Verbunde mit XMPP-Servern in demselben Unternehmen oder bei Verwendung einer festen Geschäftsbeziehung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ea717-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="ea717-151">Für XMPP-Kontakte bestehen unter "Verbund" folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="ea717-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="ea717-152">Hinzufügen von Lync-Kontakten und Anzeigen der Anwesenheit ohne Schnellautorisierung durch den Lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="ea717-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="ea717-153">Senden von Chatnachrichten an Lync-Kontakte (unabhängig davon, ob der Lync-Benutzer diese seiner Kontaktliste hinzugefügt hat)</span><span class="sxs-lookup"><span data-stu-id="ea717-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="ea717-154">Anzeigen der Statusinformationen von Lync-Benutzern</span><span class="sxs-lookup"><span data-stu-id="ea717-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="ea717-155">**Public** verifyed ein **öffentlich überprüfter** Partner ist ein öffentlicher XMPP-Anbieter, der als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ea717-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="ea717-156">XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können Lync-Kontakte hinzufügen, ihre Anwesenheit anzeigen und ihnen Chatnachrichten ohne Schnellautorisierung durch die Lync-Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="ea717-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="ea717-157">XMPP-Kontakte in Netzwerken vom Typ "Überprüft öffentlich" können jedoch keine Statusinformationen von Lync-Benutzern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea717-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="ea717-158">Diese Einstellung ist nicht zu empfehlen.</span><span class="sxs-lookup"><span data-stu-id="ea717-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="ea717-p111">**Nicht überprüft öffentlich**   Ein Partner vom Typ **Nicht überprüft öffentlich** ist ein öffentlicher XMPP-Anbieter, der nicht über die Vertrauenswürdigkeit zum Überprüfen der Identität seiner Benutzer verfügt. XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können mit Lync-Benutzern nur kommunizieren, wenn der Lync-Benutzer sie per Hinzufügung zur Kontaktliste ausdrücklich dazu autorisiert hat. XMPP-Benutzer in Netzwerken vom Typ "Nicht überprüft öffentlich" können keine Statusinformationen von Lync-Benutzern anzeigen. Diese Einstellung ist für Verbunde mit öffentlichen XMPP-Anbietern wie Google Talk zu empfehlen.</span><span class="sxs-lookup"><span data-stu-id="ea717-p111">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="ea717-163">**Verbindungstyp:** Dient zum Definieren der verschiedenen Regeln und Rückrufeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ea717-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="ea717-164">**TLS-Aushandlung**   definiert die TLS-Aushandlungs Regeln.</span><span class="sxs-lookup"><span data-stu-id="ea717-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="ea717-165">Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ea717-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="ea717-166">Bei Auswahl von optional wird die Anforderung für eine obligatorische Aushandlungs Entscheidung für den XMPP-Dienst erfüllt.</span><span class="sxs-lookup"><span data-stu-id="ea717-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="ea717-167">Anzeigen aller möglichen Einstellungen und Details für SASL-, TLS-und Rückruf-Aushandlung – einschließlich nicht gültiger und bekannter Fehler Konfigurationen – Informationen finden Sie unter [Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="ea717-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="ea717-168">**Erforderlich**   der XMPP-Dienst erfordert TLS-Aushandlung.</span><span class="sxs-lookup"><span data-stu-id="ea717-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="ea717-169">**Optional**   der XMPP-Dienst gibt an, dass TLS für die Verhandlung obligatorisch ist.</span><span class="sxs-lookup"><span data-stu-id="ea717-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="ea717-170">**Nicht unterstützt**   der XMPP-Dienst unterstützt keine TLS-Daten.</span><span class="sxs-lookup"><span data-stu-id="ea717-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="ea717-171">**Die SASL-Aushandlung**   definiert die SASL-Aushandlungs Regeln.</span><span class="sxs-lookup"><span data-stu-id="ea717-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="ea717-172">Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ea717-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="ea717-173">Wenn Sie die Option optional auswählen, bleibt die Anforderung bis zum Partner-XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="ea717-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="ea717-174">**Erforderlich**   der XMPP-Dienst erfordert SASL-Aushandlung.</span><span class="sxs-lookup"><span data-stu-id="ea717-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="ea717-175">**Optional**   der XMPP-Dienst gibt an, dass SASL für die Aushandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ea717-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="ea717-176">**Nicht unterstützt**   der XMPP-Dienst unterstützt SASL nicht.</span><span class="sxs-lookup"><span data-stu-id="ea717-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="ea717-177">**Unterstützung für Server-Rückruf Verhandlung** Der Rückruf-Aushandlungsprozess des Support Servers verwendet das DNS (Domain Name System) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner stammt.</span><span class="sxs-lookup"><span data-stu-id="ea717-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="ea717-178">Hierzu erstellt der Ausgangsserver eine Meldung eines bestimmten Typs mit einem generierten Rückrufschlüssel und schlägt den empfangenden Server im DNS nach.</span><span class="sxs-lookup"><span data-stu-id="ea717-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="ea717-179">Der Ausgangsserver sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, wahrscheinlich an den empfangenden Server.</span><span class="sxs-lookup"><span data-stu-id="ea717-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="ea717-180">Wenn der Schlüssel über den XML-Datenstrom empfangen wird, antwortet der empfangende Server dem Ausgangsserver nicht, sondern sendet den Schlüssel aber an einen bekannten autoritativen Server.</span><span class="sxs-lookup"><span data-stu-id="ea717-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="ea717-181">Der autoritative Server überprüft die Gültigkeit des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="ea717-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="ea717-182">Wenn der Schlüssel nicht gültig ist, antwortet der empfangende Server dem Ausgangsserver nicht.</span><span class="sxs-lookup"><span data-stu-id="ea717-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="ea717-183">Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ausgangsserver, dass die Identität und der Schlüssel gültig sind und dass die Unterhaltung beginnen kann.</span><span class="sxs-lookup"><span data-stu-id="ea717-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="ea717-184">Für die **Rückrufaushandlung** gibt es zwei gültige Statusangaben:</span><span class="sxs-lookup"><span data-stu-id="ea717-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="ea717-185">**True**   der XMPP-Server ist für die Verwendung der Rückruf-Aushandlung konfiguriert, wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea717-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="ea717-186">**False**   der XMPP-Server ist nicht für die Verwendung der Rückruf-Aushandlung konfiguriert, und wenn eine Anforderung von einem ursprünglichen Server empfangen werden soll, wird Sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ea717-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="ea717-187">Klicken Sie auf **Commit ausführen**, um die Änderungen an der Standort- oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ea717-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="ea717-188">Aktualisieren der DNS-Einträge für das Lync Server 2013-XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="ea717-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="ea717-189">Um DNS für den XMPP-Verbund zu konfigurieren, fügen Sie den folgenden SRV-Eintrag zu\_Ihrem externen DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Zugriffs-Edge-FQDN des Edgeserver mit dem Portwert 5269 aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="ea717-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

