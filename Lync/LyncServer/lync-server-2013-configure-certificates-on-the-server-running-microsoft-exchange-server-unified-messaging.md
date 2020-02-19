---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="b47ae-102">Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft</span><span class="sxs-lookup"><span data-stu-id="b47ae-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b47ae-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b47ae-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b47ae-104">Wenn Sie Exchange Unified Messaging (um) bereitgestellt haben, wie unter [Planen der Integration von Exchange Unified Messaging in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in der Planungsdokumentation beschrieben, und Sie den Enterprise-VoIP-Benutzern in Ihrer Organisation Exchange um Funktionen bereitstellen möchten, können Sie die folgenden Verfahren zum Konfigurieren des Zertifikats auf dem Server verwenden, auf dem Exchange um läuft.</span><span class="sxs-lookup"><span data-stu-id="b47ae-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b47ae-105">Bei internen Zertifikaten müssen sowohl die Server mit lync Server 2013 als auch die Server, auf denen Microsoft Exchange läuft, vertrauenswürdige Stammzertifizierungsstellen Zertifikate besitzen, die gegenseitig vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="b47ae-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="b47ae-106">Die Zertifizierungsstelle (Certification Authority, ca) kann identisch sein oder eine andere Zertifizierungsstelle, solange die Stammzertifikate der Zertifizierungsstelle in Ihrem Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen registriert sind.</span><span class="sxs-lookup"><span data-stu-id="b47ae-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="b47ae-107">Das Exchange Server muss mit einem Server Zertifikat konfiguriert sein, damit eine Verbindung mit lync Server 2013 hergestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="b47ae-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="b47ae-108">Laden Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="b47ae-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="b47ae-109">Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="b47ae-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="b47ae-110">Vergewissern Sie sich, dass sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Computers mit Exchange Server befindet.</span><span class="sxs-lookup"><span data-stu-id="b47ae-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="b47ae-111">Erstellen Sie eine Zertifikatanforderung für den Computer mit Exchange Server, und installieren Sie das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="b47ae-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="b47ae-112">Weisen Sie das Zertifikat für den Computer mit Exchange Server zu.</span><span class="sxs-lookup"><span data-stu-id="b47ae-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="b47ae-113">So laden Sie das Zertifizierungsstellenzertifikat herunter</span><span class="sxs-lookup"><span data-stu-id="b47ae-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="b47ae-114">Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **\<http://Namen des ausstellenden Zertifizierungsstellenservers\>/certsrv ein**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="b47ae-115">Klicken Sie unter **Task auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="b47ae-116">Wählen Sie unter **Herunterladen eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL** **die Option Encoding method to base 64**aus, und klicken Sie dann auf **Zertifizierungsstellenzertifikat herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b47ae-117">In diesem Schritt können Sie auch die Encoding-Codierungsregeln (Distinguished Encoding Rules, der) angeben.</span><span class="sxs-lookup"><span data-stu-id="b47ae-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="b47ae-118">Beachten Sie Folgendes, wenn Sie die DER-Codierung auswählen: Der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 unter <STRONG>So installieren Sie das Zertifizierungsstellenzertifikat</STRONG> ist P7B und nicht CER.</span><span class="sxs-lookup"><span data-stu-id="b47ae-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="b47ae-p103">Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**, und speichern Sie die Datei auf der Festplatte des Servers. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie im vorherigen Schritt gewählt haben.)</span><span class="sxs-lookup"><span data-stu-id="b47ae-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="b47ae-121">So installieren Sie das Zertifizierungsstellenzertifikat</span><span class="sxs-lookup"><span data-stu-id="b47ae-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="b47ae-122">Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, Microsoft Management Console (MMC), indem Sie auf **Start**und dann auf **Ausführen**klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="b47ae-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="b47ae-123">Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="b47ae-124">Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="b47ae-125">Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="b47ae-126">Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole läuft)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="b47ae-127">Klicken Sie auf **Schließen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="b47ae-128">Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)** und dann **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie anschließend auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="b47ae-129">Klicken Sie mit der rechten Maustaste auf **Zertifikate**, und klicken Sie dann auf **Alle Tasks** und **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="b47ae-130">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-130">Click **Next**.</span></span>

