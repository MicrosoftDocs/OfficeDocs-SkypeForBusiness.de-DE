---
title: Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy
description: Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579041"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="39b70-103">Anfordern und Konfigurieren eines Zertifikats für den Reverse-http-Proxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b70-103">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b70-104">_**Letztes Änderungsstand des Themas:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="39b70-104">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="39b70-105">Sie müssen das Zertifikat der Stammzertifizierungsstelle auf dem Server mit Microsoft Forefront Threat Management Gateway 2010 oder IIS arr für die Zertifizierungsstelleninfrastruktur installieren, die die Serverzertifikate für die internen Server mit Microsoft lync Server 2013 ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="39b70-105">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="39b70-p101">Sie müssen außerdem ein öffentliches Webserverzertifikat auf Ihrem Reverseproxyserver installieren. Die Liste der alternativen Antragstellernamen dieses Zertifikats sollte die veröffentlichten externen FQDNs für jeden Pool enthalten, in dem Benutzer verwaltet werden, die für den Remotezugriff aktiviert wurden. Außerdem muss das Zertifikat die externen FQDNs aller Directors oder Directorpools enthalten, die innerhalb dieser Edgeinfrastruktur verwendet werden. In den alternativen Antragstellernamen müssen außerdem die einfachen URLs für Besprechungen und Einwahl enthalten sein sowie – wenn Sie mobile Anwendungen bereitstellen und die Verwendung der AutoErmittlung planen – die externe AutoErmittlungsdienst-URL, wie im Folgenden gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39b70-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="39b70-109">Wert</span><span class="sxs-lookup"><span data-stu-id="39b70-109">Value</span></span></th>
<th><span data-ttu-id="39b70-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39b70-110">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39b70-111">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-111">Subject name</span></span></p></td>
<td><p><span data-ttu-id="39b70-112">Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="39b70-112">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="39b70-113">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-113">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b70-114">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-114">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-115">Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="39b70-115">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="39b70-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-116">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="39b70-117">Der Antragstellername muss ebenfalls in den alternativen Antragstellernamen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="39b70-117">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b70-118">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-118">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-119">Optionale Director-Webdienste (wenn Director bereitgestellt wird)</span><span class="sxs-lookup"><span data-stu-id="39b70-119">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="39b70-120">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-120">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b70-121">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-121">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-122">Einfache URL für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="39b70-122">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="39b70-p102">Alle einfachen URLs für Besprechungen müssen in den alternativen Antragstellernamen enthalten sein. Jede SIP-Domäne muss über mindestens eine aktive einfache URL für Besprechungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="39b70-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="39b70-125">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-125">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b70-126">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-126">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-127">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="39b70-127">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="39b70-128">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-128">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b70-129">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-129">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-130">Office Web Apps-Server</span><span class="sxs-lookup"><span data-stu-id="39b70-130">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="39b70-131">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-131">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b70-132">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="39b70-132">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="39b70-133">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="39b70-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="39b70-134">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b70-134">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="39b70-135">Wenn Sie auch Exchange Server verwenden, müssen Sie auch Reverse-Proxy Regeln für die Exchange-Auto Ermittlungs-und Webdienste-URLs konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="39b70-135">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="39b70-136">Wenn Ihre interne Bereitstellung mehr als einen Standard Edition-Server oder Front-End-Pool umfasst, müssen Sie Webveröffentlichungsregeln für jeden externen FQDN der Webfarm konfigurieren. Außerdem benötigen Sie entweder ein Zertifikat und einen Weblistener für jeden Eintrag, oder Sie müssen ein Zertifikat anfordern, dessen Liste alternativer Antragstellernamen die Namen enthält, die von allen Pools verwendet werden. Diese müssen einem Weblistener zugewiesen und in mehreren Webveröffentlichungsregeln gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39b70-136">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="39b70-137">Erstellen einer Zertifikatanforderung</span><span class="sxs-lookup"><span data-stu-id="39b70-137">Create a Certificate Request</span></span>

