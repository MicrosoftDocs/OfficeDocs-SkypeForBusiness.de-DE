---
title: 'Lync Server 2013: Einrichten von Zertifikaten für die externe Edge-Schnittstelle'
description: 'Lync Server 2013: Einrichten von Zertifikaten für die Schnittstelle für externe Edges.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeca6edf0a3b50ab5dcaf9ecdbaea931d7bdf947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575411"
---
# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="2fc76-103">Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fc76-103">Set up certificates for the external edge interface for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fc76-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2fc76-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2fc76-105">Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den zu verwendeten Zertifikatvorlagentyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="2fc76-105">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="2fc76-106">Standardmäßig wird für eine lync Server Zertifikatanforderung die Webserverzertifikatvorlage verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fc76-106">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="2fc76-107">Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="2fc76-107">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="2fc76-108">Jeder Edgeserver benötigt ein öffentliches Zertifikat für die Schnittstelle zwischen dem Umkreisnetzwerk und dem Internet. Der alternative Antragstellername des Zertifikats muss die externen Namen des Zugriffs-Edgediensts und die vollqualifizierten Domänennamen des Webkonferenz-Edgediensts enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fc76-108">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="2fc76-109">Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2fc76-109">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="2fc76-110">Eine Liste der öffentlichen Zertifizierungsstellen, die Zertifikate bereitstellen, die den spezifischen Anforderungen an Unified Communications-Zertifikate entsprechen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem lync Server 2013-Zertifikat-Assistenten funktionieren, finden Sie im Microsoft Knowledge Base-Artikel 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server" unter [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="2fc76-110">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="2fc76-111">Konfigurieren von Zertifikaten für die externen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2fc76-111">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="2fc76-112">Führen Sie die Schritte in diesem Abschnitt aus, um ein Zertifikat für die externe Edgeschnittstelle an einem Standort einzurichten:</span><span class="sxs-lookup"><span data-stu-id="2fc76-112">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="2fc76-113">Erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="2fc76-113">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="2fc76-114">Senden Sie die Anforderung an die öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="2fc76-114">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="2fc76-115">Importieren Sie das Zertifikat für die externe Schnittstelle jedes Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="2fc76-115">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="2fc76-116">Weisen Sie das Zertifikat für die externe Schnittstelle jedem Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="2fc76-116">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="2fc76-p102">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, exportieren Sie das Zertifikat gemeinsam mit seinem privaten Schlüssel, und kopieren Sie es auf die anderen Edgeserver. Importieren Sie das Zertifikat anschließend für jeden Edgeserver, und weisen Sie es wie zuvor beschrieben zu. Wiederholen Sie dieses Verfahren für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="2fc76-p103">Sie können öffentliche Zertifikate direkt von einer öffentlichen Zertifizierungsstelle anfordern (z. B. über die Website einer öffentlichen Zertifizierungsstelle). Bei den Verfahren in diesem Abschnitt wird für die meisten Aufgaben im Zusammenhang mit Zertifikaten der Zertifikat-Assistent verwendet. Wenn Sie ein Zertifikat direkt von einer öffentlichen Zertifizierungsstelle anfordern, ändern Sie die einzelnen Vorgehensweisen zum Anfordern, Transportieren und Importieren des Zertifikats sowie zum Importieren der Zertifikatkette entsprechend.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="2fc76-p104">Wenn Sie ein Zertifikat von einer externen Zertifizierungsstelle anfordern, müssen die angegebenen Anmeldeinformationen mit den erforderlichen Rechten zum Anfordern eines Zertifikats von dieser Zertifizierungsstelle verknüpft sein. Jede Zertifizierungsstelle verfügt über eine Sicherheitsrichtlinie zur Definition, über welche Anmeldeinformationen (also bestimmte Benutzer- und Gruppennamen) Zertifikate angefordert, ausgestellt, verwaltet oder gelesen werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="2fc76-125">Wenn Sie die Microsoft Management Console (MMC) zum Importieren der Zertifikatkette und des Zertifikats verwenden, müssen Sie diese Elemente in den Zertifikatspeicher für den Computer importieren.</span><span class="sxs-lookup"><span data-stu-id="2fc76-125">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="2fc76-126">Wenn Sie Sie in den Benutzer-oder Dienstzertifikat Speicher importieren, steht das Zertifikat im Assistenten für lync Server 2013 Zertifikat nicht für die Zuweisung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2fc76-126">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2fc76-127">So erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edgeservers</span><span class="sxs-lookup"><span data-stu-id="2fc76-127">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2fc76-128">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-128">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2fc76-129">Wenn Ihre Organisation Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL unterstützen möchte, können Sie das Zertifikat nicht mit dem Lync Server-Bereitstellungs-Assistenten anfordern.</span><span class="sxs-lookup"><span data-stu-id="2fc76-129">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="2fc76-130">Führen Sie stattdessen das weiter unten in diesem Thema beschriebene Verfahren "So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL" aus.</span><span class="sxs-lookup"><span data-stu-id="2fc76-130">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="2fc76-131">Wenn Sie über mehrere Edgeserver an einem Standort in einem Pool verfügen, können Sie den Assistenten für lync Server 2013 Zertifikate auf einem der Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-131">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="2fc76-132">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-132">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="2fc76-133">Klicken Sie auf der Seite **Zertifikatanforderung** auf **Externes Edgezertifikat**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-133">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="2fc76-134">Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-134">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="2fc76-135">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise c: \\ Zertifikat " \_ \_ Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="2fc76-135">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="2fc76-136">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fc76-136">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="2fc76-137">Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2fc76-137">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="2fc76-138">Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="2fc76-138">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="2fc76-139">Geben Sie in **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert **2048** verwendet).</span><span class="sxs-lookup"><span data-stu-id="2fc76-139">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="2fc76-140">Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als "Exportierbar" markieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2fc76-140">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="2fc76-141">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="2fc76-141">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="2fc76-142">Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="2fc76-142">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="2fc76-p107">Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="2fc76-145">Aktivieren Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** das Kontrollkästchen Domäne, um ein SIP hinzuzufügen.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2fc76-145">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="2fc76-146">Eintrag zur Liste der alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-146">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="2fc76-147">Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2fc76-147">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="2fc76-148">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-148">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="2fc76-149">Nachdem die Befehle ausgeführt wurden, führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2fc76-149">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="2fc76-150">Zum Anzeigen des Protokolls für die Zertifikatanforderung klicken Sie auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-150">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="2fc76-151">Klicken Sie auf **Weiter**, um die Zertifikatanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-151">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="2fc76-152">Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2fc76-152">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="2fc76-153">Zum Anzeigen der generierten CSR-Datei (Certificate Signing Request, Zertifikatsignieranforderung) klicken Sie auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-153">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="2fc76-154">Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-154">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="2fc76-155">Kopieren Sie die Ausgabedatei an einen Speicherort, von dem aus Sie diese an die öffentliche Zertifizierungsstelle übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="2fc76-155">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="2fc76-156">So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten über AOL</span><span class="sxs-lookup"><span data-stu-id="2fc76-156">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="2fc76-157">Wenn die erforderliche Vorlage für die Zertifizierungsstelle verfügbar ist, verwenden Sie das folgende Windows PowerShell-Cmdlets in der Edgeserver, um das Zertifikat anzufordern:</span><span class="sxs-lookup"><span data-stu-id="2fc76-157">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="2fc76-158">Der standardmäßige Zertifikatname der in lync Server 2013 bereitgestellten Vorlage ist Webserver.</span><span class="sxs-lookup"><span data-stu-id="2fc76-158">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="2fc76-159">Geben Sie nur die an \<template name\> , wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2fc76-159">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2fc76-160">Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen mit AOL unterstützen möchte, müssen Sie Windows PowerShell anstelle des Zertifikat-Assistenten verwenden, um das Zertifikat dem externen Edge für die Zugriffs-Edgedienst zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-160">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="2fc76-161">Der Grund hierfür ist, dass die lync Server 2013-Webservervorlage, die der Zertifikat-Assistent verwendet, um ein Zertifikat anzufordern, die Client-EKU-Konfiguration nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fc76-161">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="2fc76-162">Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der Zertifizierungsstellenadministrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fc76-162">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="2fc76-163">So übermitteln Sie eine Anforderung an eine öffentliche Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="2fc76-163">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="2fc76-164">Öffnen Sie die Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="2fc76-164">Open the output file.</span></span>

