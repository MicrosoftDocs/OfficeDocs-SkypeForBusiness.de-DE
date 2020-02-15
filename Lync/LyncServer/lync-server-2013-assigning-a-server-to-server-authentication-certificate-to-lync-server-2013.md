---
title: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbead49c200ab1b679ef9b4ffa3d9b03bb72cd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="be22c-102">Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be22c-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be22c-103">_**Letztes Änderungsstand des Themas:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="be22c-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="be22c-104">Um zu ermitteln, ob Microsoft lync Server 2013 bereits ein Server-zu-Server-Authentifizierungszertifikat zugewiesen wurde, führen Sie den folgenden Befehl in der lync Server 2013-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="be22c-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="be22c-105">Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Token-Ausstellerzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="be22c-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="be22c-106">Allgemein gilt, dass lync Server 2013 Zertifikat als OAuthTokenIssuer-Zertifikat verwendet werden kann. Beispielsweise kann das lync Server 2013 Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be22c-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="be22c-107">(Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen der SIP-Domäne im Feld Betreff enthält.) Die primären zwei Anforderungen für das Zertifikat, das für die Server-zu-Server-Authentifizierung verwendet wird, sind folgende: 1) das gleiche Zertifikat muss als OAuthTokenIssuer-Zertifikat auf allen Front-End-Servern konfiguriert sein. und, 2) das Zertifikat muss mindestens 2048 Bits sein.</span><span class="sxs-lookup"><span data-stu-id="be22c-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="be22c-108">Wenn Sie nicht über ein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat erhalten, das neue Zertifikat importieren und dann dieses Zertifikat für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="be22c-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="be22c-109">Nachdem Sie das neue Zertifikat angefordert und erhalten haben, können Sie sich dann bei einem beliebigen Front-End-Server anmelden und einen Windows PowerShell-Befehl wie den folgenden verwenden, um dieses Zertifikat zu importieren und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="be22c-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="be22c-110">Im vorherigen Befehl stellt der Parameter path den vollständigen Pfad zur Zertifikatsdatei dar, und der Parameter Password stellt das Kennwort dar, das dem Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="be22c-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="be22c-111">Dieses Verfahren sollte nur einmal ausgeführt werden: der Replikationsdienst von lync Server erstellt dann automatisch eine Reihe geplanter Aufgaben, mit denen das Zertifikat auf allen Front-End-Servern entschlüsselt und bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="be22c-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="be22c-112">Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="be22c-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="be22c-113">(Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Das folgende paar Windows PowerShell Befehle Ruft den Wert der Eigenschaft "Fingerabdruck" des Standardzertifikats ab und verwendet diesen Wert, um das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat festzustellen:</span><span class="sxs-lookup"><span data-stu-id="be22c-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="be22c-114">Im vorherigen Befehl ist das abgerufene Zertifikat für die Funktion als globales Server-zu-Server-Authentifizierungszertifikat konfiguriert. Das bedeutet, dass das Zertifikat auf allen Front-End-Servern repliziert und von diesen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be22c-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="be22c-115">Dieser Befehl sollte wiederum nur einmal und nur auf einem Ihrer Front-End-Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be22c-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="be22c-116">Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das OAuthTokenIssuer-Zertifikat nicht auf jeder Front-End-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="be22c-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="be22c-117">Konfigurieren Sie das Zertifikat stattdessen einmal, und überlassen Sie es dem Replikations Server von lync Server, dieses Zertifikat auf jeden Server zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="be22c-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="be22c-118">Das Cmdlet "CsCertificate" übernimmt das betreffende Zertifikat und konfiguriert dieses Zertifikat sofort als Aktuelles OAuthTokenIssuer-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="be22c-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="be22c-119">(Lync Server 2013 zwei Kopien eines Zertifikattyps aufbewahrt: das aktuelle Zertifikat und das vorherige Zertifikat.) Wenn das neue Zertifikat sofort als OAuthTokenIssuer-Zertifikat fungieren soll, sollten Sie das Cmdlet "CsCertificate" verwenden.</span><span class="sxs-lookup"><span data-stu-id="be22c-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="be22c-120">Sie können auch das Cmdlet "CsCertificate" verwenden, um ein neues Zertifikat zu "Rollen".</span><span class="sxs-lookup"><span data-stu-id="be22c-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="be22c-121">"Rolling" ein Zertifikat bedeutet einfach, dass Sie ein neues Zertifikat zu einem bestimmten Zeitpunkt als Aktuelles OAuthTokenIssuer-Zertifikat konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="be22c-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="be22c-122">Dieser Befehl ruft beispielsweise das Standardzertifikat ab und konfiguriert dann das Zertifikat für die Übernahme als Aktuelles OAuthTokenIssuer-Zertifikat vom 1. Juli 2012:</span><span class="sxs-lookup"><span data-stu-id="be22c-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="be22c-123">Am 1. Juli 2012 wird das neue Zertifikat als Aktuelles OAuthTokenIssuer-Zertifikat konfiguriert, und das alte OAuthTokenIssuer-Zertifikat wird als das vorherige Zertifikat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="be22c-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="be22c-124">Wenn Sie Windows PowerShell nicht verwenden möchten, können Sie auch die MMC-Konsole Zertifikate verwenden, um ein Zertifikat aus einem Front-End-Server zu exportieren und dieses Zertifikat dann auf allen anderen Front-End-Servern zu importieren.</span><span class="sxs-lookup"><span data-stu-id="be22c-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="be22c-125">Wenn Sie dies tun, stellen Sie sicher, dass Sie den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.</span><span class="sxs-lookup"><span data-stu-id="be22c-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="be22c-126">In diesem Fall muss die Prozedur für jede Front-End-Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be22c-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="be22c-127">Beim Exportieren und Importieren von Zertifikaten auf diese Weise werden lync Server 2013 dieses Zertifikat nicht für jeden Front-End-Server repliziert.</span><span class="sxs-lookup"><span data-stu-id="be22c-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="be22c-128">Nachdem das Zertifikat auf alle Front-End-Server importiert wurde, kann dieses Zertifikat mithilfe des lync Server-Bereitstellungs-Assistenten anstelle von Windows PowerShell zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="be22c-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="be22c-129">Wenn Sie ein Zertifikat mithilfe des Bereitstellungs-Assistenten zuweisen möchten, führen Sie die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="be22c-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="be22c-130">Klicken Sie im Startmenü auf alle Programme, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="be22c-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="be22c-131">Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="be22c-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="be22c-132">Klicken Sie auf der Seite Microsoft lync Server 2013 unter der Überschrift **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="be22c-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="be22c-133">(Hinweis: Wenn Sie bereits Zertifikate auf diesem Computer installiert haben, wird die Schaltfläche **Ausführen** erneut mit der Bezeichnung **Run**versehen.)</span><span class="sxs-lookup"><span data-stu-id="be22c-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="be22c-134">Wählen Sie im Zertifikat-Assistenten das **OAuthTokenIssuer** -Zertifikat aus, und klicken Sie dann auf **zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="be22c-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="be22c-135">Klicken Sie im Assistenten für die zertifikatzuweisung auf der Seite **zertifikatzuweisung** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="be22c-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="be22c-136">Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="be22c-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="be22c-137">Klicken Sie auf der Seite Zusammenfassung der Zertifikatzuweisung auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="be22c-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="be22c-138">Klicken Sie auf der Seite Befehle ausführen auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="be22c-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="be22c-139">Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="be22c-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

