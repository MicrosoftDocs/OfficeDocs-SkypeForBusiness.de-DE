---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502112"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="b75c6-102">Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b75c6-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b75c6-103">_**Letztes Änderungsstand des Themas:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="b75c6-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="b75c6-104">Die Zertifikate für Ihre Directorpool, Front-End-Pool und Reverseproxy erfordern zusätzliche Alternative Antragstellernamen Einträge zur Unterstützung sicherer Verbindungen mit lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="b75c6-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b75c6-105">Mit dem Cmdlet <STRONG>Get-CsCertificate</STRONG> können Sie Informationen über die derzeit zugewiesenen Zertifikate anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="b75c6-106">In der Standardansicht werden die Eigenschaften des Zertifikats jedoch abgeschnitten, und die Werte in der Eigenschaft "SubjectAlternativeNames" werden nicht vollständig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b75c6-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="b75c6-107">Mit den Cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate und <STRONG>Set-CsCertificate</STRONG> können Sie einige Informationen anzeigen und Zertifikate anfordern sowie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="b75c6-108">Wenn Sie sich bezüglich der Eigenschaften der alternativen Antragstellernamen im aktuellen Zertifikat unsicher sind, ist dies jedoch nicht unbedingt die am besten geeignete Methode.</span><span class="sxs-lookup"><span data-stu-id="b75c6-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="b75c6-109">Um das Zertifikat und alle Eigenschaften Mitglieder anzuzeigen, wird empfohlen, das Zertifikat-Snap-in <EM>Microsoft Management Console (MMC)</EM> zu verwenden oder den lync Server-Bereitstellungs-Assistenten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="b75c6-110">Im lync Server-Bereitstellungs-Assistenten können Sie den Zertifikat-Assistenten verwenden, um die Zertifikateigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="b75c6-111">Die Verfahren zum Anzeigen, anfordern und Zuweisen eines Zertifikats mithilfe der lync Server-Verwaltungsshell und der <EM>MMC (Microsoft Management Console)</EM> werden in den folgenden Verfahren erläutert.</span><span class="sxs-lookup"><span data-stu-id="b75c6-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="b75c6-112">Informationen zum Verwenden des lync Server-Bereitstellungs-Assistenten finden Sie unter Details hier, wenn Sie den optionalen Director oder Directorpool: <A href="lync-server-2013-configure-certificates-for-the-director.md">configure certificates for the Director in lync Server 2013</A>bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="b75c6-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="b75c6-113">Informationen zum Front-End-Server oder Front-End-Pool finden Sie unter Details hier: <A href="lync-server-2013-configure-certificates-for-servers.md">Konfigurieren von Zertifikaten für Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b75c6-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="b75c6-114">Die ersten Schritte in diesem Verfahren sind Vorbereitungsschritte zur Orientierung an der Rolle, die die aktuellen Zertifikate spielen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="b75c6-115">Standardmäßig verfügen die Zertifikate über keine lyncdiscover. &lt; sipdomain " &gt; oder" lyncdiscoverinternal ". &lt; Interner Domänennamen &gt; Eintrag, es sei denn, Sie haben zuvor Mobilitätsdienste installiert oder Ihre Zertifikate im Voraus vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="b75c6-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="b75c6-116">Dieses Verfahren verwendet den SIP-Domänennamen "contoso.com" und den Beispiel internen Domänennamen "contoso.net".</span><span class="sxs-lookup"><span data-stu-id="b75c6-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="b75c6-117">Die Standardzertifikat Konfiguration für lync Server 2013 und lync Server 2010 besteht darin, ein einzelnes Zertifikat (mit dem Namen "Default") mit dem Verwendungszweck default (für alle Zwecke außer für die Webdienste), "webservicesexternal" und "webservicesinternal" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="b75c6-118">Optional können Sie ein separates Zertifikat für jeden Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="b75c6-119">Zertifikate können mithilfe der Cmdlets lync Server-Verwaltungsshell und Windows PowerShell oder mithilfe des Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="b75c6-120">So aktualisieren Sie Zertifikate mit neuen alternativen Antragstellernamen mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b75c6-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="b75c6-121">Melden Sie sich am Computer mit einem Konto an, das über die Rechte und Berechtigungen eines lokalen Administrators verfügt.</span><span class="sxs-lookup"><span data-stu-id="b75c6-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="b75c6-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b75c6-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b75c6-p104">Stellen Sie fest, welche Zertifikate dem Server für welchen Verwendungszweck zugeordnet wurden. Sie benötigen diese Informationen im nächsten Schritt, um das aktualisierte Zertifikat zuzuweisen. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="b75c6-p105">Suchen Sie in der Ausgabe des im vorherigen Schritte eingegebenen Befehls, ob ein einzelnes Zertifikat für mehrere Verwendungszwecke vorhanden ist oder ob für jeden Verwendungszweck ein anderes Zertifikat zugewiesen wurde. Sie können anhand des Use-Parameters feststellen, wie ein Zertifikat verwendet wird. Vergleichen Sie den Thumbprint-Parameter für die angezeigten Zertifikate, um festzustellen, ob ein Zertifikat für mehrere Verwendungszwecke vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="b75c6-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="b75c6-p106">Aktualisieren Sie das Zertifikat. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="b75c6-131">Wenn das **Get-CsCertificate**-Cmdlet beispielsweise drei Zertifikate anzeigt, deren Use-Parameter jeweils einen anderen Wert ("Default", "WebServicesInternal" und "WebServicesExternal") enthält und alle denselben Thumbprint-Wert aufweisen, geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="b75c6-132">**Wichtig:**</span><span class="sxs-lookup"><span data-stu-id="b75c6-132">**Important:**</span></span>
    
    <span data-ttu-id="b75c6-133">Wenn für jeden Verwendungszweck ein anderes Zertifikat zugewiesen ist (der Thumbprint-Wert ist für jedes Zertifikat unterschiedlich), ist es wichtig, dass Sie das **Set-CsCertificate**-Cmdlet nicht mit mehreren Typen ausführen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="b75c6-134">Führen Sie in diesem Fall das **Set-CsCertificate**-Cmdlet für jeden Verwendungszweck separat aus.</span><span class="sxs-lookup"><span data-stu-id="b75c6-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="b75c6-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b75c6-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="b75c6-p108">Um das Zertifikat anzuzeigen, klicken Sie auf **Start** und auf **Ausführen**. Geben Sie "MMC" ein, um die Microsoft Management Console zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="b75c6-p109">Wählen Sie im MMC-Menü den Eintrag **Datei** und dann **Snap-In hinzufügen/entfernen** aus. Klicken Sie auf **Hinzufügen**. Wählen Sie das **Computerkonto**, wenn Sie dazu aufgefordert werden, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b75c6-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="b75c6-141">Wenn sich das Zertifikat auf diesem Computer befindet, wählen Sie **lokaler Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="b75c6-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="b75c6-142">Wenn sich das Zertifikat auf einem anderen Computer befindet, wählen Sie **einen anderen Computer**aus, geben Sie den vollqualifizierten Domänennamen des Computers ein, oder klicken Sie auf **Durchsuchen** geben Sie den Namen des **zu verwendenden Objekts**ein, geben Sie den Namen des Computers ein.</span><span class="sxs-lookup"><span data-stu-id="b75c6-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="b75c6-143">Klicken Sie auf **Namen überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="b75c6-143">Click **Check Names**.</span></span> <span data-ttu-id="b75c6-144">Wenn der Name des Computers aufgelöst ist, wird er unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="b75c6-145">Klicken Sie auf **OK**und dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b75c6-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="b75c6-146">Klicken Sie auf **OK** , um einen Commit für die Auswahl auszuführen und das Dialogfeld **Snap-Ins hinzufügen oder entfernen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b75c6-147">Wenn das Zertifikat nicht in der Konsole angezeigt wird, stellen Sie sicher, dass Sie keinen Benutzer oder Dienst ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b75c6-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="b75c6-148">Sie müssen Computer auswählen, oder das probper-Zertifikat kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="b75c6-p112">Um die Eigenschaften des Zertifikats anzuzeigen, erweitern Sie den Eintrag **Zertifikate** und den Eintrag **Eigene Zertifikate**, und wählen Sie **Zertifikate** aus. Klicken Sie mit der rechten Maustaste auf das Zertifikat, das Sie anzeigen möchten, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b75c6-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="b75c6-p113">Wählen Sie in der Ansicht **Zertifikat** den Eintrag **Details** aus. Dort können Sie den Namen des Zertifikat-Antragstellers auswählen, indem Sie den **Antragsteller** auswählen. Daraufhin wird der zugewiesene Antragstellername zusammen mit den zugewiesenen Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b75c6-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="b75c6-153">Um die zugewiesenen alternativen Antragstellernamen anzuzeigen, wählen Sie **Alternativer Antragstellername** aus.</span><span class="sxs-lookup"><span data-stu-id="b75c6-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="b75c6-154">Daraufhin werden alle zugewiesenen alternativen Antragstellernamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b75c6-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="b75c6-155">Die alternativen Antragstellernamen der Eigenschaft weisen normalerweise den Typ **DNS-Name** auf.</span><span class="sxs-lookup"><span data-stu-id="b75c6-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="b75c6-156">Die Datensätze folgender Member (bei denen es sich jeweils um einen vollqualifizierten Domänennamen wie im DNS-Host dargestellt (A oder bei IPv6 AAAA) handeln sollte) werden erwartet:</span><span class="sxs-lookup"><span data-stu-id="b75c6-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="b75c6-157">Der Poolname für diesen Pool oder der Name des einzelnen Servers, wenn es sich nicht um einen Pool handelt.</span><span class="sxs-lookup"><span data-stu-id="b75c6-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="b75c6-158">Der Name des Servers, dem das Zertifikat zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b75c6-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="b75c6-159">Einfache URL-Datensätze, üblicherweise "meet" und "dialin".</span><span class="sxs-lookup"><span data-stu-id="b75c6-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="b75c6-160">Interne Webdienste und Webdienste externe Namen (beispielsweise webpool01.contoso.net, webpool01.contoso.com), basierend auf den im Topologie-Generator und über berittenen Webdiensten vorgenommenen Auswahlmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="b75c6-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="b75c6-161">Wenn bereits zugewiesen, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="b75c6-161">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="b75c6-162">und "lyncdiscoverinternal".\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="b75c6-162">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="b75c6-163">Datensätze.</span><span class="sxs-lookup"><span data-stu-id="b75c6-163">records.</span></span>
    
    <span data-ttu-id="b75c6-164">Das letzte Element ist für Sie am interessantesten – falls ein SAN-Eintrag für "lyncdiscover" bzw. für "lyncdiscoverinternal" vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b75c6-164">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="b75c6-165">Sobald Sie über diese Informationen verfügen, können Sie die Zertifikatansicht und die MMC schließen.</span><span class="sxs-lookup"><span data-stu-id="b75c6-165">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="b75c6-166">Wenn ein AutoErmittlungsdienst, das heißt lyncdiscover. \> Domänenname \> und "lyncdiscoverinternal".\<domain name\></span><span class="sxs-lookup"><span data-stu-id="b75c6-166">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="b75c6-167">(je nachdem, ob es sich um ein externes oder internes Zertifikat handelt) fehlt der Alternative Antragstellername, und Sie verwenden ein einzelnes Standardzertifikat für die Typen Default, "webservicesinternal" und WebServiceExternal, und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b75c6-167">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="b75c6-168">Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-168">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="b75c6-169">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="b75c6-169">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="b75c6-170">Verwenden Sie stattdessen den DomainName-Parameter.</span><span class="sxs-lookup"><span data-stu-id="b75c6-170">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="b75c6-171">Wenn Sie den DomainName-Parameter verwenden, müssen Sie den FQDN für die Datensätze "lyncdiscoverinternal" und "lyncdiscover" definieren.</span><span class="sxs-lookup"><span data-stu-id="b75c6-171">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="b75c6-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b75c6-172">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="b75c6-173">Geben Sie Folgendes ein, um das Zertifikat zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="b75c6-173">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="b75c6-174">"Thumbprint" steht für den Fingerabdruck, der für das neu ausgestellte Zertifikat angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b75c6-174">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="b75c6-175">Gehen Sie wie folgt vor, wenn Sie separate Zertifikate für "Default", "WebServicesInternal" und "WebServicesExternal" verwenden und ein alternativer Antragstellername für den internen AutoErmittlungsdienst fehlt:</span><span class="sxs-lookup"><span data-stu-id="b75c6-175">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="b75c6-176">Geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung für die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-176">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="b75c6-p118">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den DomainName-Parameter verwenden. Bei Verwendung des DomainName-Parameters müssen Sie für den FQDN der SIP-Domäne ein entsprechendes Präfix verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b75c6-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="b75c6-181">Wenn ein alternativer Antragstellername für einen externen AutoErmittlungsdienst fehlt, geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b75c6-181">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="b75c6-p119">Wenn Sie über viele SIP-Domänen verfügen, können Sie den neuen AllSipDomain-Parameter nicht verwenden. Stattdessen müssen Sie den DomainName-Parameter verwenden. Bei Verwendung des DomainName-Parameters müssen Sie für den FQDN der SIP-Domäne ein entsprechendes Präfix verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b75c6-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="b75c6-186">Geben Sie Folgendes ein, um die einzelnen Zertifikattypen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="b75c6-186">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="b75c6-187">"Thumbprint" steht für den Fingerabdruck, der für die neu ausgestellten Zertifikate angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b75c6-187">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

