---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="d65c6-102">Konfigurieren von Zertifikaten für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d65c6-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d65c6-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d65c6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d65c6-104">Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den zu verwendeten Zertifikatvorlagentyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="d65c6-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="d65c6-105">Standardmäßig wird für eine lync Server 2013 Zertifikatanforderung die Webserverzertifikatvorlage verwendet.</span><span class="sxs-lookup"><span data-stu-id="d65c6-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="d65c6-106">Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="d65c6-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="d65c6-107">Für jeden Director wird ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat benötigt.</span><span class="sxs-lookup"><span data-stu-id="d65c6-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="d65c6-108">Ausführliche Informationen zu den Zertifikatanforderungen für Directors finden Sie in der Planungsdokumentation unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) .</span><span class="sxs-lookup"><span data-stu-id="d65c6-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="d65c6-p103">Verwenden Sie das folgende Verfahren, um Director-Zertifikate zu konfigurieren. Wiederholen Sie das Verfahren für jeden Director. Die Schritte in diesem Verfahren beschreiben, wie Sie ein Zertifikat einer internen Stammzertifizierungsstelle konfigurieren, die in Ihrem Unternehmen eingesetzt wird. Zertifikatanforderungen werden in diesem Verfahren offline verarbeitet. Ausführliche Informationen zum Anfordern von Zertifikaten bei einer externen Zertifizierungsstelle erhalten Sie von Ihrem Support-Team.</span><span class="sxs-lookup"><span data-stu-id="d65c6-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="d65c6-113">So konfigurieren Sie Zertifikate für den Director oder Director-Pool</span><span class="sxs-lookup"><span data-stu-id="d65c6-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="d65c6-114">Klicken Sie im lync Server-Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="d65c6-115">Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="d65c6-116">Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="d65c6-117">Akzeptieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="d65c6-118">Klicken Sie auf der Seite **Zertifizierungsstelle auswählen** auf die interne Windows-Zertifizierungsstelle, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="d65c6-119">Geben Sie auf der Seite **Zertifizierungsstellenkonto** alternative Anmeldeinformationen für den Fall an, dass das zur Anmeldung verwendete Konto keine ausreichenden Berechtigungen zum Anfordern des Zertifikats besitzt, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="d65c6-120">Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="d65c6-121">Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen Wert für **Anzeigename** ein, akzeptieren Sie die Schlüssellange von 2.048 Bit, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="d65c6-122">Überprüfen Sie optional die Informationen auf der Seite **Organisationsinformationen**, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="d65c6-123">Überprüfen Sie optional die Informationen auf der Seite **Geografische Informationen**, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="d65c6-124">Klicken Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d65c6-125">Die Liste der alternativen Antragstellernamen sollte den Namen des Computers enthalten, auf dem Sie den Director installieren (falls nur ein Director vorhanden ist), andernfalls den Namen des Director-Pools und die Namen der einfachen URLs, die für die Organisation konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d65c6-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="d65c6-126">Wählen Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** die Option **Konfigurierte SIP-Domänen** für alle Domänen aus, die der Director verarbeiten soll, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="d65c6-127">Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="d65c6-128">Klicken Sie auf der Seite **Zusammenfassung der Zertifikatanforderung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="d65c6-129">Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="d65c6-130">Klicken Sie auf der Seite **Status der Onlinezertifikatanforderung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="d65c6-131">Klicken Sie auf der Seite **Zertifikatzuweisung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d65c6-132">Wenn Sie das Zertifikat anzeigen möchten, doppelklicken Sie auf das Zertifikat in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d65c6-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="d65c6-133">Klicken Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="d65c6-134">Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="d65c6-135">Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d65c6-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

