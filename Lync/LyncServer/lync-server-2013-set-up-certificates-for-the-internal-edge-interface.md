---
title: 'Lync Server 2013: Einrichten der Zertifikate für die interne Edgeschnittstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="a51d7-102">Einrichten der Zertifikate für die interne Edgeschnittstelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51d7-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51d7-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a51d7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a51d7-104">Wenn Sie den Zertifikat-Assistenten ausführen, stellen Sie sicher, dass Sie mit einem Konto angemeldet sind, das Mitglied einer Gruppe ist, der die entsprechenden Berechtigungen für den Typ der Zertifikatvorlage zugewiesen wurden, die Sie verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="a51d7-105">Standardmäßig verwendet eine lync Server 2013-Zertifikatanforderung die Webserverzertifikatvorlage.</span><span class="sxs-lookup"><span data-stu-id="a51d7-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="a51d7-106">Wenn Sie ein Konto verwenden, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat mithilfe dieser Vorlage anzufordern, stellen Sie sicher, dass der Gruppe die für die Verwendung dieser Vorlage erforderlichen Registrierungsberechtigungen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="a51d7-107">Auf der internen Schnittstelle jedes Edgeserver ist ein einzelnes Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a51d7-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="a51d7-108">Zertifikate für die interne Schnittstelle können von einer internen Zertifizierungsstelle (Enterprise Certification Authority, ca) oder einer öffentlichen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="a51d7-109">Wenn Ihre Organisation über eine interne Zertifizierungsstelle verfügt, können Sie auf Kosten der Verwendung öffentlicher Zertifikate sparen, indem Sie die interne Zertifizierungsstelle verwenden, um das Zertifikat für die interne Schnittstelle auszustellen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="a51d7-110">Sie können eine interne Windows Server 2008-Zertifizierungsstelle oder eine Windows Server 2008 R2-Zertifizierungsstelle zum Erstellen dieser Zertifikate verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="a51d7-111">Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a51d7-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="a51d7-112">Gehen Sie wie folgt vor, um Zertifikate auf der Schnittstelle für den internen Edge an einer Website einzurichten:</span><span class="sxs-lookup"><span data-stu-id="a51d7-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="a51d7-113">Laden Sie die Zertifizierungsstellen Zertifizierungsstelle für die interne Schnittstelle für jeden Edgeserver herunter.</span><span class="sxs-lookup"><span data-stu-id="a51d7-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="a51d7-114">Importieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle auf jedem Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a51d7-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="a51d7-115">Erstellen Sie die Zertifikatanforderung für die interne Schnittstelle auf einem Edgeserver, dem sogenannten First Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a51d7-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="a51d7-116">Importieren Sie das Zertifikat für die interne Schnittstelle auf dem First Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a51d7-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="a51d7-117">Importieren Sie das Zertifikat auf den anderen Edgeserver auf dieser Website (oder hinter diesem Lastenausgleichsmodul bereitgestellt).</span><span class="sxs-lookup"><span data-stu-id="a51d7-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="a51d7-118">Weisen Sie das Zertifikat für die interne Schnittstelle jedes Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="a51d7-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="a51d7-119">Wenn Sie mehr als eine Website mit Edgeserver (also einer mehrseitigen Edge-Topologie) oder getrennte Gruppen von Edgeserver haben, die hinter unterschiedlichen Lastenausgleichs Servern bereitgestellt werden, müssen Sie diese Schritte für jede Website mit Edgeserver und für jede Gruppe von Edgeserver ausführen. wird hinter einem anderen Load Balancer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a51d7-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a51d7-120">Die Schritte für die Verfahren in diesem Abschnitt basieren auf der Verwendung einer Windows&nbsp;Server 2008-Zertifizierungs&nbsp;Stelle&nbsp;, einer Windows Server 2008 R2-Zertifizierungsstelle, einer Windows Server 2012-Zertifizierungsstelle oder einer Windows Server 2012 R2-Zertifizierungsstelle zum Erstellen eines Zertifikats für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a51d7-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="a51d7-121">Eine Schritt-für-Schritt-Anleitung für jede andere Zertifizierungsstelle finden Sie in der Dokumentation für diese Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="a51d7-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="a51d7-122">Standardmäßig verfügen alle authentifizierten Benutzer über die entsprechenden Benutzerrechte zum Anfordern von Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="a51d7-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="a51d7-123">Die Verfahren in diesem Abschnitt basieren auf dem Erstellen von Zertifikatanforderungen auf dem Edgeserver als Teil des Edgeserver-Bereitstellungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="a51d7-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="a51d7-124">Es ist möglich, Zertifikatanforderungen mit dem Front-End-Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="a51d7-125">Sie können dies tun, um die Zertifikatanforderung zu einem frühen Zeitpunkt des Planungs-und Bereitstellungsprozesses abzuschließen, bevor Sie die Bereitstellung der Edgeserver starten.</span><span class="sxs-lookup"><span data-stu-id="a51d7-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="a51d7-126">Dafür müssen Sie sicherstellen, dass das von Ihnen angeforderte Zertifikat mit einem exportierbaren privaten Schlüssel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a51d7-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="a51d7-127">Die Verfahren in diesem Abschnitt beschreiben die Verwendung einer CER-und einer P7B-Datei für das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="a51d7-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="a51d7-128">Wenn Sie einen anderen Dateityp verwenden, ändern Sie diese Verfahren nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="a51d7-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="a51d7-129">So laden Sie die Zertifizierungsstellen Zertifizierungsstelle für die interne Schnittstelle mithilfe der CertSrv-Website herunter</span><span class="sxs-lookup"><span data-stu-id="a51d7-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="a51d7-130">Melden Sie sich bei einem lync Server 2013-Server im internen Netzwerk (also nicht beim Edgeserver) als Mitglied der Gruppe **Administratoren** an.</span><span class="sxs-lookup"><span data-stu-id="a51d7-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="a51d7-131">Führen Sie den folgenden Befehl an einer Eingabeaufforderung aus, indem Sie auf **Start**und dann auf **Ausführen**klicken und dann Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="a51d7-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="a51d7-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a51d7-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51d7-133">Wenn Sie eine Windows Server 2008-oder Windows Server 2008 R2 Enterprise-Zertifizierungsstelle verwenden, müssen Sie HTTPS und nicht http verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="a51d7-134">Klicken Sie auf der CertSrv-Webseite der ausstellenden Zertifizierungsstelle unter **Aufgabe auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatssperrliste**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="a51d7-135">Klicken Sie unter **Herunterladen eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL**auf **Zertifizierungsstellenzertifikat Kette herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="a51d7-136">Klicken Sie im Dialogfeld **Datei Download** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="a51d7-137">Speichern Sie die P7B-Datei auf dem Festplattenlaufwerk auf dem Server, und kopieren Sie Sie dann in einen Ordner auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a51d7-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51d7-138">Die P7B-Datei enthält alle Zertifikate, die im Zertifizierungspfad enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a51d7-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="a51d7-139">Wenn Sie den Zertifizierungspfad anzeigen möchten, öffnen Sie das Serverzertifikat, und klicken Sie auf den Zertifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="a51d7-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="a51d7-140">So exportieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle mithilfe von MMC</span><span class="sxs-lookup"><span data-stu-id="a51d7-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="a51d7-141">Mit der Microsoft Management Console (MMC) können Sie das Zertifizierungsstellen-Stammzertifikat von einem beliebigen, mit der Domäne verbundenen Computer exportieren.</span><span class="sxs-lookup"><span data-stu-id="a51d7-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="a51d7-142">Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann **MMC**ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="a51d7-143">Klicken Sie in der MMC-Konsole auf **Datei**, klicken Sie auf **hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="a51d7-144">Wählen Sie in der Dialogliste **Snap-Ins hinzufügen oder entfernen** die Option **Zertifikate**aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="a51d7-145">Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="a51d7-146">Wählen Sie im Dialogfeld **Computer auswählen** die Option **lokaler Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="a51d7-147">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-147">Click **Finish**.</span></span> <span data-ttu-id="a51d7-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-148">Click **OK**.</span></span>