<span data-ttu-id="39b70-138">Sie erstellen eine Zertifikatanforderung auf dem Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="39b70-138">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="39b70-139">Sie erstellen eine Anforderung auf einem anderen Computer, aber Sie müssen das signierte Zertifikat mit dem privaten Schlüssel exportieren und auf den Reverseproxy importieren, nachdem Sie es von der öffentlichen Zertifizierungsstelle erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="39b70-139">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="39b70-140">Eine Zertifikatanforderung oder eine zertifikatsignieranforderung (CSR) ist eine Anforderung an eine vertrauenswürdige öffentliche Zertifizierungsstelle (Certification Authority, ca), um den öffentlichen Schlüssel des anfordernden Computers zu validieren und zu signieren.</span><span class="sxs-lookup"><span data-stu-id="39b70-140">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="39b70-141">Wenn ein Zertifikat generiert wird, werden ein öffentlicher Schlüssel und ein privater Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="39b70-141">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="39b70-142">Nur der öffentliche Schlüssel ist freigegeben und signiert.</span><span class="sxs-lookup"><span data-stu-id="39b70-142">Only the public key is shared and signed.</span></span> <span data-ttu-id="39b70-143">Wie der Name schon sagt, wird der öffentliche Schlüssel allen öffentlichen Anforderungen zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="39b70-143">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="39b70-144">Der öffentliche Schlüssel wird für Clients, Server und andere Requestors verwendet, die Informationen sicher austauschen und die Identität eines Computers überprüfen müssen.</span><span class="sxs-lookup"><span data-stu-id="39b70-144">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="39b70-145">Der private Schlüssel wird geschützt aufbewahrt und nur von dem Computer verwendet, der das Schlüsselpaar zum Entschlüsseln von Nachrichten erstellt hat, die mit seinem öffentlichen Schlüssel verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="39b70-145">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="39b70-146">Der private Schlüssel kann für andere Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39b70-146">The private key can be used for other purposes.</span></span> <span data-ttu-id="39b70-147">Für Reverse-Proxy-Zwecke ist die Datenverschlüsselung die primäre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="39b70-147">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="39b70-148">Sekundär ist die Zertifikatauthentifizierung auf der Zertifikatschlüssel Ebene eine weitere Verwendung und beschränkt sich nur auf die Überprüfung, dass ein Anforderer über den öffentlichen Schlüssel des Computers verfügt, oder dass es sich bei dem Computer, für den Sie einen öffentlichen Schlüssel haben, um den Computer handelt, auf den er sich beruft.</span><span class="sxs-lookup"><span data-stu-id="39b70-148">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="39b70-149">Wenn Sie Ihre Edgeserver Zertifikate und ihre Reverse-Proxy Zertifikate gleichzeitig planen, sollten Sie feststellen, dass es eine große Ähnlichkeit zwischen den beiden Zertifikatanforderungen gibt.</span><span class="sxs-lookup"><span data-stu-id="39b70-149">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="39b70-150">Wenn Sie Ihr Edgeserver Zertifikat konfigurieren und anfordern, kombinieren Sie die Edgeserver und die alternativen Alternative Namen für den Reverseproxy.</span><span class="sxs-lookup"><span data-stu-id="39b70-150">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="39b70-151">Sie können das gleiche Zertifikat für den Reverseproxy verwenden, wenn Sie das Zertifikat und den privaten Schlüssel exportieren und die exportierte Datei in den Reverseproxy kopieren und dann das Zertifikat/Schlüsselpaar importieren und nach Bedarf in den anstehenden Verfahren zuweisen.</span><span class="sxs-lookup"><span data-stu-id="39b70-151">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="39b70-152">Lesen Sie die Zertifikatanforderungen für den Edgeserver &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan für Edgeserver Zertifikate in lync Server 2013</A> und die Zusammenfassung des Reverse Proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Zertifikats-Reverseproxy in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="39b70-152">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="39b70-153">Stellen Sie sicher, dass Sie das Zertifikat mit einem exportierbaren privaten Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="39b70-153">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="39b70-154">Das Erstellen des Zertifikats und der Zertifikatanforderung mit einem exportierbaren privaten Schlüssel ist für gepoolte Edgeserver erforderlich, daher ist dies eine normale Vorgehensweise, und der Zertifikat-Assistent im lync Server-Bereitstellungs-Assistenten für die Edgeserver ermöglicht Ihnen das Festlegen des exportierbaren Kennzeichens <STRONG>privater Schlüssel</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="39b70-154">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="39b70-155">Nachdem Sie die Zertifikatanforderung von der öffentlichen Zertifizierungsstelle zurück erhalten haben, werden Sie das Zertifikat und den privaten Schlüssel exportieren.</span><span class="sxs-lookup"><span data-stu-id="39b70-155">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="39b70-156">Weitere Informationen zum Erstellen und Exportieren Ihres Zertifikats mit einem privaten Schlüssel finden Sie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" im Thema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="39b70-156">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="39b70-157">Die Erweiterung des Zertifikats sollte vom Typ <STRONG>. pfx</STRONG>sein.</span><span class="sxs-lookup"><span data-stu-id="39b70-157">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="39b70-158">Führen Sie die folgenden Schritte aus, um eine Zertifikatsignaturanforderung auf dem Computer zu generieren, auf dem das Zertifikat und der private Schlüssel zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="39b70-158">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="39b70-159">**Erstellen einer Zertifikatsignaturanforderung**</span><span class="sxs-lookup"><span data-stu-id="39b70-159">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="39b70-160">Öffnen Sie die Microsoft Management Console (MMC), fügen Sie das Zertifikat-Snap-in hinzu, wählen Sie **Computer**aus, und erweitern Sie dann **Personal**.</span><span class="sxs-lookup"><span data-stu-id="39b70-160">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="39b70-161">Ausführliche Informationen zum Erstellen einer Zertifikatkonsole in der Microsoft Management Console (MMC) finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .</span><span class="sxs-lookup"><span data-stu-id="39b70-161">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="39b70-162">Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, klicken Sie auf **Erweiterte Vorgänge**und dann auf **Benutzerdefinierte Anforderung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-162">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="39b70-163">Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="39b70-163">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="39b70-164">Wählen Sie auf der Seite **Zertifikatregistrierungsrichtlinie auswählen** unter **Benutzerdefinierte Anforderung**die Option **ohne Registrierungsrichtlinie fortfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-164">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="39b70-165">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="39b70-165">Click **Next**.</span></span>