2.  <span data-ttu-id="2fc76-165">Kopieren Sie den Inhalt der Signieranforderung für das Zertifikat, und fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="2fc76-165">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="2fc76-166">Geben Sie nach Aufforderung Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="2fc76-166">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="2fc76-167">**Microsoft** als Serverplattform.</span><span class="sxs-lookup"><span data-stu-id="2fc76-167">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="2fc76-168">**IIS** als Version.</span><span class="sxs-lookup"><span data-stu-id="2fc76-168">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="2fc76-169">**Web Server** als Verwendungstyp.</span><span class="sxs-lookup"><span data-stu-id="2fc76-169">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="2fc76-170">**PKCS7** als Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="2fc76-170">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="2fc76-171">Wenn die öffentliche Zertifizierungsstelle Ihre Informationen überprüft hat, erhalten Sie eine E-Mail mit dem erforderlichen Text für das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="2fc76-171">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="2fc76-172">Kopieren Sie den Text aus der E-Mail, und speichern Sie ihn in einer Textdatei (TXT-Datei) auf Ihrem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2fc76-172">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2fc76-173">So importieren Sie das Zertifikat für die externe Schnittstelle des Edgeservers</span><span class="sxs-lookup"><span data-stu-id="2fc76-173">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2fc76-174">Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2fc76-174">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="2fc76-175">Klicken Sie im Bereitstellungs-Assistenten auf der Seite **Edgeserver bereitstellen** neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-175">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="2fc76-176">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-176">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="2fc76-p111">Klicken Sie auf der Seite **Zertifikat importieren** auf **Durchsuchen**, um das Zertifikat zu finden und auszuwählen, das Sie für die externe Schnittstelle des Edgeservers angefordert haben (oder geben Sie den vollständigen Pfad und Dateinamen ein). Wenn das Zertifikat einen privaten Schlüssel enthält, aktivieren Sie das Kontrollkästchen **Zertifikatdatei enthält den privaten Schlüssel des Zertifikats**, und geben Sie das Kennwort für den privaten Schlüssel ein. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p111">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="2fc76-180">Überprüfen Sie auf der Seite **Zertifikat importieren – Zusammenfassung** die Angaben, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-180">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="2fc76-181">Überprüfen Sie auf der Seite **Befehle ausführen** die Ergebnisse des Imports, klicken Sie auf **Protokoll anzeigen**, um ggf. mehr Informationen einzublenden, und klicken Sie zum Abschließen des Zertifikatimports auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-181">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="2fc76-p112">Wenn Sie einen Edgeserverpool konfigurieren, exportieren Sie das Zertifikat mit seinem privaten Schlüssel, wie im Verfahren "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" weiter unten in diesem Thema beschrieben. Kopieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, und importieren Sie sie in den Computerspeicher auf den einzelnen Edgeservern.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p112">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="2fc76-184">So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool</span><span class="sxs-lookup"><span data-stu-id="2fc76-184">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="2fc76-185">Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie das Zertifikat importiert haben.</span><span class="sxs-lookup"><span data-stu-id="2fc76-185">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="2fc76-186">Klicken Sie auf **Start**, dann auf **Ausführen**, und geben Sie **MMC** ein.</span><span class="sxs-lookup"><span data-stu-id="2fc76-186">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="2fc76-187">Klicken Sie in der Microsoft Management Console (MMC) auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-187">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="2fc76-188">Klicken Sie in **Snap-Ins hinzufügen bzw. entfernen** auf **Zertifikate** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-188">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="2fc76-189">Wählen Sie im Dialogfeld **Zertifikate** den Eintrag **Computerkonto** aus, klicken Sie auf **Weiter**, wählen Sie unter **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aus, klicken Sie auf **Fertig stellen**, und klicken Sie dann auf **OK**, um die Konfiguration der MMC-Konsole abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-189">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="2fc76-190">Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern, doppelklicken Sie auf **Eigene Zertifikate**, und doppelklicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-190">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2fc76-p113">Wenn sich im Speicher Eigene Zertifikate für den lokalen Computer keine Zertifikate befinden, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Anforderungs- und Importschritte. Besteht das Problem weiterhin, wenden Sie sich an den Administrator oder Anbieter für die Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p113">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="2fc76-194">Klicken Sie im Speicher **Eigene Zertifikate** für den lokalen Computer mit der rechten Maustaste auf das zu exportierende Zertifikat, klicken Sie auf **Alle Aufgaben** und dann auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-194">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="2fc76-195">Klicken Sie im Zertifikatexport-Assistenten auf **Weiter**, wählen Sie **Ja, privaten Schlüssel exportieren** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-195">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2fc76-p114">Ist die Option <STRONG>Ja, privaten Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der diesem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert. Si müssen das Zertifikat erneut anfordern. Dabei müssen Sie sicherstellen, dass das Zertifikat für den Export des privaten Schlüssels markiert ist, bevor Sie den Export fortsetzen können. Wenden Sie sich ggf. an den Administrator oder Anbieter für die Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p114">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="2fc76-199">Wählen Sie im Dialogfeld Dateiformate exportieren die Option **Personal Information Exchange – PKCS \# 12 (aus. PFX)** , und wählen Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="2fc76-199">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="2fc76-200">Wenn möglich, alle Zertifikate im Zertifizierungspfad einbeziehen</span><span class="sxs-lookup"><span data-stu-id="2fc76-200">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="2fc76-201">Alle erweiterten Eigenschaften exportieren</span><span class="sxs-lookup"><span data-stu-id="2fc76-201">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="2fc76-p115">Wählen Sie beim Exportieren des Zertifikats von einem Edgeserver nicht die Option <STRONG>Privaten Schlüssel nach erfolgreichem Export löschen</STRONG> aus. Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p115">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="2fc76-204">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-204">Click **Next**.</span></span>

