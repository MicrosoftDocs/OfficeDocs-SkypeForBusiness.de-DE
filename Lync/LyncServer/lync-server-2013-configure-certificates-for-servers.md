---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="1d893-102">Konfigurieren von Zertifikaten für Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d893-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d893-103">_**Letztes Änderungsdatum des Themas:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="1d893-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="1d893-104">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über die richtigen Berechtigungen delegiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1d893-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="1d893-105">Details zum Delegieren von Berechtigungen finden Sie unter Berechtigungen für das [Delegieren von Setup in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1d893-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="1d893-106">Je nach Organisation und Anforderungen für das Anfordern von Zertifikaten müssen Sie möglicherweise weitere Gruppenmitgliedschaften anfordern.</span><span class="sxs-lookup"><span data-stu-id="1d893-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="1d893-107">Konsultieren Sie die Gruppe, die Ihre PKI-Zertifizierungsstelle (Public Key Infrastructure) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1d893-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d893-108">Lync Server 2013 enthält Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digest-Längen von 224, 256, 384 oder 512-Bits) von Digest-Hash-und-Signaturalgorithmen für Verbindungen von Clients, auf denen Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista oder Windows XP-Betriebssysteme, zusätzlich zu lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1d893-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="1d893-109">Damit der externe Zugriff über die SHA-2-Suite unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit einem Digest gleicher Bitlänge ausstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1d893-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="1d893-110">Die Auswahl des verwendeten Hashdigests und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden sollen, sowie von den anderen Computern und Geräten, mit denen Clients und Server kommunizieren sollen, die ebenfalls imstande sein müssen, die im Zertifikat enthaltenen Algorithmen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d893-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="1d893-111">Informationen dazu, welche Digest-Längen im Betriebssystem und einigen Clientanwendungen unterstützt werden<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>, finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="1d893-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="1d893-112">Für jeden Standard Edition-Server oder Front-End-Server sind bis zu vier Zertifikate erforderlich: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein webinternes Zertifikat und ein externes Webzertifikat.</span><span class="sxs-lookup"><span data-stu-id="1d893-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="1d893-113">Es ist jedoch möglich, ein einzelnes Standardzertifikat mit den entsprechenden Einträgen für den alternativen Subjektnamen sowie das oAuthTokenIssuer-Zertifikat anzufordern und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d893-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="1d893-114">Details zu den Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1d893-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="1d893-115">Details zum anfordern, zuweisen und Installieren des oAuthTokenIssuer-Zertifikats finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="1d893-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="1d893-116">Gehen Sie wie folgt vor, um die Standard Edition-Server-oder Front-End-Serverzertifikate anzufordern, zuzuweisen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1d893-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="1d893-117">Wiederholen Sie den Vorgang für jeden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1d893-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d893-118">Im folgenden Verfahren wird beschrieben, wie Sie Zertifikate aus einer internen Unternehmens PKI, die von Ihrer Organisation bereitgestellt wird, und mit der Offline Anforderungsverarbeitung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1d893-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="1d893-119">Informationen zum Abrufen von Zertifikaten von einer öffentlichen Zertifizierungsstelle finden Sie unter <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Zertifikatanforderungen für interne Server in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d893-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="1d893-120">In diesem Verfahren wird auch beschrieben, wie Sie während der Einrichtung des Front-End-Servers Zertifikate anfordern, zuweisen und installieren.</span><span class="sxs-lookup"><span data-stu-id="1d893-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="1d893-121">Wenn Sie Zertifikate im Voraus angefordert haben, wie im Abschnitt <A href="lync-server-2013-request-certificates-in-advance-optional.md">anfordern von Zertifikaten im Voraus (optional) für lync Server 2013</A> dieser Bereitstellungsdokumentation beschrieben wird, oder wenn Sie keine interne, in Ihrer Organisation bereitgestellte Unternehmens PKI verwenden, um Zertifikate zu erhalten, müssen Sie dieses Verfahren nach Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="1d893-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="1d893-122">So konfigurieren Sie Zertifikate für einen Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="1d893-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="1d893-123">Klicken Sie im lync Server-Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="1d893-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="1d893-124">Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern**.</span><span class="sxs-lookup"><span data-stu-id="1d893-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="1d893-125">Klicken Sie auf der Seite **Zertifikatanforderung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="1d893-p107">Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Bei Auswahl dieser Option muss die interne Zertifizierungsstelle mit automatischer Onlineregistrierung verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Anschließend müssen Sie die Zertifikatantwort importieren und der entsprechenden Zertifikatrolle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d893-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="1d893-131">Wählen Sie auf der Seite Zertifizierungs **Stelle auswählen** die Option **eine Zertifizierungsstelle in der Liste in Ihrer Umgebung gefunden** auswählen aus, und wählen Sie dann in der Liste eine bekannte Zertifizierungsstelle (durch Registrierung in Active Directory-Domänendienste) aus.</span><span class="sxs-lookup"><span data-stu-id="1d893-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="1d893-132">Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.</span><span class="sxs-lookup"><span data-stu-id="1d893-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="1d893-133">Auf der Seite **Certificate Authority-Konto** werden Sie zur Eingabe der Anmeldeinformationen aufgefordert, um die Zertifikatanforderung bei der Zertifizierungsstelle anzufordern und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d893-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="1d893-134">Sie sollten festgestellt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um ein Zertifikat im Voraus anzufordern.</span><span class="sxs-lookup"><span data-stu-id="1d893-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="1d893-135">Ihr Zertifizierungsstellenadministrator verfügt über die erforderlichen Informationen und kann Sie in diesem Schritt unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1d893-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="1d893-136">Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie in den Textfeldern einen Benutzernamen und ein Kennwort ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="1d893-137">Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d893-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d893-p110">Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="1d893-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="1d893-140">Geben Sie auf der Seite **Name und Sicherheitseinstellungen** einen **Anzeigenamen** an, der es Ihnen ermöglichen soll, das Zertifikat und den Zweck zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1d893-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="1d893-141">Wenn Sie das Feld leer lassen, wird automatisch ein Name generiert.</span><span class="sxs-lookup"><span data-stu-id="1d893-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="1d893-142">Stellen Sie die **Bit-Länge** des Schlüssels ein, oder übernehmen Sie den Standardwert von 2048-Bits.</span><span class="sxs-lookup"><span data-stu-id="1d893-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="1d893-143">Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aus, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel verschoben oder auf andere Systeme kopiert werden müssen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d893-144">Lync Server 2013 verfügt über minimale Anforderungen für einen exportierbaren privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="1d893-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="1d893-145">Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d893-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="1d893-146">Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="1d893-147">Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="1d893-148">Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="1d893-149">Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne** und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="1d893-150">Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="1d893-p113">Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1d893-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="1d893-154">Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="1d893-155">Überprüfen Sie auf der Seite **Status der Online Zertifikatanforderung** die zurückgegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="1d893-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="1d893-156">Beachten Sie, dass das Zertifikat ausgestellt und im lokalen Zertifikatspeicher installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1d893-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="1d893-157">Wenn Sie als ausgestellt und installiert, aber ungültig gemeldet wird, stellen Sie sicher, dass das Zertifizierungsstellen-Stammzertifikat im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Servers installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1d893-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="1d893-158">Informationen zum Abrufen eines vertrauenswürdigen Stammzertifizierungsstellen-Zertifikats finden Sie in ihrer Zertifizierungsstellen-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d893-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="1d893-159">Wenn Sie das abgerufene Zertifikat anzeigen müssen, klicken Sie auf **Zertifikat Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1d893-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="1d893-160">Standardmäßig ist das Kontrollkästchen für **die Verwendung des Zertifikats für lync Server-Zertifikate zuweisen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1d893-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="1d893-161">Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1d893-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="1d893-162">Wenn Sie das Kontrollkästchen für **das Zuweisen des Zertifikats zu lync Server-Zertifikat Verwendungen** auf der vorherigen Seite deaktiviert haben, wird die Seite **zertifikatzuweisung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1d893-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="1d893-163">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="1d893-163">Click **Next**.</span></span>

18. <span data-ttu-id="1d893-p116">Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d893-166">Wenn auf der Status Seite der <STRONG>Online Zertifikatanforderung</STRONG> ein Problem mit dem Zertifikat gemeldet wurde, beispielsweise wenn das Zertifikat nicht gültig ist, kann die Anzeige des tatsächlichen Zertifikats bei der Lösung des Problems behilflich sein.</span><span class="sxs-lookup"><span data-stu-id="1d893-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="1d893-167">Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1d893-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="1d893-168">Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="1d893-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="1d893-169">Überprüfen Sie anhand der Informationen auf der Seite **Zusammenfassung der Zertifikatzuweisung**, dass es sich um das zuzuweisende Zertifikat handelt, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1d893-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="1d893-p118">Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1d893-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="1d893-173">Überprüfen Sie auf der Seite des **Zertifikat-Assistenten** , ob der **Status** des Zertifikats "zugewiesen" lautet, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="1d893-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d893-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d893-174">See Also</span></span>


[<span data-ttu-id="1d893-175">Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d893-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