5.  <span data-ttu-id="39b70-166">Klicken Sie auf der Seite **Benutzerdefinierte Anforderung** für **Vorlage** auswählen **(kein Vorlage) Legacy Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="39b70-166">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="39b70-167">Wenn nicht anders von Ihrem Zertifikatanbieter verwiesen wird, lassen Sie die Option **Standarderweiterungen** deaktivieren und die Auswahl des **Anforderungs Formats** auf **PKCS \# 10**unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="39b70-167">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="39b70-168">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="39b70-168">Click **Next**.</span></span>

6.  <span data-ttu-id="39b70-169">Klicken Sie auf der Seite **Zertifikatinformationen** auf **Details**und dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="39b70-169">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="39b70-170">Geben Sie auf der Seite **Zertifikateigenschaften** auf der Registerkarte **Allgemein** im Feld **Anzeigename** einen Namen für dieses Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="39b70-170">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="39b70-171">Geben Sie optional eine Beschreibung in das Feld **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="39b70-171">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="39b70-172">Der Anzeige Name und die Beschreibung werden normalerweise vom Administrator verwendet, um zu ermitteln, was das Zertifikatzweck ist, beispielsweise **für den Reverse Proxy Listener für lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39b70-172">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="39b70-173">Wählen Sie die Registerkarte **Betreff** aus. Wählen Sie unter **Antragstellername** für den **Typ**die Option **allgemeiner Name** für den Typ des Antragstellernamens aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-173">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="39b70-174">Geben Sie für den **Wert**den Antragstellernamen ein, den Sie für den Reverseproxy verwenden werden, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-174">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="39b70-175">In dem in der Tabelle in diesem Thema angegebenen Beispiel lautet der Antragstellername Webext.contoso.com und würde in das Feld Wert für den Antragstellernamen eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39b70-175">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="39b70-176">Wählen Sie auf der Registerkarte **Betreff** unter **alternativer Name** **DNS** aus der Dropdownliste für **Type**aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-176">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="39b70-177">Geben Sie für jeden definierten alternativen Antragstellernamen, den Sie für das Zertifikat benötigen, den vollqualifizierten Domänennamen ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-177">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="39b70-178">In der Tabelle gibt es beispielsweise drei alternative Antragstellernamen, Meet.contoso.com, dialin.contoso.com und lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="39b70-178">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="39b70-179">Geben Sie Meet.contoso.com in das Feld **Wert** ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-179">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="39b70-180">Wiederholen Sie diese Schritte für alle alternativen Antragstellernamen, die Sie definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="39b70-180">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="39b70-181">Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **Erweiterungen** . Auf dieser Seite definieren Sie die kryptografischen Schlüssel Zwecke in der **Schlüsselverwendung** und die erweiterte Schlüsselverwendung in der **erweiterten Schlüsselverwendung (Anwendungsrichtlinien)**.</span><span class="sxs-lookup"><span data-stu-id="39b70-181">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="39b70-182">Klicken Sie auf den Pfeil **Schlüsselverwendung** , um die **verfügbaren Optionen**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39b70-182">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="39b70-183">Klicken Sie unter Verfügbare Optionen auf **digitale Signatur**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-183">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="39b70-184">Klicken Sie auf **Schlüssel Verschlüsselung**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-184">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="39b70-185">Aktivieren Sie das Kontrollkästchen, wenn das Kontrollkästchen für wichtige **Verwendungen dieser Schlüssel verwenden** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="39b70-185">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="39b70-186">Klicken Sie auf den Pfeil **Erweiterte Schlüsselverwendung (Anwendungsrichtlinien)** , um die **verfügbaren Optionen**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39b70-186">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="39b70-187">Klicken Sie unter Verfügbare Optionen auf **Server Authentifizierung**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-187">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="39b70-188">Klicken Sie auf **Client Authentifizierung**und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39b70-188">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="39b70-189">Wenn das Kontrollkästchen für **die Option Erweiterte Schlüsselverwendungen kritisch** aktiviert ist, deaktivieren Sie das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="39b70-189">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="39b70-190">Im Gegensatz zum Kontrollkästchen für die Schlüsselverwendung (das überprüft werden muss) müssen Sie sicherstellen, dass das Kontrollkästchen Erweiterte Schlüsselverwendung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="39b70-190">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="39b70-191">Klicken Sie auf der Seite **Zertifikateigenschaften** auf die Registerkarte **privater Schlüssel** . Klicken Sie auf den Pfeil mit den **Schlüsseloptionen** .</span><span class="sxs-lookup"><span data-stu-id="39b70-191">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="39b70-192">Wählen Sie für die **Schlüsselgröße** **2048** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-192">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="39b70-193">Wenn Sie dieses Schlüsselpaar und CSR auf einem anderen Computer als dem Reverse-Proxy generieren, für den dieses Zertifikat vorgesehen ist, wählen Sie exportierbaren **privaten Schlüssel erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-193">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="39b70-195">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="39b70-195">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="39b70-196">Das auswählen <strong>eines exportierbaren privaten Schlüssels</strong> wird in der Regel empfohlen, wenn Sie mehr als einen Reverseproxy in einer Farm haben, da Sie das Zertifikat und den privaten Schlüssel auf jeden Computer in der Farm kopieren.</span><span class="sxs-lookup"><span data-stu-id="39b70-196">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="39b70-197">Wenn Sie einen exportierbaren privaten Schlüssel zulassen, müssen Sie mit dem Zertifikat und dem Computer, auf dem es generiert wurde, besonders vorsichtig vorgehen.</span><span class="sxs-lookup"><span data-stu-id="39b70-197">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="39b70-198">Bei Gefährdung des privaten Schlüssels wird das Zertifikat als nutzlos dargestellt, und der Computer oder Computer kann dem externen Zugriff und anderen Sicherheitsrisiken möglicherweise ausgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="39b70-198">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="39b70-199">Klicken Sie auf der Registerkarte **privater Schlüssel** auf den Pfeil des **Schlüsseltyps** .</span><span class="sxs-lookup"><span data-stu-id="39b70-199">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="39b70-200">Wählen Sie die Option **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="39b70-200">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="39b70-201">Klicken Sie auf **OK** , um die festgelegten **Zertifikateigenschaften** zu speichern.</span><span class="sxs-lookup"><span data-stu-id="39b70-201">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="39b70-202">Klicken Sie auf der Seite **Zertifikatregistrierung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="39b70-202">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="39b70-203">Auf der Seite **wo möchten Sie die Offlineanforderung speichern?** werden Sie aufgefordert, einen **Dateinamen** und ein **Datei Format** zum Speichern der Zertifikatsignaturanforderung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="39b70-203">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="39b70-204">Geben Sie im Feld Dateiname einen Pfad und einen Datei **Namen** für die Anforderung ein, oder klicken Sie auf **Durchsuchen** , um einen Speicherort für die Datei auszuwählen, und geben Sie den Dateinamen für die Anforderung ein.</span><span class="sxs-lookup"><span data-stu-id="39b70-204">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="39b70-205">Klicken Sie für das **Dateiformat**entweder auf **Base 64** oder **Binary**.</span><span class="sxs-lookup"><span data-stu-id="39b70-205">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="39b70-206">Wählen Sie **Basis 64** , es sei denn, Sie werden vom Anbieter anderweitig für Ihre Zertifikate instruiert.</span><span class="sxs-lookup"><span data-stu-id="39b70-206">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="39b70-207">Suchen Sie die Anforderungsdatei, die Sie im vorherigen Schritt gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="39b70-207">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="39b70-208">Übermitteln Sie Sie an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="39b70-208">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="39b70-209">Microsoft hat öffentliche Zertifizierungsstellen identifiziert, die die Anforderungen für Unified Communications Zwecke erfüllen.</span><span class="sxs-lookup"><span data-stu-id="39b70-209">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="39b70-210">Eine Liste wird im folgenden Knowledge Base-Artikel verwaltet.</span><span class="sxs-lookup"><span data-stu-id="39b70-210">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