11. <span data-ttu-id="2fc76-205">Geben Sie ein Kennwort für den privaten Schlüssel ein, geben Sie das Kennwort zur Bestätigung erneut ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-205">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="2fc76-p116">Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung PFX verwenden. Für den Pfad gilt, dass entweder alle anderen Edgeserver in dem Pool darauf zugreifen können müssen, oder dass er für den Transport mittels Wechseldatenträger, z. B. USB-Stick, verfügbar ist. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-p116">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="2fc76-209">Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Assistenten**, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-209">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="2fc76-210">Klicken Sie im Dialogfeld erfolgreichen Export auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-210">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="2fc76-211">Importieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, indem Sie das weiter oben in diesem Thema beschriebene Verfahren "So importieren Sie das Zertifikat für die externe Schnittstelle des Edgeservers" ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-211">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2fc76-212">So weisen Sie der externen Schnittstelle des Edgeservers das Zertifikat zu</span><span class="sxs-lookup"><span data-stu-id="2fc76-212">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2fc76-213">Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-213">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="2fc76-214">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-214">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="2fc76-215">Klicken Sie auf der Seite **Zertifikatzuweisung** auf **Externes Edgezertifikat**, und aktivieren Sie das Kontrollkästchen **Erweiterte Zertifikatverwendungen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-215">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="2fc76-216">Aktivieren Sie auf der Seite **Erweiterte Zertifikatverwendungen** alle Kontrollkästchen, um das Zertifikat allen Verwendungen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-216">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="2fc76-217">Wählen Sie auf der Seite **Zertifikatspeicher** das öffentliche Zertifikat aus, das Sie für die externe Schnittstelle dieses Edgeservers angefordert und importiert haben.</span><span class="sxs-lookup"><span data-stu-id="2fc76-217">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2fc76-218">Wenn das angeforderte und importierte Zertifikat nicht in der Liste aufgeführt wird, stellen Sie sicher, dass der Antragstellername und die alternativen Antragstellernamen des Zertifikats alle Anforderungen für das Zertifikat erfüllen. Wenn Sie das Zertifikat und die Zertifikatkette nicht über die vorstehenden Verfahren, sondern manuell importiert haben, überprüfen Sie zudem, ob sich das Zertifikat im richtigen Zertifikatspeicher befindet (im Zertifikatspeicher des Computers, nicht des Benutzers oder Diensts).</span><span class="sxs-lookup"><span data-stu-id="2fc76-218">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="2fc76-219">Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen, und klicken Sie dann auf **Weiter**, um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2fc76-219">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="2fc76-220">Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2fc76-220">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="2fc76-221">Nachdem Sie das Edgezertifikat über diese Schritte zugewiesen haben, öffnen Sie auf jedem Server das Zertifikat-Snap-In, erweitern Sie den Eintrag **Zertifikate (Lokaler Computer)** sowie den Eintrag **Eigene Zertifikate**, und klicken Sie auf **Zertifikate**. Überprüfen Sie dann im Detailbereich, ob das Zertifikat aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="2fc76-221">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="2fc76-222">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie dieses Verfahren für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="2fc76-222">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

