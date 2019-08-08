---
title: Konfigurieren des XMPP-Gateways auf lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e972b8729126615a375f4d82f4c378a71642a4fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="b0bb4-102">Konfigurieren des XMPP-Gateways auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0bb4-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0bb4-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b0bb4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b0bb4-104">Wenn Sie Richtlinien für die Unterstützung von Verbundpartnern des Extensible Messaging and Presence Protocol (XMPP) konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (im). (beispielsweise Windows Live) oder SIP-Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="b0bb4-105">Sie konfigurieren einen XMPP-Verbund Partner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="b0bb4-106">Sobald die Richtlinien vorhanden sind, umfassen zusätzliche Aufgaben die Konfiguration der XMPP-Gateway-Zertifikate, die Bereitstellung des lync Server 2013-XMPP-Gateways und schließlich das Aktualisieren der DNS-Einträge für das XMPP-Gateway.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="b0bb4-107">Konfigurieren von XMPP-Gateway-Zertifikaten auf dem lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b0bb4-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="b0bb4-108">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b0bb4-109">Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Run anstelle von Run erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="b0bb4-110">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="b0bb4-111">Klicken Sie auf der Seite **Zertifikatanforderung** auf **externes Zertifikat**.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="b0bb4-112">Aktivieren Sie auf der Seite **verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, aber später senden** .</span><span class="sxs-lookup"><span data-stu-id="b0bb4-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="b0bb4-113">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="b0bb4-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="b0bb4-114">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="b0bb4-115">Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="b0bb4-116">Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="b0bb4-117">Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von 2048) an.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="b0bb4-118">Überprüfen Sie, ob das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="b0bb4-119">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="b0bb4-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="b0bb4-120">Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="b0bb4-121">Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="b0bb4-122">Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="b0bb4-123">Aktivieren Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="b0bb4-124">Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b0bb4-125">Wenn der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (wie contoso.com) in den San-Einträgen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="b0bb4-126">Wenn Sie weitere Einträge benötigen, fügen Sie Sie in diesem Schritt hinzu.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="b0bb4-127">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="b0bb4-128">Nachdem die Befehle ausgeführt wurden, können Sie das **Protokoll anzeigen**oder auf **weiter** klicken, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="b0bb4-129">Auf der Seite **Zertifikatanforderungsdatei** können Sie die generierte CSR-Datei (Certificate Signing Request) anzeigen, indem Sie auf **Fertig stellen**klicken oder den Zertifikat-Assistenten verlassen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="b0bb4-130">Kopieren Sie die Anforderungsdatei, und senden Sie Sie an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="b0bb4-131">Nachdem Sie das öffentliche Zertifikat empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserver-Dienste beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="b0bb4-132">Hierzu geben Sie in der lync Server-Verwaltungskonsole Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b0bb4-133">Konfigurieren eines neuen lync Server 2013 XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="b0bb4-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b0bb4-134">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b0bb4-135">Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff** , und klicken Sie dann auf **XMPP Federated Partners**.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="b0bb4-136">Wenn Sie eine neue Konfiguration erstellen möchten, klicken Sie auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="b0bb4-137">Definieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-137">Define the following settings:</span></span>

