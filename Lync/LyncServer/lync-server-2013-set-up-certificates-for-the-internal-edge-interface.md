---
title: 'Lync Server 2013: Einrichten von Zertifikaten für die interne Edge-Schnittstelle'
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
ms.openlocfilehash: b1e43527c188b95863f2285c1adf4107ea53ebed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="f7a55-102">Einrichten von Zertifikaten für die interne Edge-Schnittstelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7a55-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a55-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f7a55-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f7a55-104">Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den zu verwendeten Zertifikatvorlagentyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="f7a55-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="f7a55-105">Standardmäßig wird für eine lync Server 2013 Zertifikatanforderung die Webserverzertifikatvorlage verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7a55-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="f7a55-106">Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="f7a55-p102">Ein einzelnes Zertifikat ist für die interne Schnittstelle jedes Edgeservers erforderlich. Die Zertifikate für die interne Schnittstelle können von einer internen Unternehmenszertifizierungsstelle oder von einer öffentlichen Zertifizierungsstelle ausgestellt werden. Wenn Ihre Organisation eine interne Zertifizierungsstelle bereitstellt, können Sie die Ausgaben für die Verwendung öffentlicher Zertifikate einsparen, indem Sie das Zertifikat für die interne Schnittstelle von der internen Zertifizierungsstelle ausstellen lassen. Zum Erstellen dieser Zertifikate können Sie eine interne Windows Server 2008- oder Windows Server 2008 R2-Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="f7a55-111">Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f7a55-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="f7a55-112">Führen Sie die Schritte in diesem Abschnitt aus, um Zertifikate für die interne Edgeschnittstelle an einem Standort einzurichten:</span><span class="sxs-lookup"><span data-stu-id="f7a55-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="f7a55-113">Laden Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle auf die einzelnen Edgeserver herunter.</span><span class="sxs-lookup"><span data-stu-id="f7a55-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="f7a55-114">Importieren Sie die Zertifikatskette der Zertifizierungsstelle auf den einzelnen Edgeservern für die interne Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f7a55-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="f7a55-115">Erstellen Sie die Zertifikatanforderung für die interne Schnittstelle auf einem Edgeserver, der dann als erster Edgeserver bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f7a55-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="f7a55-116">Importieren Sie das Zertifikat für die interne Schnittstelle auf dem ersten Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="f7a55-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="f7a55-117">Importieren Sie das Zertifikat auf den anderen Edgeservern an diesem Standort (bzw. auf Edgeservern, die hinter diesem Hardwaregerät zum Lastenausgleich bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="f7a55-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="f7a55-118">Weisen Sie das Zertifikat für die interne Schnittstelle jedes Edgeservers zu.</span><span class="sxs-lookup"><span data-stu-id="f7a55-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="f7a55-119">Falls Sie über mehrere Standorte mit Edgeservern verfügen (also über eine Edgetopologie mit mehreren Standorten) oder falls Sie separate Gruppen von Edgeservern hinter verschiedenen Hardwaregeräten zum Lastenausgleich bereitstellen, müssen Sie diese Schritte für jeden Standort, der über Edgeserver verfügt, sowie für jede Gruppe von Edgeservern, die hinter einem Hardwaregerät zum Lastenausgleich bereitgestellt wird, separat ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7a55-120">Die Schritte in diesem Abschnitt basieren auf der Verwendung einer Windows Server&nbsp;2008-Zertifizierungsstelle, einer&nbsp;Windows&nbsp;Server 2008 R2-Zertifizierungsstelle, Windows Server 2012 ca oder Windows Server 2012 R2-Zertifizierungsstelle, um ein Zertifikat für jede Edgeserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="f7a55-121">Eine Schritt-für-Schritt-Anleitung für andere Zertifizierungsstellen finden Sie in der Dokumentation für die jeweilige Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f7a55-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="f7a55-122">Standardmäßig besitzen alle authentifizierten Benutzer die entsprechenden Benutzerrechte zum Anfordern von Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="f7a55-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="f7a55-p104">Die Verfahren in diesem Abschnitt basieren auf der Erstellung von Zertifikatanforderungen auf dem Edgeserver im Rahmen des Edgeserver-Bereitstellungsprozesses. Zertifikatanforderungen können mithilfe des Front-End-Servers erstellt werden. Dies ist möglich, um die Zertifikatanforderung zu einem frühen Zeitpunkt im Planungs- und Bereitstellungsprozess vor der Bereitstellung der Edgeserver abzuschließen. Hierzu müssen Sie sicherstellen, dass das angeforderte Zertifikat mit einem exportierbaren privaten Schlüssel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="f7a55-p105">Die Verfahren in diesem Abschnitt beschreiben die Verwendung einer CER- und einer P7B-Datei für das Zertifikat. Wenn Sie einen anderen Dateityp verwenden, ändern Sie diese Verfahren entsprechend ab.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="f7a55-129">So laden Sie mithilfe der certsv-Website eine Zertifizierungskette der Zertifizierungstelle für die interne Schnittestelle herunter</span><span class="sxs-lookup"><span data-stu-id="f7a55-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="f7a55-130">Melden Sie sich bei einem lync Server 2013 Server im internen Netzwerk (nicht im Edgeserver) als Mitglied der Gruppe **Administratoren** an.</span><span class="sxs-lookup"><span data-stu-id="f7a55-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="f7a55-131">Führen Sie an einer Eingabeaufforderung den folgenden Befehl aus, indem Sie auf **Start** und dann auf **Ausführen** klicken und Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="f7a55-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="f7a55-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f7a55-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a55-133">Wenn Sie eine Windows Server 2008- oder Windows Server 2008 R2-Unternehmenszertifizierungsstelle verwenden, müssen Sie "https" anstelle von "http" einsetzen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="f7a55-134">Klicken Sie auf der CertSrv-Webseite der ausstellenden Zertifizierungsstelle unter **Aufgabe auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="f7a55-135">Klicken Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste** auf **Download der Zertifizierungsstellen-Zertifikatkette**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="f7a55-136">Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="f7a55-137">Speichern Sie die P7B-Datei auf der Festplatte auf dem Server, und kopieren Sie die Datei dann in einen Ordner auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="f7a55-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a55-p106">Die P7B-Datei enthält alle Zertifikate, die sich unter dem Zertifizierungspfad befinden. Zum Anzeigen des Zertifizierungspfads öffnen Sie das Serverzertifikat, und klicken Sie auf den Zertifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="f7a55-140">So exportieren Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle mit der MMC</span><span class="sxs-lookup"><span data-stu-id="f7a55-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="f7a55-141">Sie können das Stammzertifikat der Zertifizierungsstelle von einem beliebigen Computer mit der Microsoft Management Console (MMC) aus einem beliebigen Domänenbeitritt exportieren.</span><span class="sxs-lookup"><span data-stu-id="f7a55-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="f7a55-142">Klicken Sie auf **Start** und dann auf **Ausführen**, und geben Sie dann **MMC** ein.</span><span class="sxs-lookup"><span data-stu-id="f7a55-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="f7a55-143">Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Hinzufügen/Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="f7a55-p108">Wählen Sie in der Dialogfeldliste **Snap-Ins hinzufügen bzw. entfernen** den Eintrag **Zertifikate** aus, und klicken Sie dann auf **Hinzufügen**. Wählen Sie bei entsprechender Eingabeaufforderung **Computerkonto** aus. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer** aus. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="f7a55-p109">Erweitern Sie **Zertifikate (Lokaler Computer)**. Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und wählen Sie **Zertifikate** aus.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="f7a55-p110">Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie **Alle Aufgaben** aus, und wählen Sie dann **Exportieren** aus. Daraufhin wird der **Zertifikatexport-Assistent** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="f7a55-154">Klicken Sie im **Zertifikatexport-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="f7a55-155">Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** ein Format für den Export aus.</span><span class="sxs-lookup"><span data-stu-id="f7a55-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="f7a55-156">Wir empfehlen die **Syntax Standard für kryptografische Nachrichten \#– PKCS 7-Zertifikate (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="f7a55-157">Wenn Sie die **Syntax Standard für kryptografische Nachrichten auswählen \#– PKCS 7-Zertifikate (. P7B)**, aktivieren Sie das Kontrollkästchen **alle Zertifikate im Zertifizierungspfad einschließen** , um die Zertifikatkette einschließlich Zertifikat der Stammzertifizierungsstelle und aller Zwischenzertifizierungsstellen Zertifikate zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="f7a55-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="f7a55-158">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-158">Click **Next**.</span></span>