10. <span data-ttu-id="b47ae-p104">Klicken Sie auf **Durchsuchen**, um auf die Datei zuzugreifen, und klicken Sie dann auf **Weiter**. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie in Schritt 3 unter **So laden Sie das Zertifizierungsstellenzertifikat herunter** gewählt haben.)</span><span class="sxs-lookup"><span data-stu-id="b47ae-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="b47ae-133">Aktivieren Sie die Option **Alle Zertifikate in folgendem Speicher speichern**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="b47ae-134">Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="b47ae-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="b47ae-135">Klicken Sie auf **Weiter**, um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="b47ae-136">So überprüfen Sie, ob die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen aufgeführt ist</span><span class="sxs-lookup"><span data-stu-id="b47ae-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="b47ae-137">Erweitern Sie auf dem Server mit Exchange um unter MMC die Option **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="b47ae-138">Überprüfen Sie im Detailbereich, ob Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="b47ae-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="b47ae-139">So konfigurieren Sie Exchange Server 2013 um mit lync Server</span><span class="sxs-lookup"><span data-stu-id="b47ae-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="b47ae-140">Ausführliche Informationen finden Sie unter "integrieren Exchange 2013 um mit lync Server" in die Exchange Server Dokumentation [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)unter.</span><span class="sxs-lookup"><span data-stu-id="b47ae-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="b47ae-141">So erstellen Sie eine Zertifikatanforderung und installieren Sie das Zertifikat auf Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b47ae-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="b47ae-142">Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **\<http://** Namen des ausstellenden Zertifizierungsstellenservers**\>/certsrv ein**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="b47ae-143">Klicken Sie unter **Task auswählen** auf **Zertifikat anfordern**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="b47ae-144">Klicken Sie unter **Zertifikat anfordern** auf **Erweiterte Zertifikatanforderung**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="b47ae-145">Klicken Sie unter **Erweiterte Zertifikatanforderung** auf **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="b47ae-146">Wählen Sie unter **Erweiterte Zertifikatanforderung** den Eintrag **Webserver** oder eine andere für die Serverauthentifizierung konfigurierte Serverzertifikatvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="b47ae-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="b47ae-147">Geben Sie unter **identifizierende Informationen für Offline Vorlage**im Feld **Name** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange Server ein.</span><span class="sxs-lookup"><span data-stu-id="b47ae-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b47ae-148">Sie müssen den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b47ae-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="b47ae-149">Aktivieren Sie unter **Schlüsseloptionen** das Kontrollkästchen **Zertifikat in lokalem Zertifikatspeicher aufbewahren**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="b47ae-150">Klicken Sie unten auf der Webseite auf die Schaltfläche **Absenden**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="b47ae-151">Klicken Sie im Bestätigungsdialogfeld auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="b47ae-152">Klicken Sie auf der Seite **Zertifikat wurde ausgestellt** auf **Dieses Zertifikat installieren**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="b47ae-153">Klicken Sie im Bestätigungsdialogfeld auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="b47ae-154">Vergewissern Sie sich, dass die folgende Meldung angezeigt wird: Das neue Zertifikat wurde installiert.</span><span class="sxs-lookup"><span data-stu-id="b47ae-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="b47ae-155">So erstellen Sie ein Zertifikat auf Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="b47ae-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="b47ae-156">Melden Sie sich bei dem Server an, auf dem Exchange um mit den entsprechenden Benutzerrechten ausführt.</span><span class="sxs-lookup"><span data-stu-id="b47ae-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="b47ae-157">Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)unter.</span><span class="sxs-lookup"><span data-stu-id="b47ae-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="b47ae-158">Anweisungen zum Erstellen des Zertifikats finden Sie in den folgenden Vorgehensweisen:</span><span class="sxs-lookup"><span data-stu-id="b47ae-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="b47ae-159">"Erstellen eines neuen Exchange-Zertifikats" unter[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="b47ae-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="b47ae-160">"Importieren eines Exchange-Zertifikats" unter[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="b47ae-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b47ae-161">Im Feld <STRONG>Antragstellername</STRONG> des Zertifikats müssen Sie den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b47ae-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="b47ae-162">So weisen Sie das Zertifikat auf Exchange Server 2007 (SP1) zu</span><span class="sxs-lookup"><span data-stu-id="b47ae-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="b47ae-163">Öffnen Sie auf dem Server mit Exchange um MMC.</span><span class="sxs-lookup"><span data-stu-id="b47ae-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="b47ae-164">Erweitern Sie in der Konsolenstruktur den Eintrag **Persönlich**, und klicken Sie auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="b47ae-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="b47ae-165">Vergewissern Sie sich, dass im Detailfenster Ihr eigenes Zertifikat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b47ae-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="b47ae-166">Doppelklicken Sie auf das Zertifikat, um die Details zu lesen und sicherzustellen, dass es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b47ae-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b47ae-167">Es kann eine Weile dauern, bis das Zertifikat als gültig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b47ae-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="b47ae-168">Starten Sie den Microsoft Exchange Unified Messaging-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b47ae-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b47ae-169">Der Server, auf dem Exchange Server 2007 SP1 Unified Messaging ausgeführt wird, ruft automatisch das richtige Zertifikat ab.</span><span class="sxs-lookup"><span data-stu-id="b47ae-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="b47ae-170">Öffnen Sie die Ereignisanzeige, und suchen Sie nach der Ereignis-ID 1112. Dieses Ereignis gibt an, welches Zertifikat der Server, auf dem Exchange Server 2007 SP1 Unified Messaging ausgeführt wird, abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b47ae-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="b47ae-171">So weisen Sie das Zertifikat auf Exchange Server 2010 zu</span><span class="sxs-lookup"><span data-stu-id="b47ae-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="b47ae-172">Melden Sie sich bei dem Server an, auf dem Exchange um mit den entsprechenden Benutzerrechten ausführt.</span><span class="sxs-lookup"><span data-stu-id="b47ae-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="b47ae-173">Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)unter.</span><span class="sxs-lookup"><span data-stu-id="b47ae-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="b47ae-174">Das Verfahren zum Zuweisen des Zertifikats finden Sie unter "Zuweisen von Diensten zu einem Zertifikat" [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)unter.</span><span class="sxs-lookup"><span data-stu-id="b47ae-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