5.  <span data-ttu-id="b0bb4-138">**Primäre Domäne**     (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="b0bb4-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="b0bb4-139">Die primäre Domäne ist die Basisdomäne des XMPP-Partners.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="b0bb4-140">Geben Sie beispielsweise **Fabrikam.com** für den Namen der XMPP-Partnerdomäne ein.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="b0bb4-141">Dies ist ein erforderlicher Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-141">This is a required entry.</span></span>

6.  <span data-ttu-id="b0bb4-142">**Beschreibung**   die Beschreibung gilt für Notizen oder andere identifizierende Informationen für diese bestimmte Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="b0bb4-143">Dieser Eintrag ist optional.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-143">This entry is optional.</span></span>

7.  <span data-ttu-id="b0bb4-144">**Zusätzliche**   Domänen zusätzliche Domänen sind Domänen, die Teil der Domäne Ihres XMPP-Partners sind und als Teil der zulässigen XMPP-Kommunikation enthalten sein sollten.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="b0bb4-145">Wenn es sich bei der primären Domäne beispielsweise um **Fabrikam.com**handelt, werden alle anderen Domänen aufgelistet, die unter fabrikam.com sind, mit denen Sie über XMPP kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="b0bb4-146">**Partnertyp**   der **Partnertyp** ist eine erforderliche Einstellung.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="b0bb4-147">Sie müssen eine der folgenden Optionen auswählen, um zu beschreiben und zu erzwingen, welche Kontakte hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="b0bb4-148">Sie können Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-148">You can select from:</span></span>
    
      - <span data-ttu-id="b0bb4-149">**Federated** Ein **Federated** -Partner-Typ stellt eine hohe Vertrauensebene zwischen der lync Server-Bereitstellung und dem XMPP-Partner dar.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="b0bb4-150">Dieser Partnertyp wird für die Föderation mit XMPP-Servern innerhalb desselben Unternehmens oder mit einer festgelegten Geschäftsbeziehung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="b0bb4-151">XMPP-Kontakte in Verbundpartnern können:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="b0bb4-152">Fügen Sie lync-Kontakte hinzu, und zeigen Sie deren Anwesenheit ohne ausdrückliche Autorisierung des lync-Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="b0bb4-153">Senden Sie Sofortnachrichten an lync-Kontakte, unabhängig davon, ob der lync-Benutzer Sie in seine Kontaktliste aufgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="b0bb4-154">Anzeigen der Status Notizen eines lync-Benutzers</span><span class="sxs-lookup"><span data-stu-id="b0bb4-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="b0bb4-155">**Öffentlich überprüft** ein **öffentlicher überprüfte** Partner ist ein öffentlicher XMPP-Anbieter, der als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="b0bb4-156">XMPP-Kontakte in öffentlich überprüfte Netzwerke können lync-Kontakte hinzufügen und deren Anwesenheit anzeigen und Ihnen Sofortnachrichten senden, ohne die ausdrückliche Autorisierung der lync-Benutzer zu haben.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="b0bb4-157">Bei XMPP-Kontakten in öffentlich überprüften Netzwerken werden die Status Notizen der lync-Benutzer nie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="b0bb4-158">Diese Einstellung wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="b0bb4-159">**Öffentliche nicht bestätigt** Ein **öffentlicher** , nicht überprüfter Partner ist ein öffentlicher XMPP-Anbieter, der nicht als vertrauenswürdig eingestuft wird, um die Identität seiner Benutzer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="b0bb4-160">XMPP-Benutzer in öffentlichen nicht überprüften Netzwerken können nicht mit lync-Benutzern kommunizieren, es sei denn, der lync-Benutzer hat Sie ausdrücklich autorisiert, indem Sie Sie der Kontaktliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="b0bb4-161">Für XMPP-Benutzer in öffentlichen nicht überprüften Netzwerken werden die Status Notizen von lync-Benutzern nie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="b0bb4-162">Diese Einstellung wird für alle Föderationen mit öffentlichen XMPP-Anbietern wie Google Talk empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="b0bb4-163">**Verbindungstyp:** Definiert die verschiedenen Regeln und Dialback-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="b0bb4-164">**TLS**   -Aushandlung definiert die TLS-Aushandlungs Regeln.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="b0bb4-165">Ein XMPP-Dienst kann TLS erfordern, kann TLS optional machen, oder Sie definieren, dass TLS nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="b0bb4-166">Wenn Sie optional auswählen, bleibt die Anforderung dem XMPP-Dienst für eine obligatorische Aushandlungs Entscheidung überlassen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="b0bb4-167">So zeigen Sie alle möglichen Einstellungen und Details für SASL-, TLS-und Dialback-Aushandlung an – einschließlich Ungültiger und bekannter Fehler Konfigurationen – finden Sie unter Aushandlungs [Einstellungen für XMPP-Verbundpartner in lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="b0bb4-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="b0bb4-168">**Erforderlich**   der XMPP-Dienst erfordert TLS-Aushandlung.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="b0bb4-169">**Optional**   : der XMPP-Dienst gibt an, dass TLS obligatorisch-zu-Negotiate ist.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="b0bb4-170">**Nicht unterstützt**   der XMPP-Dienst unterstützt keine TLS-Funktion.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="b0bb4-171">**SASL**   -Aushandlung definiert die SASL-Aushandlungs Regeln.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="b0bb4-172">Ein XMPP-Dienst kann SASL erfordern, kann SASL optional machen, oder Sie definieren, dass SASL nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="b0bb4-173">Wenn Sie optional auswählen, bleibt die Anforderung dem Partner XMPP-Dienst für eine obligatorische-zu-Aushandlungs Entscheidung überlassen.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="b0bb4-174">**Erforderlich**   der XMPP-Dienst erfordert SASL-Aushandlung.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="b0bb4-175">**Optional**   zeigt der XMPP-Dienst an, dass SASL obligatorisch-zu-Negotiate ist.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="b0bb4-176">**Nicht unterstützt**   der XMPP-Dienst unterstützt keine SASL-Funktion.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="b0bb4-177">**Support Server-Dialback** -Aushandlung Der Dialback-Aushandlungsprozess für Support Server verwendet das Domain Name System (DNS) und einen autorisierenden Server, um zu überprüfen, ob die Anforderung von einem gültigen XMPP-Partner kam.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="b0bb4-178">Zu diesem Zweck erstellt der ursprüngliche Server eine Nachricht eines bestimmten Typs mit einem generierten Dialback-Schlüssel und schlägt den empfangenden Server in DNS nach.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="b0bb4-179">Der ursprüngliche Server sendet den Schlüssel in einem XML-Datenstrom an den resultierenden DNS-Lookup, vermutlich den empfangenden Server.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="b0bb4-180">Nach Erhalt des Schlüssels über den XML-Datenstrom antwortet der empfangende Server nicht auf den ursprünglichen Server, sondern sendet den Schlüssel an einen bekannten autorisierenden Server.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="b0bb4-181">Der autorisierende Server überprüft, ob der Schlüssel entweder gültig oder ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="b0bb4-182">Wenn dies nicht der Fall ist, antwortet der empfangende Server nicht auf den ursprünglichen Server.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="b0bb4-183">Wenn der Schlüssel gültig ist, informiert der empfangende Server den Ursprungsserver, dass Identität und Schlüssel gültig sind und die Konversation beginnen kann.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="b0bb4-184">Es gibt zwei gültige Zustände für **Dialback**-Aushandlung:</span><span class="sxs-lookup"><span data-stu-id="b0bb4-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="b0bb4-185">**True**   : der XMPP-Server ist für die Verwendung von Dialback-Aushandlung konfiguriert, wenn eine Anforderung von einem Ursprungsserver empfangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="b0bb4-186">**Falsch**   der XMPP-Server ist nicht für die Verwendung von Dialback-Aushandlung konfiguriert, und wenn eine Anforderung von einem Ursprungsserver empfangen werden soll, wird Sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="b0bb4-187">Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b0bb4-188">Aktualisieren von DNS-Einträgen für lync Server 2013 XMPP-Gateway</span><span class="sxs-lookup"><span data-stu-id="b0bb4-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b0bb4-189">Zum Konfigurieren von DNS für die XMPP-Föderation fügen Sie den folgenden SRV-Eintrag zu Ihrem\_externen DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Access-Edge-FQDN des Edge-Servers mit einem Portwert von 5269 aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="b0bb4-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