4.  <span data-ttu-id="a51d7-149">Erweitern Sie **Zertifikate (lokaler Computer)**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="a51d7-150">Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und wählen Sie **Zertifikate**aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="a51d7-151">Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat.</span><span class="sxs-lookup"><span data-stu-id="a51d7-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="a51d7-152">Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie **alle Aufgaben**, und wählen Sie **exportieren**aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="a51d7-153">Der **Zertifikat Export-Assistent** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a51d7-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="a51d7-154">Klicken Sie im **Zertifikat Export-Assistenten**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="a51d7-155">Wählen Sie im Dialogfeld **Dateiformat exportieren** ein Format aus, in das exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a51d7-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="a51d7-156">Wir empfehlen die **Syntax Standard für kryptografische Nachrichten \#– PKCS 7-Zertifikate (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="a51d7-157">Wenn Sie die **Syntax Standard für kryptografische Nachrichten auswählen \#– PKCS 7-Zertifikate (. P7B)**, aktivieren Sie das Kontrollkästchen **alle Zertifikate in den Zertifizierungspfad einbeziehen, wenn möglich** , um die Zertifikatkette zu exportieren, einschließlich des Zertifikats der Stammzertifizierungsstelle und aller Zwischenzertifizierungsstellen Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a51d7-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="a51d7-158">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-158">Click **Next**.</span></span>

