---
title: 'Lync Server 2013: Konfigurieren von Active Directory Verbunddiensten (AD FS 2.0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="a6308-102">Konfigurieren von Active Directory Verbunddiensten (AD FS 2.0) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6308-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6308-103">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="a6308-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="a6308-104">Im folgenden Abschnitt wird beschrieben, wie Sie Active Directory Verbunddienste (AD FS 2.0) zur Unterstützung der mehrstufigen Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a6308-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="a6308-105">Informationen zum Installieren von AD FS 2.0 finden Sie unter AD FS 2.0 Schritt-für-Schritt und Anleitungen unter [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="a6308-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="a6308-106">Verwenden Sie beim Installieren von AD FS 2.0 nicht den Windows Server-Manager, um die Active Directory Rolle "Verbunddienste" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a6308-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="a6308-107">Laden Sie stattdessen das RTW-Paket für Active Directory Verbunddienste 2,0 unter <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="a6308-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="a6308-108">**So konfigurieren Sie AD FS für die zweistufige Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="a6308-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="a6308-109">Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0 Computer an.</span><span class="sxs-lookup"><span data-stu-id="a6308-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="a6308-110">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6308-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="a6308-111">Führen Sie in der Windows PowerShell Befehlszeile den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a6308-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="a6308-112">Erstellen Sie eine Partnerschaft mit jedem lync Server 2013 mit kumulativen Updates für lync Server 2013: July 2013 Director, Enterprise-Pool und Standard Edition-Server, die für die passive Authentifizierung aktiviert werden, indem Sie den folgenden Befehl ausführen, und ersetzen Sie den für Ihre Bereitstellung spezifischer Servername:</span><span class="sxs-lookup"><span data-stu-id="a6308-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="a6308-113">Starten Sie im Menü Verwaltungs Tools die AD FS 2.0 Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="a6308-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="a6308-114">Erweitern Sie Vertrauensstellungen der vertrauenden **Seite**der **Vertrauensstellung** \> .</span><span class="sxs-lookup"><span data-stu-id="a6308-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="a6308-115">Stellen Sie sicher, dass für Ihre lync Server 2013 eine neue Vertrauensstellung mit kumulierten Updates für lync Server 2013 erstellt wurde: July 2013 Enterprise-Pool oder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="a6308-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="a6308-116">Erstellen und Zuweisen einer Ausstellungs Autorisierungsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="a6308-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="a6308-117">Erstellen und Zuweisen einer Ausstellungs Transformationsregel für die Vertrauensstellung der vertrauenden Seite mithilfe Windows PowerShell, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="a6308-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="a6308-118">Klicken Sie in der AD FS 2.0-Verwaltungskonsole mit der rechten Maustaste auf die Vertrauensstellung der vertrauenden Seite, und wählen Sie **Anspruchsregeln bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a6308-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="a6308-119">Wählen Sie die Registerkarte **Ausstellungs Autorisierungsregeln** aus, und stellen Sie sicher, dass die neue Autorisierungsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a6308-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="a6308-120">Wählen Sie die Registerkarte **ausstellungstransformationsregeln** aus, und stellen Sie sicher, dass die neue Transformationsregel erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a6308-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