8.  <span data-ttu-id="f7a55-p112">Geben Sie im Dialogfeld **Zu exportierende Datei** im Eingabefeld für den Dateinamen einen Pfad und Dateinamen (die Standarderweiterung lautet ".p7b") für das exportierte Zertifikat ein. Optional können Sie auf **Durchsuchen** klicken, ein Verzeichnis zum Speichern des exportierten Zertifikats suchen und einen Namen für das exportierte Zertifikat angeben. Klicken Sie auf **Speichern**. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="f7a55-p113">Überprüfen Sie die Zusammenfassung der Aktionen, und klicken Sie auf **Fertig stellen**, um den Zertifikatexport abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="f7a55-165">So importieren Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7a55-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="f7a55-166">Öffnen Sie auf jedem Edgeserver die MMC (Microsoft Management Console), indem Sie auf **Start** und dann auf **Ausführen** klicken, im Feld **Öffnen** den Befehl **mmc** eingeben und dann auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="f7a55-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="f7a55-167">Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="f7a55-168">Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="f7a55-169">Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="f7a55-170">Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **Lokalen Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="f7a55-171">Klicken Sie auf **Schließen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="f7a55-172">Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen** zeigen Sie auf **Alle Aufgaben**, und klicken Sie anschließend auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="f7a55-173">Geben Sie im Assistenten unter **Zu importierende Datei** den Dateinamen des Zertifikats ein (also den Namen, den Sie im vorherigen Verfahren beim Herunterladen der Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle angegeben haben).</span><span class="sxs-lookup"><span data-stu-id="f7a55-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="f7a55-174">Wiederholen Sie dieses Verfahren für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="f7a55-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="f7a55-175">So erstellen Sie die Zertifikatanforderung für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7a55-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="f7a55-176">Starten Sie auf einem der Edgeserver den Bereitstellungs-Assistenten, und klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a55-177">Wenn Sie in einem Pool über mehrere Edgeserver an einem Standort verfügen, können Sie den Zertifikat-Assistenten auf jedem dieser Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="f7a55-178">Nachdem Sie Schritt 3 erstmals ausgeführt haben, ändert sich die Schaltfläche in <STRONG>Erneut ausführen</STRONG>, und ein grünes Häkchen, das auf den erfolgreichen Abschluss der Aufgabe hinweist, wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="f7a55-179">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="f7a55-180">Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="f7a55-181">Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="f7a55-182">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Namen der Datei ein, in die die Anforderung gespeichert werden soll (beispielsweise **c:\\CERT\_Internal\_Edge. CER**).</span><span class="sxs-lookup"><span data-stu-id="f7a55-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="f7a55-183">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="f7a55-184">Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f7a55-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="f7a55-185">Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein (Beispiel: Interner Edge).</span><span class="sxs-lookup"><span data-stu-id="f7a55-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="f7a55-186">Geben Sie in **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert **2048** verwendet).</span><span class="sxs-lookup"><span data-stu-id="f7a55-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f7a55-187">Höhere Bitlängen bieten mehr Sicherheit, beeinträchtigen jedoch die Geschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="f7a55-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="f7a55-188">Wenn das Zertifikat exportierbar sein muss, aktivieren Sie das Kontrollkästchen **Privaten Schlüssel des Zertifikats als "Exportierbar" markieren**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="f7a55-189">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="f7a55-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="f7a55-190">Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="f7a55-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="f7a55-191">Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="f7a55-192">Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="f7a55-193">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="f7a55-194">Nachdem die Befehle ausgeführt wurden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f7a55-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="f7a55-195">Zum Anzeigen des Protokolls für die Zertifikatanforderung klicken Sie auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="f7a55-196">Klicken Sie auf **Weiter**, um die Zertifikatanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="f7a55-197">Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f7a55-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="f7a55-198">Zum Anzeigen der generierten CSR-Datei (Certificate Signing Request, Zertifikatsignieranforderung) klicken Sie auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="f7a55-199">Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="f7a55-200">Senden Sie diese Datei an die Zertifizierungsstelle (per E-Mail oder mit einer anderen von Ihrer Organisation für die Zertifizierungsstelle des Unternehmens unterstützten Methode), und kopieren Sie, nachdem Sie die Antwortdatei erhalten haben, das neue Zertifikat auf diesen Computer, sodass es für einen Import zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f7a55-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="f7a55-201">So importieren Sie das Zertifikat für die interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7a55-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="f7a55-202">Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f7a55-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="f7a55-203">Klicken Sie im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="f7a55-204">Nachdem Sie Schritt 3 erstmals ausgeführt haben, ändert sich die Schaltfläche in **Erneut ausführen**. Ein grünes Häkchen, das auf den erfolgreichen Abschluss der Aufgabe hinweist, wird jedoch erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="f7a55-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="f7a55-205">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="f7a55-206">Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie für die interne Schnittstelle des Edgeservers angefordert und erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen).</span><span class="sxs-lookup"><span data-stu-id="f7a55-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="f7a55-207">Wenn Sie Zertifikate für andere Mitglieder des Pools importieren und ein Zertifikat einen privaten Schlüssel enthält, aktivieren Sie das Kontrollkästchen **Zertifikatdatei enthält den privaten Schlüssel des Zertifikats**, und geben Sie das Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="f7a55-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="f7a55-208">So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool</span><span class="sxs-lookup"><span data-stu-id="f7a55-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="f7a55-209">Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie das Zertifikat importiert haben.</span><span class="sxs-lookup"><span data-stu-id="f7a55-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="f7a55-210">Klicken Sie auf **Start**, dann auf **Ausführen**, und geben Sie **MMC** ein.</span><span class="sxs-lookup"><span data-stu-id="f7a55-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="f7a55-211">Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="f7a55-212">Klicken Sie auf der Seite Snap-Ins hinzufügen oder entfernen auf **Zertifikate**und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="f7a55-213">Wählen Sie im Dialogfeld Zertifikat-Snap-in die Option **Computer Konto**aus.</span><span class="sxs-lookup"><span data-stu-id="f7a55-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="f7a55-214">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-214">Click **Next**.</span></span> <span data-ttu-id="f7a55-215">Wählen Sie unter Computer auswählen **die Option Lokaler Computer: (Computer, auf dem diese Konsole läuft)** aus.</span><span class="sxs-lookup"><span data-stu-id="f7a55-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="f7a55-216">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-216">Click **Finish**.</span></span> <span data-ttu-id="f7a55-217">Klicken Sie auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="f7a55-p115">Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **Eigene Zertifikate**, und doppelklicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f7a55-p116">Wenn sich im Speicher Eigene Zertifikate für den lokalen Computer keine Zertifikate befinden, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Anforderungs- und Importschritte. Besteht das Problem weiterhin, wenden Sie sich an den Administrator oder Anbieter für die Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="f7a55-p117">Klicken Sie im Speicher Eigene Zertifikate für den lokalen Computer mit der rechten Maustaste auf das zu exportierende Zertifikat. Klicken Sie auf **Alle Aufgaben** und dann auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="f7a55-p118">Klicken Sie im Zertifikatexport-Assistenten auf **Weiter**. Wählen Sie **Ja, privaten Schlüssel exportieren** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a55-p119">Ist die Option <STRONG>Ja, privaten Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der diesem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert. Si müssen das Zertifikat erneut anfordern. Dabei müssen Sie sicherstellen, dass das Zertifikat für den Export des privaten Schlüssels markiert ist, bevor Sie den Export fortsetzen können. Wenden Sie sich ggf. an den Administrator oder Anbieter für die Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="f7a55-231">Wählen Sie im Dialogfeld Dateiformate exportieren die Option **Personal Information Exchange\#– PKCS 12 (aus. PFX)** , und wählen Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="f7a55-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="f7a55-232">Wenn möglich, alle Zertifikate im Zertifizierungspfad einbeziehen</span><span class="sxs-lookup"><span data-stu-id="f7a55-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="f7a55-233">Alle erweiterten Eigenschaften exportieren</span><span class="sxs-lookup"><span data-stu-id="f7a55-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="f7a55-p120">Wählen Sie beim Exportieren des Zertifikats von einem Edgeserver nicht die Option <STRONG>Privaten Schlüssel nach erfolgreichem Export löschen</STRONG> aus. Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="f7a55-236">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="f7a55-p121">Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="f7a55-p122">Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung PFX verwenden. Für den Pfad gilt, dass entweder alle anderen Edgeserver in dem Pool darauf zugreifen können müssen, oder dass er für den Transport mittels Wechseldatenträger, z. B. USB-Stick, verfügbar ist. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="f7a55-243">Lesen Sie die Zusammenfassung im Dialogfeld abschließen des Assistenten für den Zertifikat Export.</span><span class="sxs-lookup"><span data-stu-id="f7a55-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="f7a55-244">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-244">Click **Finish**.</span></span>

