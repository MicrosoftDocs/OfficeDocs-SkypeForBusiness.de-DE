---
title: 'Lync Server 2013: Ändern der Zertifikate für Mobilität'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="84a0c-102">Ändern der Zertifikate für Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84a0c-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84a0c-103">_**Letztes Änderungsdatum des Themas:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="84a0c-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="84a0c-104">Um sichere Verbindungen zwischen Ihrer lync-Umgebung und ihren mobilen Clients zu unterstützen, müssen die Secure Socket Layer (SSL)-Zertifikate für Ihren Director-Pool, Front-End-Pool und Reverse-Proxy mit einem zusätzlichen alternativen Betreff-Namen aktualisiert werden ( San)-Einträge.</span><span class="sxs-lookup"><span data-stu-id="84a0c-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="84a0c-105">Wenn Sie weitere Details zu den Zertifikatanforderungen für Mobilität lesen müssen, lesen Sie den Abschnitt Zertifikatanforderungen unter [Technische Anforderungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), aber im Grunde müssen Sie neue Zertifikate von der Zertifizierungsstelle mit den zusätzlichen San-Einträgen abrufen und diese Zertifikate dann mithilfe der Schritte dieses Artikels hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="84a0c-106">Bevor Sie beginnen, ist es in der Regel ratsam, zu wissen, welche alternativen Namen ihre Zertifikate bereits haben.</span><span class="sxs-lookup"><span data-stu-id="84a0c-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="84a0c-107">Wenn Sie sich nicht sicher sind, was bereits konfiguriert wurde, gibt es viele Möglichkeiten, dies herauszufinden. Während die Option zum Ausführen der Befehle " **Get-CsCertificate** " und "andere PowerShell" zum Anzeigen dieser Informationen (die wir weiter unten durchlaufen) standardmäßig die Daten abgeschnitten werden, werden möglicherweise nicht alle benötigten Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84a0c-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="84a0c-108">Um sich das Zertifikat und alle seine Eigenschaften genauer anzusehen, können Sie zur Microsoft Management Console (MMC) wechseln und das Zertifikat-Snap-In laden (das wir auch weiter unten durchlaufen), oder Sie können einfach den lync Server-Bereitstellungs-Assistenten einchecken.</span><span class="sxs-lookup"><span data-stu-id="84a0c-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="84a0c-109">Wie bereits erwähnt, führen Sie die folgenden Schritte durch die Aktualisierung der Zertifikate mithilfe der lync Server-Verwaltungsshell und der MMC.</span><span class="sxs-lookup"><span data-stu-id="84a0c-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="84a0c-110">Wenn Sie stattdessen den Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten für diesen Zweck verwenden möchten, können Sie für den Director-oder Director-Pool die [Konfiguration von Zertifikaten für den Director in lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) überprüfen, wenn Sie einen konfiguriert haben (Dies ist möglicherweise nicht der Fall).</span><span class="sxs-lookup"><span data-stu-id="84a0c-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="84a0c-111">Für den Front-End-Server oder den Front-End-Pool empfiehlt es sich, [Zertifikate für Server in lync Server 2013 zu konfigurieren](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="84a0c-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="84a0c-112">Als letztes sollten Sie Bedenken, dass Sie möglicherweise über ein einzelnes Standardzertifikat in ihrer lync Server 2013-Umgebung verfügen, oder dass Sie möglicherweise getrennte Zertifikate für den Standardwert (alles andere als die Webdienste), WebServicesExternal und WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="84a0c-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="84a0c-113">Was auch immer Ihre Konfiguration ist, diese Schritte sollten Ihnen helfen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="84a0c-114">So aktualisieren Sie Zertifikate mit neuen alternativen Subjektnamen mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="84a0c-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="84a0c-115">Sie müssen sich bei Ihrem lync Server 2013-Server mit einem Konto anmelden, das über lokale Administratorrechte und-Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="84a0c-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="84a0c-116">Wenn Sie die PowerShell **-Anforderungs-CsCertificate** in Schritten 12 und darüber hinaus ausführen, muss das Konto darüber hinaus über Rechte für die angegebene Zertifizierungsstelle (Certification Authority, ca) verfügen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="84a0c-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="84a0c-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="84a0c-118">Bevor Sie ein aktualisiertes Zertifikat zuweisen können, müssen Sie herausfinden, welche Zertifikate dem Server zugewiesen wurden und für welche Art von Verwendung.</span><span class="sxs-lookup"><span data-stu-id="84a0c-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="84a0c-119">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="84a0c-120">Überprüfen Sie die Ausgabe des vorherigen Schritts, um festzustellen, ob ein einzelnes Zertifikat für mehrere Zwecke zugewiesen wurde oder ob für jede Verwendung ein anderes Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="84a0c-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="84a0c-121">Schauen Sie sich den use-Parameter an, um zu erfahren, wie ein Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84a0c-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="84a0c-122">Vergleichen Sie den Parameter Fingerabdruck für die angezeigten Zertifikate, um festzustellen, ob dasselbe Zertifikat mehrere Verwendungszwecke aufweist.</span><span class="sxs-lookup"><span data-stu-id="84a0c-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="84a0c-123">Behalten Sie den Parameter Fingerabdruck im Auge.</span><span class="sxs-lookup"><span data-stu-id="84a0c-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="84a0c-124">Aktualisieren Sie das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="84a0c-124">Update the certificate.</span></span> <span data-ttu-id="84a0c-125">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="84a0c-126">Wenn beispielsweise das Cmdlet " **Get-CsCertificate** " ein Zertifikat mit der Verwendung von Default, einem anderen mit einer Verwendung von WebServicesInternal und einem anderen mit einer Verwendung von WebServicesExternal angezeigt hat und alle denselben Fingerabdruckwert hatten, sollten Sie in der Befehlszeile Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="84a0c-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="84a0c-127">**Wichtig:**</span><span class="sxs-lookup"><span data-stu-id="84a0c-127">**Important:**</span></span>
    
    <span data-ttu-id="84a0c-128">Wenn für jede Verwendung ein separates Zertifikat zugewiesen wird (damit der von Ihnen geprüfte Fingerabdruckwert für jedes Zertifikat anders ist), ist es wichtig, dass Sie das Cmdlet " **CsCertificate** " **nicht** mit mehreren Typen ausführen, wie im obigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="84a0c-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="84a0c-129">Führen Sie in diesem Fall das Cmdlet " **Satz-CsCertificate** " für jede Verwendung separat aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="84a0c-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84a0c-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="84a0c-131">Klicken Sie zum Anzeigen des Zertifikats (oder der Zertifikate) auf **Start**, klicken Sie auf **ausführen.**...</span><span class="sxs-lookup"><span data-stu-id="84a0c-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="84a0c-132">Geben Sie MMC ein, um die Microsoft Management Console zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="84a0c-133">Wählen Sie im MMC-Menü **Datei**aus, wählen Sie **Snap-in hinzufügen/entfernen**aus, und wählen Sie Zertifikate aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="84a0c-134">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="84a0c-134">Click **Add**.</span></span> <span data-ttu-id="84a0c-135">Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="84a0c-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="84a0c-136">Wenn es sich um den Server handelt, auf dem sich das Zertifikat befindet, wählen Sie **lokaler Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="84a0c-137">Wenn sich das Zertifikat auf einem anderen Computer befindet, sollten Sie **einen anderen Computer**auswählen, und dann können Sie entweder den vollqualifizierten Domänennamen des Computers eingeben, oder Sie klicken auf **Durchsuchen** **Geben Sie den zu wählenden Objektnamen**ein, und geben Sie den Namen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="84a0c-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="84a0c-138">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="84a0c-138">Click **Check Names**.</span></span> <span data-ttu-id="84a0c-139">Wenn der Name des Computers aufgelöst wird, wird er unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="84a0c-140">Klicken Sie auf **OK**und dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="84a0c-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="84a0c-141">Klicken Sie auf **OK** , um die Auswahl zu bestätigen, und schließen Sie das Dialogfeld **Snap-Ins hinzufügen oder entfernen** .</span><span class="sxs-lookup"><span data-stu-id="84a0c-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="84a0c-142">Wenn Sie die Eigenschaften des Zertifikats anzeigen möchten, erweitern Sie **Zertifikate**, erweitern Sie **Personal**, und wählen Sie **Zertifikate**aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="84a0c-143">Wählen Sie das Zertifikat aus, das Sie anzeigen möchten, klicken Sie mit der rechten Maustaste auf das Zertifikat, und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="84a0c-144">Wählen Sie in der **Zertifikat** Ansicht **Details**aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="84a0c-145">Hier können Sie den Namen des Zertifikat Antragstellers auswählen, indem Sie **Betreff** auswählen und der zugewiesene Antragstellername und die zugehörigen Eigenschaften angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="84a0c-146">Wenn Sie die alternativen Namen des zugewiesenen betreffs anzeigen möchten, wählen Sie **alternativer Betreffname**aus.</span><span class="sxs-lookup"><span data-stu-id="84a0c-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="84a0c-147">Hier werden alle zugewiesenen Subjekt alternativen Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84a0c-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="84a0c-148">Die hier gefundenen Alternativen Betreff-Namen sind standardmäßig vom Typ **DNS-Name** .</span><span class="sxs-lookup"><span data-stu-id="84a0c-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="84a0c-149">Die folgenden Member sollten angezeigt werden (alle sollten vollqualifizierte Domänennamen sein, die in DNS-Hosteinträgen (A oder, wenn IPv6 AAAA) dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="84a0c-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="84a0c-150">Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt</span><span class="sxs-lookup"><span data-stu-id="84a0c-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="84a0c-151">Server Name, dem das Zertifikat zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="84a0c-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="84a0c-152">Einfache URL-Einträge, in der Regel treffen und einwählen</span><span class="sxs-lookup"><span data-stu-id="84a0c-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="84a0c-153">Webdienste interne und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den Optionen, die im Topologie-Generator und über berittenen Webdiensten ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="84a0c-154">Wenn Sie bereits zugewiesen ist, wird die lyncdiscover. \<sipdomain\> und lyncdiscoverinternal. \<sipdomain\> -Datensätze.</span><span class="sxs-lookup"><span data-stu-id="84a0c-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="84a0c-155">Das letzte Element ist das, was Sie am meisten interessieren – wenn ein lyncdiscover-und lyncdiscoverinternal-San-Eintrag vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="84a0c-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="84a0c-156">Wiederholen Sie diese Schritte, wenn Sie über mehrere zu überprüfende Zertifikate verfügen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="84a0c-157">Sobald Sie über diese Informationen verfügen, können Sie die Zertifikat Ansicht und die MMC schließen.</span><span class="sxs-lookup"><span data-stu-id="84a0c-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="84a0c-158">Gehen Sie wie folgt vor, wenn der Alternative Name des AutoErmittlungsdiensts nicht vorhanden ist und Sie ein einzelnes Standardzertifikat für die Typen Standard, WebServicesInternal und WebServiceExternal verwenden:</span><span class="sxs-lookup"><span data-stu-id="84a0c-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="84a0c-159">Geben Sie an der Eingabeaufforderung der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="84a0c-160">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="84a0c-161">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="84a0c-162">Wenn Sie den Parameter Domain Name verwenden, müssen Sie den FQDN für die lyncdiscoverinternal-und lyncdiscover-Datensätze definieren.</span><span class="sxs-lookup"><span data-stu-id="84a0c-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="84a0c-163">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84a0c-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="84a0c-164">Um das Zertifikat zuzuweisen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="84a0c-165">Wobei "Daumenabdruck" der für das neu ausgestellte Zertifikat angezeigte Fingerabdruck ist.</span><span class="sxs-lookup"><span data-stu-id="84a0c-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="84a0c-166">Gehen Sie bei einem fehlenden internen autodiscover-San bei Verwendung separater Zertifikate für Standard, WebServicesInternal und WebServicesExternal wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="84a0c-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="84a0c-167">Geben Sie an der Eingabeaufforderung der Befehlszeile der lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="84a0c-168">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="84a0c-169">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="84a0c-170">Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="84a0c-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84a0c-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="84a0c-172">Geben Sie für einen fehlenden externen Auto Ermittlungs Betreff-alternativen Namen in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="84a0c-173">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="84a0c-174">Stattdessen müssen Sie den Domain Name-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="84a0c-175">Wenn Sie den Parameter Domain Name verwenden, müssen Sie ein entsprechendes Präfix für den FQDN der SIP-Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="84a0c-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="84a0c-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84a0c-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="84a0c-177">Wenn Sie die einzelnen Zertifikattypen zuweisen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="84a0c-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="84a0c-178">Wobei "Daumenabdruck" der für die neu ausgestellten einzelnen Zertifikate angezeigte Fingerabdruck ist.</span><span class="sxs-lookup"><span data-stu-id="84a0c-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84a0c-179">Einfach zu beachten: die Schritte 12 und 13 sollten nur ausgeführt werden, wenn das Konto, auf dem Sie ausgeführt wird, Zugriff auf die Zertifizierungsstelle mit den entsprechenden Berechtigungen hat.</span><span class="sxs-lookup"><span data-stu-id="84a0c-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="84a0c-180">Wenn Sie sich nicht mit einem Konto anmelden können, das diese Berechtigungen hat, oder wenn Sie eine öffentliche oder Remote-Zertifizierungsstelle für Ihre Zertifikate verwenden, müssen Sie diese über den lync Server-Bereitstellungs-Assistenten anfordern, der oben im Artikel.</span><span class="sxs-lookup"><span data-stu-id="84a0c-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