8.  <span data-ttu-id="a51d7-159">Geben Sie im Dialogfeld **Datei zum Exportieren** in den Dateinamen Eintrag einen Pfad und Dateinamen (die Standarderweiterung ist P7B) für das exportierte Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="a51d7-160">Klicken Sie optional auf **Durchsuchen**, suchen Sie ein Verzeichnis, in dem das exportierte Zertifikat platziert werden soll, und geben Sie einen Namen für das exportierte Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="a51d7-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="a51d7-161">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-161">Click **Save**.</span></span> <span data-ttu-id="a51d7-162">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-162">Click **Next**.</span></span>

9.  <span data-ttu-id="a51d7-163">Überprüfen Sie die Zusammenfassung der Aktionen, und klicken Sie auf **Fertig stellen** , um den Export des Zertifikats abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="a51d7-164">Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="a51d7-165">So importieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a51d7-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="a51d7-166">Öffnen Sie auf jedem Edgeserver die Microsoft Management Console (MMC), indem Sie auf **Start**klicken, auf **Ausführen**klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="a51d7-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="a51d7-167">Klicken Sie im Menü **Datei** auf **Snap-in hinzufügen/entfernen**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="a51d7-168">Klicken Sie im Feld **eigenständige Snap-Ins hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="a51d7-169">Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a51d7-170">Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="a51d7-171">Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="a51d7-172">Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen**, zeigen Sie auf **alle Aufgaben**, und klicken Sie dann auf **importieren**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="a51d7-173">Geben Sie im Assistenten in **zu importierende Datei**den Dateinamen des Zertifikats an (also den Namen, den Sie beim Herunterladen der Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle im vorherigen Verfahren angegeben haben).</span><span class="sxs-lookup"><span data-stu-id="a51d7-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="a51d7-174">Wiederholen Sie diesen Vorgang auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a51d7-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="a51d7-175">So erstellen Sie die Zertifikatanforderung für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a51d7-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="a51d7-176">Starten Sie auf einem der Edgeserver den Bereitstellungs-Assistenten, und klicken Sie neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51d7-177">Wenn Sie über mehrere Edgeserver an einem Speicherort in einem Pool verfügen, können Sie den Zertifikat-Assistenten auf einem beliebigen Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="a51d7-178">Nachdem Sie Schritt 3 beim ersten Mal ausgeführt haben, wird die Schaltfläche <STRONG>erneut ausgeführt</STRONG>, und ein grünes Häkchen, das den erfolgreichen Abschluss des Vorgangs angibt, wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="a51d7-179">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="a51d7-180">Klicken Sie auf der Seite **Zertifikatanforderung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="a51d7-181">Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="a51d7-182">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen ein, zu dem die Anforderung gespeichert werden soll (beispielsweise **c:\\CERT\_Internal\_Edge. CER**).</span><span class="sxs-lookup"><span data-stu-id="a51d7-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="a51d7-183">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="a51d7-184">Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a51d7-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="a51d7-185">Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein (beispielsweise interner Rand).</span><span class="sxs-lookup"><span data-stu-id="a51d7-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="a51d7-186">Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von **2048**) an.</span><span class="sxs-lookup"><span data-stu-id="a51d7-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a51d7-187">Höhere Bit-Längen bieten mehr Sicherheit, wirken sich aber negativ auf die Geschwindigkeit aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="a51d7-188">Wenn das Zertifikat exportierbar sein muss, aktivieren Sie das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** .</span><span class="sxs-lookup"><span data-stu-id="a51d7-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="a51d7-189">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit (z. b. eine Abteilung oder Abteilung) ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="a51d7-190">Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.</span><span class="sxs-lookup"><span data-stu-id="a51d7-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="a51d7-191">Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="a51d7-192">Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a51d7-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="a51d7-193">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="a51d7-194">Führen Sie nach Abschluss der Befehle die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a51d7-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="a51d7-195">Wenn Sie das Protokoll für die Zertifikatanforderung anzeigen möchten, klicken Sie auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="a51d7-196">Klicken Sie auf **weiter**, um die Zertifikatanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="a51d7-197">Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a51d7-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="a51d7-198">Klicken Sie zum Anzeigen der generierten CSR-Datei (Certificate Signing Request) auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="a51d7-199">Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="a51d7-200">Senden Sie diese Datei an Ihre Zertifizierungsstelle (per e-Mail oder einer anderen von Ihrer Organisation unterstützten Methode für Ihre Unternehmenszertifizierungsstelle), und kopieren Sie das neue Zertifikat, wenn Sie die Antwortdatei erhalten, auf diesen Computer, damit es für den Import verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a51d7-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="a51d7-201">So importieren Sie das Zertifikat für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a51d7-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="a51d7-202">Melden Sie sich bei dem Edgeserver an, auf dem Sie die Zertifikatanforderung als Mitglied der lokalen Gruppe Administratoren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a51d7-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="a51d7-203">Klicken Sie im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="a51d7-204">Nachdem Sie Schritt 3 beim ersten Mal ausgeführt haben, wird die Schaltfläche **erneut in ausführen**geändert, aber ein grünes Häkchen (das den erfolgreichen Abschluss des Vorgangs angibt) wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="a51d7-205">Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **Zertifikat aus a importieren. P7B, PFX-oder CER-Datei**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="a51d7-206">Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und den Dateinamen des Zertifikats ein, das Sie für die interne Schnittstelle dieses Edgeserver angefordert und empfangen haben (oder klicken Sie auf **Durchsuchen** , um die Datei zu suchen und auszuwählen).</span><span class="sxs-lookup"><span data-stu-id="a51d7-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="a51d7-207">Wenn Sie Zertifikate für andere Mitglieder des Pools ein Zertifikat mit einem privaten Schlüssel importieren, aktivieren Sie das Kontrollkästchen **Zertifikatsdatei enthält den privaten Schlüsselzertifikat** , und geben Sie das Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="a51d7-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="a51d7-208">So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool</span><span class="sxs-lookup"><span data-stu-id="a51d7-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="a51d7-209">Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie das Zertifikat importiert haben.</span><span class="sxs-lookup"><span data-stu-id="a51d7-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="a51d7-210">Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie **MMC**ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="a51d7-211">Klicken Sie in der MMC-Konsole auf **Datei**, und klicken Sie auf **Snap-in hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="a51d7-212">Klicken Sie auf der Seite Snap-Ins hinzufügen oder entfernen auf **Zertifikate**, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="a51d7-213">Wählen Sie im Dialogfeld Zertifikate-Snap-in die Option **Computer Konto**aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="a51d7-214">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-214">Click **Next**.</span></span> <span data-ttu-id="a51d7-215">Wählen Sie unter Computer auswählen **die Option Lokaler Computer aus: (der Computer, auf dem diese Konsole ausgeführt wird)**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="a51d7-216">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-216">Click **Finish**.</span></span> <span data-ttu-id="a51d7-217">Klicken Sie auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="a51d7-218">Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a51d7-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="a51d7-219">Doppelklicken Sie auf **persönlich**, und doppelklicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a51d7-220">Wenn im persönlichen Zertifikatspeicher für den lokalen Computer keine Zertifikate vorhanden sind, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a51d7-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="a51d7-221">Überprüfen Sie die Schritte zum Anfordern und importieren.</span><span class="sxs-lookup"><span data-stu-id="a51d7-221">Review the request and import steps.</span></span> <span data-ttu-id="a51d7-222">Wenn das Problem weiterhin besteht, wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="a51d7-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="a51d7-223">Klicken Sie im persönlichen Zertifikatspeicher des lokalen Computers mit der rechten Maustaste auf das Zertifikat, das Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a51d7-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="a51d7-224">Klicken Sie auf **alle Aufgaben**, und klicken Sie auf **exportieren**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="a51d7-225">Klicken Sie im Zertifikat Export-Assistenten auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="a51d7-226">Wählen Sie **Ja aus, exportieren Sie den privaten Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="a51d7-227">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a51d7-228">Wenn die Auswahl <STRONG>Ja, privater Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der dem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert.</span><span class="sxs-lookup"><span data-stu-id="a51d7-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="a51d7-229">Sie müssen das Zertifikat erneut anfordern, um sicherzustellen, dass das Zertifikat markiert ist, damit der Export des privaten Schlüssels zugelassen wird, bevor Sie den Export fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="a51d7-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="a51d7-230">Wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="a51d7-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="a51d7-231">Wählen Sie im Dialogfeld Dateiformate exportieren den Eintrag **Personal Information Exchange\#– PKCS 12 (. PFX)** , und wählen Sie dann die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a51d7-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="a51d7-232">Nach Möglichkeit alle Zertifikate in den Zertifizierungspfad einbeziehen</span><span class="sxs-lookup"><span data-stu-id="a51d7-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="a51d7-233">Exportieren aller erweiterten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a51d7-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="a51d7-234">Wenn Sie das Zertifikat von einem Edgeserver exportieren, wählen Sie <STRONG>den privaten Schlüssel nicht löschen aus, wenn der Export erfolgreich ist</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a51d7-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="a51d7-235">Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.</span><span class="sxs-lookup"><span data-stu-id="a51d7-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="a51d7-236">Klicken Sie auf **Weiter**, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="a51d7-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="a51d7-237">Wenn Sie zum Schützen des privaten Schlüssels ein Kennwort zuweisen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="a51d7-238">Geben Sie das Kennwort zur Bestätigung erneut ein.</span><span class="sxs-lookup"><span data-stu-id="a51d7-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="a51d7-239">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-239">Click **Next**.</span></span>

