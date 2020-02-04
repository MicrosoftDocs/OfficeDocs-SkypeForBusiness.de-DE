---
title: 'Lync Server 2013: Einrichten der Zertifikate für die externe Edgeschnittstelle'
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
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="69dd2-102">Einrichten der Zertifikate für die externe Edgeschnittstelle für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69dd2-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69dd2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="69dd2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="69dd2-104">Wenn Sie den Zertifikat-Assistenten ausführen, stellen Sie sicher, dass Sie mit einem Konto angemeldet sind, das Mitglied einer Gruppe ist, der die entsprechenden Berechtigungen für den Typ der Zertifikatvorlage zugewiesen wurden, die Sie verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="69dd2-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="69dd2-105">Standardmäßig wird für eine lync Server-Zertifikatanforderung die Vorlage Webserverzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="69dd2-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="69dd2-106">Wenn Sie ein Konto verwenden, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat mithilfe dieser Vorlage anzufordern, stellen Sie sicher, dass der Gruppe die für die Verwendung dieser Vorlage erforderlichen Registrierungsberechtigungen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="69dd2-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="69dd2-107">Jeder Edgeserver erfordert ein öffentliches Zertifikat auf der Schnittstelle zwischen dem Umkreisnetzwerk und dem Internet, und der Alternative Name des Zertifikats muss die externen Namen des Access Edge-Diensts und des Webkonferenz-Edgedienst vollständig enthalten qualifizierte Domänennamen (FQDNs).</span><span class="sxs-lookup"><span data-stu-id="69dd2-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="69dd2-108">Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="69dd2-109">Eine Liste der öffentlichen Zertifizierungsstellen, die Zertifikate bereitstellen, die bestimmte Anforderungen für Unified Communications-Zertifikate erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem lync Server 2013-Zertifikat-Assistenten funktionieren, finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Microsoft Knowledge Base-Artikel 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server" unter.</span><span class="sxs-lookup"><span data-stu-id="69dd2-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="69dd2-110">Konfigurieren von Zertifikaten für die externen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="69dd2-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="69dd2-111">Gehen Sie wie folgt vor, um ein Zertifikat für die externe Edge-Schnittstelle an einer Website einzurichten:</span><span class="sxs-lookup"><span data-stu-id="69dd2-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="69dd2-112">Erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edge-Servers.</span><span class="sxs-lookup"><span data-stu-id="69dd2-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="69dd2-113">Senden Sie die Anfrage an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="69dd2-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="69dd2-114">Importieren Sie das Zertifikat für die externe Schnittstelle jedes Edge-Servers.</span><span class="sxs-lookup"><span data-stu-id="69dd2-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="69dd2-115">Weisen Sie das Zertifikat für die externe Schnittstelle jedes Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="69dd2-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="69dd2-116">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, exportieren Sie das Zertifikat zusammen mit seinem privaten Schlüssel, und kopieren Sie es auf die anderen Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="69dd2-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="69dd2-117">Importieren Sie die Datei für jeden Edgeserver, und weisen Sie Sie wie zuvor beschrieben zu.</span><span class="sxs-lookup"><span data-stu-id="69dd2-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="69dd2-118">Wiederholen Sie diesen Vorgang für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="69dd2-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="69dd2-119">Sie können öffentliche Zertifikate direkt von einer öffentlichen Zertifizierungsstelle (etwa über die Website einer öffentlichen Zertifizierungsstelle) anfordern.</span><span class="sxs-lookup"><span data-stu-id="69dd2-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="69dd2-120">Die Verfahren in diesem Abschnitt verwenden den Zertifikat-Assistenten für die meisten Zertifikataufgaben.</span><span class="sxs-lookup"><span data-stu-id="69dd2-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="69dd2-121">Wenn Sie sich entschieden haben, ein Zertifikat direkt von einer öffentlichen Zertifizierungsstelle anzufordern, müssen Sie die einzelnen Verfahren entsprechend anpassen, um das Zertifikat anzufordern, zu transportieren und zu importieren sowie die Zertifikatkette zu importieren.</span><span class="sxs-lookup"><span data-stu-id="69dd2-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="69dd2-122">Wenn Sie ein Zertifikat von einer externen Zertifizierungsstelle anfordern, müssen die bereitgestellten Anmeldeinformationen Rechte besitzen, um ein Zertifikat von dieser Zertifizierungsstelle anzufordern.</span><span class="sxs-lookup"><span data-stu-id="69dd2-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="69dd2-123">Jede Zertifizierungsstelle verfügt über eine Sicherheitsrichtlinie, die festlegt, welche Anmeldeinformationen (also bestimmte Benutzer-und Gruppennamen) Zertifikate anfordern, ausgeben, verwalten oder lesen dürfen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="69dd2-124">Wenn Sie die Zertifikate Microsoft Management Console (MMC) zum Importieren der Zertifikatkette und des Zertifikats verwenden möchten, müssen Sie Sie in den Zertifikatspeicher für den Computer importieren.</span><span class="sxs-lookup"><span data-stu-id="69dd2-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="69dd2-125">Wenn Sie Sie in den Benutzer-oder Dienstzertifikat Speicher importieren, steht das Zertifikat im lync Server 2013-Zertifikat-Assistenten nicht für die Zuweisung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="69dd2-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="69dd2-126">So erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="69dd2-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="69dd2-127">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69dd2-128">Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen (im) mit AOL unterstützen möchte, können Sie den lync Server-Bereitstellungs-Assistenten nicht verwenden, um das Zertifikat anzufordern.</span><span class="sxs-lookup"><span data-stu-id="69dd2-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="69dd2-129">Führen Sie stattdessen die Schritte im Abschnitt "So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL" weiter unten in diesem Thema aus.</span><span class="sxs-lookup"><span data-stu-id="69dd2-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="69dd2-130">Wenn Sie über mehrere Edgeserver an einem Speicherort in einem Pool verfügen, können Sie den lync Server 2013-Zertifikat-Assistenten auf einem der Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="69dd2-131">Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="69dd2-132">Klicken Sie auf der Seite **Zertifikatanforderung** auf **externes Zertifikat**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="69dd2-133">Aktivieren Sie auf der Seite **verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, aber später senden** .</span><span class="sxs-lookup"><span data-stu-id="69dd2-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="69dd2-134">Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="69dd2-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="69dd2-135">Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69dd2-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="69dd2-136">Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="69dd2-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="69dd2-137">Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="69dd2-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="69dd2-138">Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von **2048**) an.</span><span class="sxs-lookup"><span data-stu-id="69dd2-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="69dd2-139">Überprüfen Sie, ob das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="69dd2-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="69dd2-140">Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="69dd2-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="69dd2-141">Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.</span><span class="sxs-lookup"><span data-stu-id="69dd2-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="69dd2-142">Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="69dd2-143">Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.</span><span class="sxs-lookup"><span data-stu-id="69dd2-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="69dd2-144">Aktivieren Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.</span><span class="sxs-lookup"><span data-stu-id="69dd2-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="69dd2-145">Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="69dd2-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="69dd2-146">Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="69dd2-147">Führen Sie nach Abschluss der Befehle die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="69dd2-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="69dd2-148">Wenn Sie das Protokoll für die Zertifikatanforderung anzeigen möchten, klicken Sie auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="69dd2-149">Klicken Sie auf **weiter**, um die Zertifikatanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="69dd2-150">Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="69dd2-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="69dd2-151">Klicken Sie zum Anzeigen der generierten CSR-Datei (Certificate Signing Request) auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="69dd2-152">Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="69dd2-153">Kopieren Sie die Ausgabedatei an einen Speicherort, an den Sie Sie an die öffentliche Zertifizierungsstelle übermitteln können.</span><span class="sxs-lookup"><span data-stu-id="69dd2-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="69dd2-154">So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL</span><span class="sxs-lookup"><span data-stu-id="69dd2-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="69dd2-155">Wenn die erforderliche Vorlage für die Zertifizierungsstelle verfügbar ist, verwenden Sie das folgende Windows PowerShell-Cmdlet auf dem Edgeserver, um das Zertifikat anzufordern:</span><span class="sxs-lookup"><span data-stu-id="69dd2-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="69dd2-156">Der Standardzertifikat Name der Vorlage, die in lync Server 2013 bereitgestellt wird, ist Web Server.</span><span class="sxs-lookup"><span data-stu-id="69dd2-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="69dd2-157">Geben Sie nur \<den Vorlagen\> Namen an, wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="69dd2-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69dd2-158">Wenn Ihre Organisation öffentliche Chat Verbindungen mit AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten Windows PowerShell verwenden, um das Zertifikat anzufordern, das dem externen Edge für den Access Edge-Dienst zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="69dd2-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="69dd2-159">Der Grund hierfür ist, dass die vom Zertifikat-Assistenten zum Anfordern eines Zertifikats verwendete lync Server 2013-Webservervorlage die Client-EKU-Konfiguration nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="69dd2-160">Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der CA-Administrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="69dd2-161">So senden Sie eine Anforderung an eine öffentliche Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="69dd2-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="69dd2-162">Öffnen Sie die Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="69dd2-162">Open the output file.</span></span>

