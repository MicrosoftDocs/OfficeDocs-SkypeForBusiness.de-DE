---
title: 'Lync Server 2013: Konfigurieren der Active Directory-Verbunddienste (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="9eabb-102">Konfigurieren der Active Directory-Verbunddienste (AD FS 2,0) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eabb-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eabb-103">_**Letztes Änderungsdatum des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="9eabb-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="9eabb-104">Im folgenden Abschnitt wird beschrieben, wie Active Directory-Partnerverbunddienste (AD FS 2.0) konfiguriert werden muss, damit die mehrstufige Authentifizierung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9eabb-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="9eabb-105">Informationen zum Installieren von AD FS 2,0 finden Sie unter Schritt-für-Schritt-Anleitungen zu AD FS 2,0 und Anleitungen unter [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="9eabb-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9eabb-106">Wenn Sie AD FS 2.0 installieren, dürfen Sie nicht den Windows Server Manager verwenden, um die Active Directory-Partnerverbunddienste-Rolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9eabb-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="9eabb-107">Laden Sie stattdessen das 2,0-RTW-Paket für Active Directory Federation Services <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>unter herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="9eabb-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="9eabb-108">**So konfigurieren Sie AD FS für die zweistufige Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="9eabb-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="9eabb-109">Melden Sie sich beim AD FS 2.0-Computer über ein Domänenadministratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="9eabb-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="9eabb-110">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9eabb-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="9eabb-111">Führen Sie aus der Windows PowerShell-Befehlszeile den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9eabb-111">From the Windows PowerShell command-line, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  <span data-ttu-id="9eabb-112">Einrichten einer Partnerschaft mit jedem lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Director, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen, wobei die für Ihre Bereitstellung spezifischer Servername:</span><span class="sxs-lookup"><span data-stu-id="9eabb-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="9eabb-113">Starten Sie aus dem Menü „Verwaltung“ die AD FS 2.0-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="9eabb-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="9eabb-114">Erweitern von Vertrauensstellungen für **vertrauenswürdige Beziehungen** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="9eabb-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="9eabb-115">Überprüfen Sie, ob eine neue Vertrauensstellung für Ihren lync Server 2013 mit kumulativen Updates für lync Server 2013: Juli 2013 Enterprise-Pool oder Standard Edition-Server erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9eabb-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="9eabb-116">Erstellen Sie eine Ausstellungsautorisierungsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="9eabb-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="9eabb-117">Erstellen Sie eine Ausstellungstransformationsregel für Ihre Vertrauensstellung der vertrauenden Seite und weisen Sie diese Regel zu. Führen Sie dazu über Windows PowerShell die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="9eabb-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="9eabb-118">Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf Ihre Vertrauensstellung der vertrauenden Seite und wählen Sie **Anspruchsregeln bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="9eabb-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="9eabb-119">Wählen Sie die Registerkarte **Ausstellungsautorisierungsregeln** aus und vergewissern Sie sich, dass die neue Autorisierungsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9eabb-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="9eabb-120">Wählen Sie die Registerkarte **Ausstellungstransformationsregeln** aus und vergewissern Sie sich, dass die neue Transformationsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9eabb-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