11. <span data-ttu-id="a51d7-240">Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung .pfx verwenden.</span><span class="sxs-lookup"><span data-stu-id="a51d7-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="a51d7-241">Der Pfad muss entweder für alle anderen Edgeserver im Pool zugänglich sein oder über Wechselmedien zur Verfügung stehen, beispielsweise einen USB-Speicherstick.</span><span class="sxs-lookup"><span data-stu-id="a51d7-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="a51d7-242">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-242">Click **Next**.</span></span>

12. <span data-ttu-id="a51d7-243">Überprüfen Sie die Zusammenfassung im Dialogfeld zum Abschließen des Zertifikat Export-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="a51d7-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="a51d7-244">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-244">Click **Finish**.</span></span>

13. <span data-ttu-id="a51d7-245">Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="a51d7-246">Importieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und führen Sie die Schritte aus, die in den Verfahren zum [Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="a51d7-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="a51d7-247">So weisen Sie das interne Zertifikat auf den Edgeserver zu</span><span class="sxs-lookup"><span data-stu-id="a51d7-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="a51d7-248">Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="a51d7-249">Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **vorhandenes Zertifikat zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="a51d7-250">Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Interner Edgeserver** aus.</span><span class="sxs-lookup"><span data-stu-id="a51d7-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="a51d7-251">Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie für den internen Edge importiert haben (aus dem vorherigen Verfahren).</span><span class="sxs-lookup"><span data-stu-id="a51d7-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="a51d7-252">Überprüfen Sie auf der Seite **Certificate Assignment Summary** Ihre Einstellungen, und klicken Sie dann auf **weiter** , um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a51d7-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="a51d7-253">Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a51d7-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="a51d7-254">Nachdem Sie dieses Verfahren zum Zuweisen des internen Edge-Zertifikats verwendet haben, öffnen Sie das Zertifikat-Snap-in auf jedem Server, erweitern Sie **Zertifikate (lokaler Computer)**, erweitern Sie **Personal**, klicken Sie auf **Zertifikate**, und überprüfen Sie im Detailbereich, ob das Zertifikat für das interne Edge aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a51d7-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="a51d7-255">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie diesen Vorgang für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="a51d7-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