2.  <span data-ttu-id="69dd2-163">Kopieren Sie den Inhalt der Certificate Signing Request (CSR), und fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="69dd2-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="69dd2-164">Wenn Sie dazu aufgefordert werden, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="69dd2-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="69dd2-165">**Microsoft** als Server Plattform.</span><span class="sxs-lookup"><span data-stu-id="69dd2-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="69dd2-166">**IIS** als Version.</span><span class="sxs-lookup"><span data-stu-id="69dd2-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="69dd2-167">**Web Server** als Verwendungstyp.</span><span class="sxs-lookup"><span data-stu-id="69dd2-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="69dd2-168">**PKCS7** als Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="69dd2-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="69dd2-169">Wenn die öffentliche Zertifizierungsstelle Ihre Informationen überprüft hat, erhalten Sie eine e-Mail-Nachricht mit Text, der für Ihr Zertifikat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="69dd2-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="69dd2-170">Kopieren Sie den Text aus der e-Mail-Nachricht, und speichern Sie den Inhalt in einer Textdatei (txt) auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="69dd2-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="69dd2-171">So importieren Sie das Zertifikat für die externe Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="69dd2-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="69dd2-172">Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="69dd2-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="69dd2-173">Klicken Sie im Bereitstellungs-Assistenten auf der Seite **Edgeserver bereitstellen** neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="69dd2-174">Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **Zertifikat aus einer P7B-, PFX-oder CER-Datei importieren**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="69dd2-175">Klicken Sie auf der Seite **Zertifikat importieren** auf **Durchsuchen** , um das Zertifikat zu suchen und auszuwählen, das Sie für die externe Schnittstelle des Edge-Servers angefordert haben (oder Sie können den vollständigen Pfad und den Dateinamen eingeben).</span><span class="sxs-lookup"><span data-stu-id="69dd2-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="69dd2-176">Wenn das Zertifikat einen privaten Schlüssel enthält, wählen Sie **Zertifikatdatei enthält den privaten** Schlüssel des Zertifikats aus, und geben Sie das Kennwort für den privaten Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="69dd2-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="69dd2-177">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-177">Click **Next**.</span></span>

