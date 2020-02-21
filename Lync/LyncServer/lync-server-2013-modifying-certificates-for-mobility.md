---
title: 'Lync Server 2013: Ändern von Zertifikaten für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64676494916bf2c2bd71399bbdd04642da50cee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7a51a-102">Ändern von Zertifikaten für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a51a-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a51a-103">_**Letztes Änderungsstand des Themas:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="7a51a-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="7a51a-104">Um sichere Verbindungen zwischen Ihrer lync-Umgebung und ihren mobilen Clients zu unterstützen, müssen die SSL-Zertifikate (Secure Socket Layer) für Ihre Directorpool, Front-End-Pool und Reverseproxy mit einigen zusätzlichen alternativen Antragstellernamen aktualisiert werden ( San)-Einträge.</span><span class="sxs-lookup"><span data-stu-id="7a51a-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="7a51a-105">Wenn Sie weitere Details zu den Zertifikatanforderungen für Mobilität lesen müssen, lesen Sie den Abschnitt Zertifikatanforderungen unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), aber im Grunde müssen Sie neue Zertifikate von der Zertifizierungsstelle mit den zusätzlichen San-Einträgen erhalten, und fügen Sie diese Zertifikate dann mithilfe der Schritte dieses Artikels hinzu.</span><span class="sxs-lookup"><span data-stu-id="7a51a-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="7a51a-106">Bevor Sie beginnen, ist es normalerweise ratsam zu wissen, welche alternativen Antragstellernamen ihre Zertifikate bereits besitzen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="7a51a-107">Wenn Sie nicht sicher sind, was bereits konfiguriert ist, gibt es viele Möglichkeiten, dies herauszufinden. Während die Option zum Ausführen der Befehle **Get-CsCertificate** und other PowerShell zum Anzeigen dieser Informationen (die wir weiter unten durchlaufen) standardmäßig die Daten abgeschnitten werden, sodass Sie möglicherweise nicht alle Eigenschaften angezeigt werden, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="7a51a-108">Um ein gutes Bild des Zertifikats und seiner Eigenschaften zu erhalten, können Sie zur Microsoft Management Console (MMC) wechseln und das Zertifikat-Snap-in (das wir auch weiter unten durchlaufen) laden, oder Sie können einfach den lync Server-Bereitstellungs-Assistenten einchecken.</span><span class="sxs-lookup"><span data-stu-id="7a51a-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="7a51a-109">Wie oben erwähnt, führen Sie die folgenden Schritte durch die Aktualisierung der Zertifikate mithilfe der lync Server-Verwaltungsshell und der MMC.</span><span class="sxs-lookup"><span data-stu-id="7a51a-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="7a51a-110">Wenn Sie den Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten für diese stattdessen verwenden möchten, können Sie in lync Server 2013 für den Director oder den Directorpool [Konfigurieren von Zertifikaten für den Director](lync-server-2013-configure-certificates-for-the-director.md) überprüfen, wenn Sie einen konfiguriert haben (möglicherweise nicht).</span><span class="sxs-lookup"><span data-stu-id="7a51a-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="7a51a-111">Für die Front-End-Server oder Front-End-Pool sollten Sie die Informationen zum [Konfigurieren von Zertifikaten für Server in lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="7a51a-112">Als letztes müssen Sie Bedenken, dass Sie möglicherweise ein einzelnes Standardzertifikat in ihrer lync Server 2013 Umgebung haben oder wenn Sie unterschiedliche Zertifikate für den Standardwert (alles andere als die Webdienste), "webservicesexternal" und "webservicesinternal".</span><span class="sxs-lookup"><span data-stu-id="7a51a-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="7a51a-113">Unabhängig von Ihrer Konfiguration sollten diese Schritte Ihnen helfen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="7a51a-114">So aktualisieren Sie Zertifikate mit neuen alternativen Antragstellernamen mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="7a51a-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="7a51a-115">Sie müssen sich bei Ihrem lync Server 2013 Server mit einem Konto anmelden, das über lokale Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="7a51a-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="7a51a-116">Wenn Sie den PowerShell **-Anforderungs-CsCertificate** in den Schritten 12 und darüber hinaus ausführen, benötigt das Konto außerdem Rechte für die angegebene Zertifizierungsstelle (Certification Authority, ca).</span><span class="sxs-lookup"><span data-stu-id="7a51a-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="7a51a-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7a51a-118">Bevor Sie ein aktualisiertes Zertifikat zuweisen können, müssen Sie herausfinden, welche Zertifikate dem Server zugewiesen wurden und für welchen Verwendungstyp.</span><span class="sxs-lookup"><span data-stu-id="7a51a-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="7a51a-119">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7a51a-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="7a51a-120">Überprüfen Sie die Ausgabe des vorherigen Schritts, um festzustellen, ob ein einzelnes Zertifikat für mehrere Zwecke verwendet wurde oder ob für jede Verwendung ein anderes Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7a51a-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="7a51a-121">Suchen Sie im Use-Parameter, um herauszufinden, wie ein Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a51a-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="7a51a-122">Vergleichen Sie den Thumbprint-Parameter für die angezeigten Zertifikate, um festzustellen, ob ein Zertifikat für mehrere Verwendungszwecke vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="7a51a-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="7a51a-123">Halten Sie den Fingerabdruck Parameter im Auge.</span><span class="sxs-lookup"><span data-stu-id="7a51a-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="7a51a-124">Aktualisieren Sie das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="7a51a-124">Update the certificate.</span></span> <span data-ttu-id="7a51a-125">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7a51a-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="7a51a-126">Wenn das **Get-CsCertificate-** Cmdlet beispielsweise ein Zertifikat mit der Standardeinstellung, ein anderes mit einer Verwendung von "webservicesinternal" und ein anderes mit einer Verwendung von "webservicesexternal" angezeigt wurde und alle denselben Fingerabdruckwert hatten, sollten Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="7a51a-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="7a51a-127">**Wichtig:**</span><span class="sxs-lookup"><span data-stu-id="7a51a-127">**Important:**</span></span>
    
    <span data-ttu-id="7a51a-128">Wenn für jede Verwendung ein separates Zertifikat zugewiesen wird (damit der von Ihnen überprüfte Fingerabdruckwert für jedes Zertifikat unterschiedlich ist), ist es wichtig, dass Sie das Cmdlet " **CsCertificate** " **nicht** mit mehreren Typen ausführen, wie im obigen Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7a51a-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="7a51a-129">Führen Sie in diesem Fall das **Set-CsCertificate**-Cmdlet für jeden Verwendungszweck separat aus.</span><span class="sxs-lookup"><span data-stu-id="7a51a-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="7a51a-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7a51a-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="7a51a-131">Klicken Sie zum Anzeigen des Zertifikats (oder der Zertifikate) auf **Start**, klicken Sie auf **ausführen.**</span><span class="sxs-lookup"><span data-stu-id="7a51a-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="7a51a-132">Geben Sie "MMC" ein, um die Microsoft Management Console zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="7a51a-133">Wählen Sie im MMC-Menü den Eintrag **Datei** und dann **Snap-In hinzufügen/entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="7a51a-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="7a51a-134">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-134">Click **Add**.</span></span> <span data-ttu-id="7a51a-135">Wählen Sie das **Computerkonto**, wenn Sie dazu aufgefordert werden, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="7a51a-136">Wenn es sich um den Server handelt, auf dem sich das Zertifikat befindet, wählen Sie **lokaler Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="7a51a-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="7a51a-137">Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **einen anderen Computer**aus, und geben Sie dann entweder den vollqualifizierten Domänennamen des Computers ein, oder klicken Sie auf **Durchsuchen** **Geben Sie den zu verwendenden Objektnamen**ein ein, und geben Sie den Namen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="7a51a-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="7a51a-138">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-138">Click **Check Names**.</span></span> <span data-ttu-id="7a51a-139">Wenn der Name des Computers aufgelöst wird, wird er unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="7a51a-140">Klicken Sie auf **OK**und dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="7a51a-141">Klicken Sie auf **OK** , um einen Commit für die Auswahl auszuführen und das Dialogfeld **Snap-Ins hinzufügen oder entfernen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="7a51a-p113">Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate**, und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="7a51a-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="7a51a-p114">Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a51a-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="7a51a-146">Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus.</span><span class="sxs-lookup"><span data-stu-id="7a51a-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="7a51a-147">Hier werden alle zugewiesenen alternativen Antragstellernamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a51a-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="7a51a-148">Die alternativen Antragstellernamen, die hier gefunden werden, sind standardmäßig vom Typ **DNS-Name** .</span><span class="sxs-lookup"><span data-stu-id="7a51a-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="7a51a-149">Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:</span><span class="sxs-lookup"><span data-stu-id="7a51a-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="7a51a-150">Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt</span><span class="sxs-lookup"><span data-stu-id="7a51a-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="7a51a-151">Der Name des Servers, dem das Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7a51a-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="7a51a-152">Einfache URL-Datensätze, üblicherweise "meet" und "dialin".</span><span class="sxs-lookup"><span data-stu-id="7a51a-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="7a51a-153">Interne Webdienste und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den im Topologie-Generator und über berittenen Webdiensten vorgenommenen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="7a51a-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="7a51a-154">Wenn bereits zugewiesen, lyncdiscover. \<sipdomain "\> und" lyncdiscoverinternal ". \<sipdomain "\> -Datensätze.</span><span class="sxs-lookup"><span data-stu-id="7a51a-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="7a51a-155">Am meisten interessieren Sie sich für das letzte Element – Wenn ein lyncdiscover-und "lyncdiscoverinternal"-San-Eintrag vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7a51a-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="7a51a-156">Wiederholen Sie diese Schritte, wenn Sie über mehrere Zertifikate zu überprüfen haben.</span><span class="sxs-lookup"><span data-stu-id="7a51a-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="7a51a-157">Sobald Sie über diese Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.</span><span class="sxs-lookup"><span data-stu-id="7a51a-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="7a51a-158">Gehen Sie wie folgt vor, wenn ein alternativer Antragstellername für den AutoErmittlungsdienst fehlt und Sie ein einzelnes Standardzertifikat für die Typen "Default", "WebServicesInternal" und "WebServicesExternal" verwenden:</span><span class="sxs-lookup"><span data-stu-id="7a51a-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="7a51a-159">Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7a51a-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="7a51a-160">Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="7a51a-161">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="7a51a-162">Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die "lyncdiscoverinternal"-und lyncdiscover-Datensätze definieren.</span><span class="sxs-lookup"><span data-stu-id="7a51a-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="7a51a-163">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7a51a-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="7a51a-164">Geben Sie Folgendes ein, um das Zertifikat zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="7a51a-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="7a51a-165">"Thumbprint" steht für den Fingerabdruck, der für das neu ausgestellte Zertifikat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7a51a-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="7a51a-166">Gehen Sie für ein fehlendes internes Auto Ermittlungs-San bei Verwendung von separaten Zertifikaten für Default, "webservicesinternal" und "webservicesexternal" folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7a51a-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="7a51a-167">Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7a51a-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="7a51a-168">Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="7a51a-169">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="7a51a-170">Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="7a51a-171">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7a51a-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="7a51a-172">Wenn ein alternativer Antragstellername für einen externen AutoErmittlungsdienst fehlt, geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7a51a-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="7a51a-173">Wenn Sie über zahlreiche SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="7a51a-174">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="7a51a-175">Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a51a-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="7a51a-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7a51a-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="7a51a-177">Geben Sie Folgendes ein, um die einzelnen Zertifikattypen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="7a51a-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="7a51a-178">"Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten Zertifikate angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7a51a-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a51a-179">Beachten Sie, dass die Schritte 12 und 13 nur ausgeführt werden sollten, wenn das Konto, auf dem Sie ausgeführt werden, über die entsprechenden Berechtigungen auf die Zertifizierungsstelle zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="7a51a-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="7a51a-180">Wenn Sie sich nicht mit einem Konto anmelden können, das diese Berechtigungen besitzt, oder wenn Sie eine öffentliche oder Remotezertifizierungsstelle für Ihre Zertifikate verwenden, müssen Sie diese über den lync Server-Bereitstellungs-Assistenten anfordern, der oben im Artikel.</span><span class="sxs-lookup"><span data-stu-id="7a51a-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