13. <span data-ttu-id="f7a55-245">Klicken Sie im Dialogfeld Export erfolgreich auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="f7a55-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="f7a55-246">Importieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, und führen Sie die Schritte aus, die in der [Benutzeroberfläche zum Einrichten von Zertifikaten für die externe edgedatei für lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) Verfahren beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="f7a55-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="f7a55-247">So weisen Sie das interne Zertifikat auf den Edgeservern zu</span><span class="sxs-lookup"><span data-stu-id="f7a55-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="f7a55-248">Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="f7a55-249">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="f7a55-250">Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Edge intern** aus.</span><span class="sxs-lookup"><span data-stu-id="f7a55-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="f7a55-251">Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie (im vorherigen Verfahren) für den internen Edge importiert haben.</span><span class="sxs-lookup"><span data-stu-id="f7a55-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="f7a55-252">Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen, und klicken Sie dann auf **Weiter**, um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7a55-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="f7a55-253">Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f7a55-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="f7a55-254">Nachdem Sie das interne Edgezertifikat über diese Schritte zugewiesen haben, öffnen Sie auf jedem Server das Zertifikat-Snap-In, erweitern Sie den Eintrag **Zertifikate (Lokaler Computer)** sowie den Eintrag **Eigene Zertifikate**, und klicken Sie auf **Zertifikate**. Überprüfen Sie dann im Detailbereich, ob das interne Edgezertifikat aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="f7a55-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="f7a55-255">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie dieses Verfahren für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="f7a55-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