5.  <span data-ttu-id="69dd2-178">Überprüfen Sie auf der Seite **Zertifikatzusammenfassung importieren** die Zusammenfassung, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="69dd2-179">Überprüfen Sie beim **Ausführen von Befehlen**die Ergebnisse des Imports, klicken Sie auf **Protokoll anzeigen** , wenn Sie weitere Informationen benötigen, und klicken Sie dann auf **Fertig stellen** , um den Zertifikatimport abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="69dd2-180">Wenn Sie einen Edge-Server-Pool konfigurieren, exportieren Sie das Zertifikat mit seinem privaten Schlüssel, wie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69dd2-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="69dd2-181">Kopieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und importieren Sie Sie in den Computerspeicher auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="69dd2-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="69dd2-182">So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool</span><span class="sxs-lookup"><span data-stu-id="69dd2-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="69dd2-183">Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie das Zertifikat importiert haben.</span><span class="sxs-lookup"><span data-stu-id="69dd2-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="69dd2-184">Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie **MMC**ein.</span><span class="sxs-lookup"><span data-stu-id="69dd2-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="69dd2-185">Klicken Sie in der MMC-Konsole (Microsoft Management Console) auf **Datei**, und klicken Sie dann auf **Snap-in hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="69dd2-186">Klicken Sie unter **Snap-Ins hinzufügen oder entfernen**auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="69dd2-187">Wählen Sie im Dialogfeld **Zertifikate** die Option **Computerkonto**aus, klicken Sie auf **weiter**, wählen Sie **lokaler Computer aus: (der Computer, auf dem diese Konsole ausgeführt wird)** klicken Sie auf Computer **auswählen**, klicken Sie auf **Fertig stellen** , und klicken Sie dann auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="69dd2-188">Doppelklicken Sie auf **Zertifikate (lokaler Computer)** , um die Zertifikatspeicher zu erweitern, doppelklicken Sie auf **persönlich**, und doppelklicken Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="69dd2-189">Wenn im persönlichen Zertifikatspeicher für den lokalen Computer keine Zertifikate vorhanden sind, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="69dd2-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="69dd2-190">Überprüfen Sie die Schritte zum Anfordern und importieren.</span><span class="sxs-lookup"><span data-stu-id="69dd2-190">Review the request and import steps.</span></span> <span data-ttu-id="69dd2-191">Wenn das Problem weiterhin besteht, wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="69dd2-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="69dd2-192">Klicken Sie im **persönlichen Zertifikatspeicher für den lokalen Computer**mit der rechten Maustaste auf das zu exportierende Zertifikat, klicken Sie auf **alle Vorgänge**, und klicken Sie dann auf **exportieren**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="69dd2-193">Klicken Sie im Zertifikat Export-Assistenten auf **weiter**, wählen Sie ja aus, **exportieren Sie den privaten Schlüssel**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69dd2-194">Wenn die Auswahl <STRONG>Ja, privater Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der dem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert.</span><span class="sxs-lookup"><span data-stu-id="69dd2-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="69dd2-195">Sie müssen das Zertifikat erneut anfordern, um sicherzustellen, dass das Zertifikat markiert ist, damit der Export des privaten Schlüssels zugelassen wird, bevor Sie den Export fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="69dd2-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="69dd2-196">Wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="69dd2-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="69dd2-197">Wählen Sie im Dialogfeld Dateiformate exportieren den Eintrag **Personal Information Exchange\#– PKCS 12 (. PFX)** , und wählen Sie dann die folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="69dd2-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="69dd2-198">Nach Möglichkeit alle Zertifikate in den Zertifizierungspfad einbeziehen</span><span class="sxs-lookup"><span data-stu-id="69dd2-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="69dd2-199">Exportieren aller erweiterten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="69dd2-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="69dd2-200">Wenn Sie das Zertifikat von einem Edgeserver exportieren, wählen Sie <STRONG>den privaten Schlüssel nicht löschen aus, wenn der Export erfolgreich ist</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="69dd2-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="69dd2-201">Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.</span><span class="sxs-lookup"><span data-stu-id="69dd2-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="69dd2-202">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-202">Click **Next**.</span></span>

11. <span data-ttu-id="69dd2-203">Geben Sie ein Kennwort für den privaten Schlüssel ein, geben Sie das Kennwort erneut ein, um es zu bestätigen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="69dd2-204">Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung .pfx verwenden.</span><span class="sxs-lookup"><span data-stu-id="69dd2-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="69dd2-205">Der Pfad muss entweder für alle anderen Edgeserver im Pool zugänglich sein oder über Wechselmedien zur Verfügung stehen, beispielsweise einen USB-Speicherstick.</span><span class="sxs-lookup"><span data-stu-id="69dd2-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="69dd2-206">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-206">Click **Next**.</span></span>

13. <span data-ttu-id="69dd2-207">Überprüfen Sie die Zusammenfassung im **Assistenten zum Abschließen des Zertifikat Exports**, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="69dd2-208">Klicken Sie im Dialogfeld erfolgreichen Export auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="69dd2-209">Importieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und folgen Sie den Schritten unter "So importieren Sie das Zertifikat für das externe Interface des Edge-Servers" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="69dd2-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="69dd2-210">So weisen Sie das Zertifikat für die externe Schnittstelle des Edge-Servers zu</span><span class="sxs-lookup"><span data-stu-id="69dd2-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="69dd2-211">Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="69dd2-212">Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **vorhandenes Zertifikat zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="69dd2-213">Klicken Sie auf der Seite **zertifikatzuweisung** auf **externes Zertifikat** , und aktivieren Sie das Kontrollkästchen **Erweiterte Zertifikatverwendung** .</span><span class="sxs-lookup"><span data-stu-id="69dd2-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="69dd2-214">Aktivieren Sie auf der Seite **Erweiterte Zertifikatverwendung** alle Kontrollkästchen, um das Zertifikat für alle Verwendungszwecke zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="69dd2-215">Wählen Sie auf der Seite **Zertifikatspeicher** das öffentliche Zertifikat aus, das Sie für die externe Schnittstelle des Edge-Servers angefordert und importiert haben.</span><span class="sxs-lookup"><span data-stu-id="69dd2-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69dd2-216">Wenn das angeforderte und importierte Zertifikat nicht in der Liste enthalten ist, besteht eine der Problembehebungsmethoden darin, zu überprüfen, ob der Antragstellername und der Alternative Name des Zertifikats alle Anforderungen für das Zertifikat erfüllen, und wenn Sie die Datei manuell importiert haben Zertifikat-und Zertifikatkette anstelle der vorhergehenden Vorgehensweisen, dass sich das Zertifikat im richtigen Zertifikatspeicher befindet (der Computerzertifikatspeicher, nicht der Benutzer oder Dienstzertifikat Speicher).</span><span class="sxs-lookup"><span data-stu-id="69dd2-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="69dd2-217">Überprüfen Sie auf der Seite **Certificate Assignment Summary** Ihre Einstellungen, und klicken Sie dann auf **weiter** , um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="69dd2-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="69dd2-218">Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="69dd2-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="69dd2-219">Nachdem Sie dieses Verfahren zum Zuweisen des Edge-Zertifikats verwendet haben, öffnen Sie das Zertifikat-Snap-in auf jedem Server, erweitern Sie **Zertifikate (lokaler Computer)**, erweitern Sie **Personal**, klicken Sie auf **Zertifikate**, und überprüfen Sie im Detailbereich, ob das Zertifikat aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="69dd2-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="69dd2-220">Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie diesen Vorgang für jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="69dd2-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

